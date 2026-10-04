# Chat History - ace-run (research.d.gem)

- **TIMESTAMP:** 2026-09-25 20:12:13 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.d.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_195911.md`

## Prompt

%id(gem, clan=research.d)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.d.cld`, `research.d.grk`, `research.d.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you
audit all open memory beads for valid memory update recommendations? End your analysis
with a recommended set of memory file changes that you think I should make. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Audit: Open Memory Task Beads & Recommended Updates

**Researcher:** `research.d.gem` (Gemini 3.8 Flash)  
**Report File:** [`open_memory_beads_audit__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/open_memory_beads_audit__gem.md)  
**Artifact ID:** `explicit:631e60643ed767fdb51394d5` (`file:explicit:631e60643ed767fdb51394d5`)  
**Artifact Label:** `research:202609/open_memory_beads_audit__gem.md`  

---

## Executive Summary

An exhaustive independent audit of all **15 open task beads** of type `memory` was performed against the current SASE memory corpus under [`sase/memory/`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory), current codebase implementation, upstream epic landing state, and memory governance rules.

### Bead Disposition Breakdown

| Category | Count | Bead IDs | Summary |
| :--- | :---: | :--- | :--- |
| **Valid & Actionable Now** | **8** | [`sase-sa`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-sa/README.md), [`sase-st`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-st/README.md), [`sase-yd`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-yd/README.md), [`sase-12x`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-12x/README.md), [`sase-148`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-148/README.md), [`sase-16r`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-16r/README.md), [`sase-18a`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-18a/README.md), [`sase-18h`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-18h/README.md), [`sase-195`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-195/README.md) | Verified defects/gaps in memory documentation that should be applied now. |
| **Blocked on Active Epics** | **2** | [`sase-134`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-134/README.md), [`sase-ya`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-ya/README.md) | Documenting `%hold` and remote dispatch. `sase-134` is explicitly blocked on child epic `sase-11l.11` (currently in-progress repairing hold admission); `sase-ya` should wait until the `sase-xe.16` / `sase-133` dispatch epics stabilize. |
| **Already Implemented / Obsolete** | **1** | [`sase-sl`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-sl/README.md) | Visual PNG tolerance guidance was already corrected during the migration to [`lint_and_test.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/lint_and_test.md). Close as already done. |
| **Non-Memory Operational Boards** | **3** | [`sase-xs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-xs/README.md), [`sase-xt`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-xt/README.md), [`sase-xu`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/beads/pages/sase-xu/README.md) | Co-opted as supervisor message boards for Athena agent watch loops (Sep 6–7, 2026). Explicitly state: *"does not request a memory edit"*. Close / archive. |

---

## Recommended Set of Memory File Changes

The following concrete changes are recommended for implementation:

### 1. [`sase/memory/glossary/proc-shell.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/glossary/proc-shell.md) (re: `sase-sa`)
* **Problem:** Glossary definition restricts proc shells to "belonging to a sase agent", omitting stand-alone `%proc` launch units (`origin: xprompt-proc`). Note that while the bead references `sase/sase.yml`, glossary terms now live in strand files under `sase/memory/glossary/`.
* **Recommended Change:** Update the definition:
  ```markdown
  A proc shell is a named supervised proc with durable output and lifecycle state.
  A proc shell may belong to a sase agent (a session-attached monitor carrying timeout,
  workspace-claim, and follow-up policy) or run stand-alone (dispatched by a `%proc` launch
  unit with origin `xprompt-proc`, belonging to no agent and projected as its own row kind
  in the Agents tab). A gate shell's execution-phase proc does not make it a proc shell: it
  stays `shell_kind: "gate"` throughout, pending or executing.
  ```
* **Post-edit Action:** Run `sase memory init` to re-sync `AGENTS.md` and provider shims.

