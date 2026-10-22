# Chat History - ace-run (research.47.final)

- **TIMESTAMP:** 2026-10-09 14:12:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.47.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_130507.md`

## Prompt

%clan(research.47, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] A
number of sase agents just failed on this machine with the following error:
`ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`

- This error was clearly caused by updating sase while agents were running, which is
  something I would like to support.
- I would like to start automatically detecting errors like this and attempting to
  automatically resolve the issue by dismissing and re-launching the sase agent that
  failed.
- We should try to restart an agent exactly once when a detected error pattern matches.
  Think hard about which error patterns we should check for.
- This operation should be very similar to what happens when the user selects a failed
  agent on the "Agents" tab, uses the `,x` keymap to dismiss and edit it, and then
  submitting the prompt (e.g. via the `<ctrl+g><enter>` keymap) that loads in the prompt
  input widget without modifying it.
- We should send an excellent and thorough sase notification to the user when we restart
  a failed agent like this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.47.final %m:@xlarge
%wait:research.47.cdx %wait:research.47.cld %wait:research.47.grk %wait:research.47.mus %wait:research.47.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

A
number of sase agents just failed on this machine with the following error:
`ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`

- This error was clearly caused by updating sase while agents were running, which is
  something I would like to support.
- I would like to start automatically detecting errors like this and attempting to
  automatically resolve the issue by dismissing and re-launching the sase agent that
  failed.
- We should try to restart an agent exactly once when a detected error pattern matches.
  Think hard about which error patterns we should check for.
- This operation should be very similar to what happens when the user selects a failed
  agent on the "Agents" tab, uses the `,x` keymap to dismiss and edit it, and then
  submitting the prompt (e.g. via the `<ctrl+g><enter>` keymap) that loads in the prompt
  input widget without modifying it.
- We should send an excellent and thorough sase notification to the user when we restart
  a failed agent like this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.47.cdx`, `research.47.cld`, `research.47.grk`, `research.47.mus`, `research.47.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.47.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.47.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

I've opened the research repo and am now reading the five reports (the cdx one has two snapshots, so I'm checking whether they differ).

The canonical cdx file matches the newer snapshot, so there is one cdx report. Reading all five now.

Read grk, mus, and gem. Now reading the full cdx and cld reports, which were too large to show inline.

The five reports are moved. Before writing, I'm checking an existing `__final.md` in the research repo so the consolidated report matches house style.

Writing the consolidated report now.

Report written. Registering it as a durable artifact for the linker.

Registered. Verifying the final layout, then submitting the final declaration.

The consolidated report is written and registered for the linker as `file:explicit:dc6c8cdfa8506080181eab6d`. The host will commit it after this turn.

**One thing to act on now:** `chop.refresh_docs.sase.9_780508.2` will die with the same `auto_launch_prefix` ImportError when `.1` finishes. It started on an affected revision and is still waiting, so it hasn't started its model turn. Relaunching it now with `,x` and an unchanged submit costs nothing.

**What actually happened.** I confirmed this from the runner logs, and it corrects several of the five reports:
- Five agents died, not four: `research.46.final`, `research.46.image`, `toobig-7h.test_justfile_lint.0`, `sase-1j1.6`, and bob-cli `0yz`.
- All five crashed inside `refresh_runner_code_after_wait()`, the code meant to survive a sase update during a `%wait`. It notices the code changed, then loads a few new modules *before* restarting itself. Old in-memory code asked the new files for `auto_launch_prefix`, which `9fd8a081f4` removed at 11:49.
- All five were still waiting, so no model work was lost and `,x` was exactly the right fix.
- Current master still has this shape, so the next rename of one of those modules will cause the same failure.
- Two reports' fixes would not have helped: grk and gem suggest preloading `sase.monitor`, but that preload only runs after the wait.
- The `sase dev update` log isn't a complete record: HEAD moved between 11:53 and 13:33 with no entry, so it can't be the main evidence that sase changed during a run.

**Is it a good idea?** Yes, as a safety net. About 43 agents have died this way since July (my own scan found 44), with 33 updates in the last four days. The design changes I'd make:
- **"Exactly once" becomes "at most once per agent lineage"**, recorded durably before anything is touched.
- **Only automate `,x` for agents that died before their model turn.** About half of past cases died after it; there a fresh relaunch would redo hours of work and strand the finished diff. For those, notify and leave the workspace held.
- **A matching error isn't enough.** Also require evidence that sase changed during the run, plus a fresh process that can import the *current* code. cld's version checks that the same import now succeeds, which would refuse today's incident because the symbol is gone for good.
- **Save the evidence first.** `,x` with name reuse deletes the old run's artifacts, error report and notifications, and the user never saw the failure.
- **Ship the prevention fix first:** restart before loading anything new, plus a test that fails if anything is imported in between.

**Recommended solution:**
- **Where it runs:** a separate process, never the dying agent or the TUI. The failing runner only triggers it, through the existing `code_swap_guarded_exec.py` bootstrap, which waits for any in-progress update to finish. A periodic sweep catches anything missed.
- **How it relaunches:** the same `plan_agent_restart` / `execute_agent_restart` path the provider drain already uses, keeping the same agent names. Dependencies go first.
- **Logic placement:** the error classifier and the once-only record go in sase-core.
- **The notification:** one `↻` notification per update, in the amber (`#FFAF5F`) the Updates panel already uses for stale running code. It has a live report showing each replacement's current status and a single info toast; red alerts only when something needs you.
- **Long term:** pin each process to a fixed copy of the code it started with, so updating while agents run is safe by design.

The report ends with four open questions for you: auto-resuming agents that died after their model turn, always reusing names, a second restart after a later update, and whether you want release pinning.

Files are in `sase/repos/research/202610/update_skew_agent_auto_restart/`:
- `update_skew_agent_auto_restart__final.md`
- `update_skew_agent_auto_restart__cdx.md`
- `update_skew_agent_auto_restart__cld.md`
- `update_skew_agent_auto_restart__grk.md`
- `update_skew_agent_auto_restart__mus.md`
- `update_skew_agent_auto_restart__gem.md`
