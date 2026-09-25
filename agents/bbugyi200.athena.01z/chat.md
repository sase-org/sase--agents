# Chat History - ace-run (01z)

- **TIMESTAMP:** 2026-08-15 07:11:58 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 01z

## Prompt

#gh:gh_sase-org__sase Can you describe the @research:202608/proc_ownership_and_shell_taxonomy/proc_ownership_and_shell_taxonomy.md file? %m:grok/grok-4.6

## Response

I'll open the research sidecar through the repo skill first, then read that taxonomy file and summarize it.

The sidecar is open. Next I’ll read the taxonomy report and summarize what it actually says.

The report is long; I’ll pull the remaining sections so the description covers the full argument.

This is a consolidated research report in the `sase--research` sidecar. It answers how SASE should own background work and name the things that run it.

**File:** `202608/proc_ownership_and_shell_taxonomy/proc_ownership_and_shell_taxonomy.md`  
**Date:** 2026-08-14  
**Status:** research (not an implementation plan)

It merges two earlier reports (`__a` from Codex, `__b` from Claude), then re-checks them against `sase` at `5601920c9`, the linked `sase-core` checkout, and the live proc/agent stores. It also sits on three 2026-08-13 reports: detached-proc convergence, named proc shells, and the monitor command substrate.

The research question is three-part:

1. Stop running procs inside the ACE TUI. Every proc should be supervisor-owned and detached, and `-d|--detached` should leave `sase proc run`.
2. Fold sase monitors into sase procs via `--shell <name>`, with `sase monitor` remaining as a service-level wrapper.
3. Adopt this vocabulary: **agent lane → sase agent**, plus **agent shell**, **proc shell**, and **sase shell**.

---

### The taxonomy

A **sase agent** is either an agent family or a solo agent. A **sase shell** is one executable member of that agent: an **agent shell** (an LLM/provider run) or a **proc shell** (a named, supervised command). The report’s anchor sentence is:

> A sase agent is a sequence of sase shells.

A family container (`pc`) is a sase agent but not a shell. Clans, hoods, and tribes are not shells either.

The report’s main claim is that this model **already exists in the code**; it just has no names. `sase agent list -a` already returns a mixed list of agent shells and proc shells. On the day of the snapshot, 73 rows included 30 with `agent_family_role="monitor"`. Proc shells already have names in the agent namespace (`sase-m4.6--mon-0`), and `sase monitor` already resolves id, shell, and agent. Suffix allocation (`--mon`, `--mon-0`) already exists.

So the taxonomy epic is documentation, glossary, help text, and one CLI option swap — not a new architecture. The report also says **do not add a top-level `sase shell` command**. That name belongs to the concept. Keep `sase monitor`.

Only one of five meanings of “lane” should be renamed: **agent lane**. AXE chop lanes, scoped-test lanes, ACE display lanes, and launch-override lanes stay. Rust is almost untouched (~33 hits).

---

### Identity is not exclusion

This is the one real disagreement between the two source reports, and the consolidated report sides with `__a`.

- `shell_name` is identity: you can `show` / `kill` / `list` by name.
- `concurrency_keys` is exclusion: a set with overlap semantics.

`__b` wanted one field to do both (“the name *is* the dedup key”). That cannot express ACE’s current exclusion, which is set-overlap (`requested & info.exclusive_scopes`). One live call site claims three scopes at once (`sase-update`, `agent-cli-update`, `agents-sync`). Collapsing the two would repeat the `kind` mistake: one field encoding two orthogonal facts.

Consequence: standalone proc shells (named procs that are not family-attached monitors) are **not** a prerequisite for moving ACE procs out of the TUI. Migrated ACE work needs concurrency keys, not names. Most of it should not mint a sase agent at all.

---

### Concrete design calls

| Decision | Choice |
| --- | --- |
| `--shell` short option | **`-N`**, not `-S` (`-S` is already `--status` on `sase proc list`) |
| Timeouts on `ProcWire` | **integer milliseconds** (`Option<u64>`). `ProcWire` derives `Eq`; `f64` seconds would not compile |
| Supervisor | Promote the **monitor** kernel (`double-fork`, timeouts, identity-over-pid). Delete `procs/supervisor.py`. Ship that swap alone for bisectability |
| `sase monitor` | Keep it as a **direct Python facade** over `sase.procs`. Not a CLI-to-CLI wrapper (extra ~0.58s + version skew), not a wrapper process (kill would destroy the settler) |
| Monitor `start` flag rename | `-a/--agent` on `start`; on `list`, keep `-l` and only rename the long option (because `-a` is `--all`) |

A shell name containing `--` is fully qualified (`pc--check`). A bare name is a suffix under the calling agent. Uniqueness is `(project, fully-qualified shell name)`, which also means at most one active shell per sequential sase agent.

Namedness, session attribution, family attachment, and execution ownership stay independent. There should be no `kind="shell"`.

---

### The two large follow-on epics

**Epic B — merge monitors into procs.** Additive wire v3 (`shell_name`, `artifacts_dir`, integer-ms timeouts, `concurrency_keys`, fingerprints, etc.), atomic store ops (`reserve_proc` / `request_proc_stop` / `finish_proc`), kernel swap, then named shells, family attachment, and the monitor facade. Terminal proc status must mean fully settled (claim released, follow-up launched or suppressed, artifacts written).

**Epic C — no procs inside ACE.** The real producer inventory is **56 call sites in 36 files** (`_submit_tracked_proc` 39 + `_submit_proc` 17). Both prior reports undercounted; `_submit_background_proc` does not exist. Long work (patch kill, agent dismiss, updates, launches) becomes detached procs. Sub-second work such as “Stash prompt” (~90 ms vs ~1.0–1.2 s of detached startup) should become a plain Textual worker, not a proc.

Then drop `-d|--detached` from `run` and `list`. It already chooses attribution, not detachment. Keep `--session`. Reject `--detached` for one release with an actionable message.

---

### Highest-severity traps

1. **Kind removal.** `validate_kind` runs on **read** and silently skips invalid rows. All 101 live store rows were `kind="tui"`. Removing `tui` from `PROC_KINDS` would make the visible proc store empty.
2. **Log pruning.** `delete_proc_logs` currently ignores `log_path` and only deletes under `proc_logs_dir()`, which accidentally protects artifacts logs. Making the pruner path-driven would start deleting those logs on nearly every append.
3. **Producer undercount.** A migration scoped to 41 sites would miss all 17 `_submit_proc` callers.

---

### Recommended sequence

1. Land the **taxonomy alone** (behavior-preserving).
2. Merge monitors into procs, keeping identity and exclusion as separate fields.
3. Then pull ACE procs out of the TUI and remove `--detached`.

Epic C depends on Epic B phases 1–4 (wire, kernel, atomic concurrency keys), **not** on standalone shells.

The file ends with acceptance criteria, eight open decisions (including whether to fix `sase monitor start`’s three required options, which violate `cli_rules.md`), and a risk list centered on naming fatigue, silent history loss, and dual-record divergence.