### 2. [`sase/memory/xprompts.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/xprompts.md) (re: `sase-st`)
* **Problem:** Documents `[[ ... ]]` multi-line text without the closing terminator rule or structural shorthand binding, causing parsing ambiguities for agents.
* **Recommended Change:** In the **Invoke** section, update `Args:` and `Shorthands:`:
  ```markdown
  - Args: `#name(a, b)`, `#name(k=v)` (positional first), quoted comma/special
    values, `[[ ... ]]` multi-line text. A `[[` block closes at the first `]]`
    whose next non-whitespace character is an argument terminator (`,`, `)`, `}`,
    `|`, or end of the argument region); a `]]` anywhere else is content. A `]]`
    that must be followed by a terminator needs an explicit quoted argument
    instead.
  - Shorthands: `#name:arg`, `#name:a,b`, `` #name:`arg with spaces` ``, `#name+` =
    `#name:true`; line `#name: text` captures to blank line, `#name:: text` to next
    line-boundary directive. Shorthand free text (`#name: text`, `#name:: text`,
    `#name(args): text`) is bound structurally rather than re-lexed, so commas,
    `]]`, `+`, and unbalanced parens in prose stay inside the value. `+` decodes to
    a space only on the bare unquoted `#name:a,b` colon form.
  ```

### 3. [`sase/memory/lint_and_test.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/lint_and_test.md) (re: `sase-18h` & `sase-16r`)
* **Problem 1 (`sase-18h`):** Memory claims `just check` runs every whole-repo lint gate, but `Justfile` explicitly excludes `toobig` (enforced via `just lint` in CI; file splitting owned by `toobig_split`).
* **Problem 2 (`sase-16r`):** Memory predates epic `sase-169` and omits the exit-0 `partial` status, WARNING block check, lock waiting, and worker translation for visual snapshot updates.
* **Recommended Change:**
  1. In Section 1 overview:
     ```markdown
     `just check` runs every whole-repo lint gate except `toobig` plus a diff-scoped
     test lane (`just test-scoped`) that selects tests via a static import-graph closure.
     (CI enforces `toobig` through `just lint`, while the `toobig_split` routine owns
     automated file splits).
     ```
  2. In **PNG Snapshot Tests**:
     ```markdown
     Update mode (`just fix-tui-screenshots`, `just update-visual-snapshots`, and the
     update stage of local `just check-full`) salvages per node and per golden. When
     unrecovered failing nodes, unstable captures, or concurrent edits prevent updating
     certain goldens, it still exits 0 with status `partial`. After a `partial` run, agents
     must read the WARNING block or the manifest's `skipped` list and `pruning_skipped_reason`;
     do not assume exit 0 means all goldens updated. `-n N` / `--numprocesses N` after `--`
     is translated to the governed `SASE_PYTEST_WORKERS`. A second run in the same checkout
     waits for the maintenance lock (bounded, default 2 hours) instead of refusing at once.
     CI's dedicated `visual-test` job (`--check`) stays strict and never writes goldens.
     ```

### 4. [`sase/memory/tui_screenshot.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/tui_screenshot.md) (re: `sase-12x` & `sase-16r`)
* **Problem 1 (`sase-12x`):** Troubleshooting advises installing the "visual extra" for `resvg_py`, but `resvg_py` is now an unconditional runtime dependency in `pyproject.toml`.
* **Problem 2 (`sase-16r`):** Golden Maintenance section lacks the `partial` status and lock-wait update contract.
* **Recommended Change:**
  1. In **Troubleshooting**, update the first bullet:
     ```markdown
     - Missing resvg dependency: `resvg_py` is an unconditional runtime dependency for
       normal installs; a missing import indicates an incomplete or stale SASE environment.
       Run `sase update` or reinstall/upgrade the Python environment owning the `sase`
       entry point. The single canonical renderer contract remains.
     ```
  2. In **Golden Maintenance**, document the `partial` update contract parallel to `lint_and_test.md`.

