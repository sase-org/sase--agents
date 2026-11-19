# Chat History - ace-run (sase-1tz.2.1.6)

- **TIMESTAMP:** 2026-11-19 17:52:35 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tz.2.1.6

## Prompt

%auto
#gh:gh_sase-org__sase
%id(6, clan=sase-1tz.2.1, bead=sase-1tz.2.1.6)
%model:@medium
%w(sase-1tz.2.1.4, for_epic=false)
%w(bead=sase-1tz.2.1.4)
Can you complete the work for bead sase-1tz.2.1.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2.1.6` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2.1.6` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2.1.6 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2.1.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2.1.6 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2.1.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2.1.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead **sase-1tz.2.1.6 is closed**.

**What landed**

- **sase-core** (`sase/repos/linked/sase-core`, uncommitted for the land stitch): new terminal `unrecoverable` deferred-prompt outcome. It fires only when past grace, attempts exhausted, no local source, and no sidecar copy. Wire fields are `#[serde(default)]`, so old payloads still parse and old cores simply never report it.
- **sase**: restore and prepare now probe **both** the row's `artifacts_dir` and the inventory run's `source_label` (the stale-dir gap, with regression tests). Terminal failures retire over two passes with a deterministic `prompt_archive_unrecoverable: <evidence>` reason — no quarantine, never acknowledged as success — append one record to `~/.sase/agent_publication/terminal_obligations.jsonl`, are skipped by `--retry-quarantined` revival, and release pool protection. No workspace-hold change: missing sources create no dirty paths, so no hold is tied to them (verified in the settle path).
- **Docs**: `hood-sync.md` (terminal section) and the `--retry-quarantined` help/CLI row (`terminal rows stay retired`). The two still-test-only readers are allow-listed via `--epic-symbol` re-keyed to open **sase-1tz.2.1.7** (confirmed: no epic-symbol entries remain for .6).

**Verification (observed, not inferred)**

- sase-core: 70/70 `agent_publication_recovery` tests pass (3 new unrecoverable goldens), clippy and fmt clean.
- sase: 8 new terminal tests + sync-level retire/audit test + 2 facade tests pass; deferred dir, core recovery, and pool staging suites green (72 passed). `fmt`, `ruff`, `mypy` all pass.
- Measurements (read-only): athena 369 quarantined prompt rows / 13 terminal / 32 missing-source digest lines in 7d; apollo 263 / 312.

**Left for land** (recorded on the bead): commit the sase-core half and ratchet `sase-core-revision.txt` (Python side degrades gracefully until then). Pre-existing failures that reproduce identically on the clean tree were filed as follow-ups, not fixed: the drain-accounting lazy-import isolation bug, `test_cleanup_after_success_does_not_resurrect`, and the `LaunchPromptContext` symvision finding.

Declaration accepted for `commit` (main: close, sase-core: keep). Bead sase-1tz.2.1.6 work preserved for host commit.
