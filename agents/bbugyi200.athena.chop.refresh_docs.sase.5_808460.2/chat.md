# Chat History - ace-run (chop.refresh_docs.sase.5_808460.2)

- **TIMESTAMP:** 2026-09-21 21:55:45 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.5_808460.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_808460.2, tribe=chop)
%wait:chop.refresh_docs.sase.5_808460.1
%queue(capacity=1)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

The four verification passes are done: most claims hold, and a handful are wrong. I'm now fixing the docs.

The ace.md and axe.md fixes are in. Next I'm correcting beads, notifications, configuration, llms, and workspace.

All doc fixes are applied. Now I'm running the repo's documentation checks.

The Markdown formatting check passes. Now running the repo's `check` gate.

I checked every claim in the update agent's docs commit (`5453acde0b`) against the code. Most held up; I fixed the ones that didn't in 7 files. The strict docs build, the Markdown formatting check and `sase tool run check` all pass. The fixes are declared for the host to commit.

**What was wrong, now fixed:**
- **`SVC` pill (`ace.md`, `axe.md`):** the docs said the old RUNNING/STOPPED/RESTARTING labels show until the first status snapshot arrives, and that `-R` shows RESTARTING. In reality the health pill takes over after the first status load, showing a teal `0/0` if no snapshot could be read. So the old labels only flash briefly at startup, and `-R` never shows RESTARTING. I also fixed which procs the `N/M` count includes, and noted that any host state other than running (including starting) reports as "host stopped".
- **Other `ace.md` fixes:**
  - The Services info panel shows "stopped" for a host that is starting or has a stale heartbeat.
  - The quit dialog's count also leaves out monitor shells, and stopping the scheduler is best effort.
  - The Beads footer only appears when there are more than five rows.
  - A batch of reminders that come back from snooze produces one toast per row (or grouped toasts when more than three arrive), not a single toast.
  - I moved the `GateExecutionFailed` row into alphabetical order in its table.
- **`beads.md`:**
  - The touch index is not refreshed by bead changes that go through the Rust fast path, such as a plain `update`, `+1` or `snooze`. `sase bead sync` does refresh it.
  - The doctor check has more states than the docs listed.
  - The glyph table is ordered strongest to weakest, which it now says.
  - The "No beads touched" message also appears when the `-v` filter matches nothing.
- **`notifications.md`:**
  - In the gate-failure dialog, `R` means "Run the whole branch again", and only for the `command` and `terminal_prepare` stages.
  - The bell also needs a `tmux_ring_bell` helper on `PATH`.
  - I defined "settlement notification" where it is first used.
- **`configuration.md`, `llms.md`, `workspace.md`:**
  - The Antigravity weekly-window wording is now accurate.
  - The row for the legacy detach-scope environment variable now matches the current one.
  - An agent run's workspace-preparation error leaves out the failing step name.

**Suspected code bugs (not fixed; also listed in the commit message):**
1. `tmux_ring_bell` isn't in `tools/`. The bell only works because a copy happens to be on your `PATH`, and it fails silently without one (`_ring_tmux_bell` in `src/sase/ace/tui/actions/agents/_notification_polling.py`).
2. The gate-failure dialog always shows Resume, but pressing `r` when the selected options can't be recovered silently does nothing (`src/sase/ace/tui/actions/agents/_notification_gate_recovery.py`).
3. Bead changes handled by the Rust fast path never refresh the touch index, so the doctor check's advice "Run any `sase bead` mutation" is misleading (`src/sase/main/bead_fast_path.py`, `src/sase/doctor/checks_beads.py`).
4. The `sase bead touched` help text says views come from human `show` views, but only agent views are logged. The update agent had already flagged this one (`src/sase/main/parser_bead_touched.py` vs `src/sase/bead/bead_views.py`).