### 5. [`sase/memory/tui_perf.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/tui_perf.md) (re: `sase-195`)
* **Problem:** Rule 12 advises setting a guard flag and clearing it synchronously in `finally:`. Because Textual dispatches `OptionHighlighted` to the message queue, the handler executes *after* `finally:` has cleared the flag, causing cursor freezes or skipped selection indices.
* **Recommended Change:** Rewrite Rule 12:
  ```markdown
  12. **Guard programmatic widget updates against queued echoes.** `OptionList` emits
      `OptionHighlighted` as an asynchronous queued message on programmatic `highlighted = X`
      assignments. A guard flag cleared synchronously in `finally:` never catches the echo
      because the handler executes long after the flag is cleared. Instead, use a check that
      survives the message queue: count pending programmatic echoes per row
      (decrementing as each echo arrives) and discard messages whose `Option` is no longer
      in the current list, or check against the last programmatic index or a generation
      counter. See `CommandLinePopup` (`src/sase/ace/tui/command_line/popup.py`,
      `_pending_echoes`) for the reference implementation. `clear_options()` clears highlights
      without posting messages.
  ```

### 6. [`sase/memory/decisions/machine-link-writes-off-primary.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/decisions/machine-link-writes-off-primary.md) (new strand, re: `sase-yd`)
* **Problem:** Epic `sase-y3` established the architectural rule that background machine mutations never target sidecar clones nested under the human primary checkout (`~/.sase/projects/<key>/repos/<role>` vs `hidden_sidecar_clone_dir`), but no decisions strand records it.
* **Recommended Change:** Create a new decision record strand documenting Claim, Why (over primary mutation, relaxing authorization, or numbered workspaces), Cost (second on-disk clone per role), and Reopen Condition. Link to [`decisions:host-owned-completion`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/decisions/host-owned-completion.md).

### 7. [`sase/memory/decisions/tool-run-handoff-fail-closed.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/decisions/tool-run-handoff-fail-closed.md) & [`decisions/record-before-admit.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/decisions/record-before-admit.md) (re: `sase-18a`)
* **Problem:** E2 durable ToolRun hand-off made explicit `sase tool run -H` fail-closed when reservations cannot be committed, narrowing the claim in `decisions:record-before-admit` that recording always stays fail-open.
* **Recommended Change:** Create `tool-run-handoff-fail-closed.md` as a new strand and mark `record-before-admit.md` `Partly superseded` with a back-link.

### 8. [`tools/AGENTS.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/AGENTS.md) and Shims (re: `sase-148`)
* **Problem:** Line 65 states live smoke cases remain labeled `phase-pending` without `--live`, but the harness (`tools/smoke_sase_tool_runs`) emits `not-run`.
* **Recommended Change:** Update the sentence to:
  ```markdown
  The three live cases (`dod-8-live-monitor`, `dod-8-live-proc`, `dod-13-overhead`) are
  labeled `not-run` unless `--live` is passed; passing `--live` runs all 35 cases.
  ```
  Sync with [`tools/CLAUDE.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/CLAUDE.md), [`tools/GEMINI.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/GEMINI.md), [`tools/OPENCODE.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/OPENCODE.md), and [`tools/QWEN.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tools/QWEN.md).

---

## Action Plan for Bead Closures

1. **Apply the 8 valid edits above**, then close beads `sase-sa`, `sase-st`, `sase-yd`, `sase-12x`, `sase-148`, `sase-16r`, `sase-18a`, `sase-18h`, and `sase-195`.
2. **Close `sase-sl` as already resolved** (`already_done`), noting that `lint_and_test.md` already enforces exact pixel equality.
3. **Close or retriage `sase-xs`, `sase-xt`, and `sase-xu`**, recording them as settled supervisor logs from early September.
4. **Leave `sase-134` open**, blocked until child epic `sase-11l.11` closes.
5. **Leave `sase-ya` open**, deferred until remote dispatch stabilization lands.
