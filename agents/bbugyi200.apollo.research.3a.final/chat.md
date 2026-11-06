# Chat History - ace-run (research.3a.final)

- **TIMESTAMP:** 2026-11-04 15:59:04 EST
- **MODEL:** claude/opus
- **AGENT:** research.3a.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261104_150927.md`

## Prompt

%clan(research.3a, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to start working through this project's task beads, starting with the 10 most
important / impactful ones that I should work. Can you do some research to help me
determine what those 10 beads are? If <10 actually need to be worked, then recommend
only the task beads that you feel should be worked. Make sure that you review any
running sase agents on this machine and my athena machine before selecting the task
beads, to make sure that an ongoing epic (for example) isn't going to conflict with any
of them.

End your analysis with a ranked list of task beads that you think should be worked, with
justification and a recommended solution for each.]]) %id:research.3a.final %m:@xlarge
%wait:research.3a.cdx %wait:research.3a.cld %wait:research.3a.grk %wait:research.3a.mus %wait:research.3a.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to start working through this project's task beads, starting with the 10 most
important / impactful ones that I should work. Can you do some research to help me
determine what those 10 beads are? If <10 actually need to be worked, then recommend
only the task beads that you feel should be worked. Make sure that you review any
running sase agents on this machine and my athena machine before selecting the task
beads, to make sure that an ongoing epic (for example) isn't going to conflict with any
of them.

End your analysis with a ranked list of task beads that you think should be worked, with
justification and a recommended solution for each.

When you author or carry over Mermaid diagrams, load `/mermaid_diagrams` before
drafting, even when no image or diagrams companion runs. The skill has the shared
figure-selection, styling, and PDF-render review rules. If the provider skill is not
deployed, verify the edited plugin's guide with `sase macro show skill/mermaid_diagrams --format raw` (or
`sase macro show /mermaid_diagrams --format raw`) and use the form this host supports.
This guidance does not enable a companion diagrams agent.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3a.cdx`, `research.3a.cld`, `research.3a.grk`, `research.3a.mus`, `research.3a.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3a.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3a.linker`, can find it:

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

Reading the remaining three researcher reports next, then I'll do my own live-agent and bead checks.

Read all five reports. Now checking live agents on apollo and athena myself, since the conflict screen is where the reports disagree most.

Pulled the live task-bead inventory (392 active now). Next I'll check the status of every candidate the five reports named and run quick repros on the contested ones.

The private store is confirmed `PRIVATE`, so sase-1db is a latent guard rather than active exposure. Now running quick repros on contested candidates.

Confirmed 39 in-progress epics with every child closed (sase-12u). Checking recent master history for any candidate that has already been fixed.

agy is only ~1% of runs since Nov 1 (17 of ~1,700 across both hosts), so sase-15o's real impact is small. Last overlap check is the prompt-loss pair (1ce/1cg) against the hijack prompt-bar phase.

All picks re-confirmed against current code. Loading the Mermaid guide before drafting the sequencing figure.

A sequencing table answers "what starts now versus what waits" well enough, so the report won't include a figure. Now setting up the output directory and moving the five reports.

All five reports are moved. Writing the consolidated report now.

Registered the report as `file:explicit:bfac58b15b4354a8dfd1a802`. Checking the final layout, then finalizing the turn.

I've written the merged report and registered it for the linker agent. Ten task beads are worth working now. Eight can start immediately; one (sase-1qj) should be planned now but landed after the Agent Hijack epic's restart and crash-repair phases on athena close. I checked live agents on apollo and athena at 20:44 UTC; none of the picks touch files the running epics are changing.

**Ranked list:**

1. **sase-1r4**: a live `sase update` that changes a function signature silently kills running agents. On 11-03 it killed three and left a monitor stuck for about six hours. **Fix:** recognise that error as update skew only when the code actually changed, explain it in the failure notice, and settle the stranded monitor. Stay away from the hijack epic's recovery helpers.
2. **sase-1al**: a trio of command-line panel tests fails in 13 of 26 full test runs on apollo, including every failed run since 11-03 and a run with no code changes. **Fix:** give these tests a pre-built grammar instead of raising timeouts.
3. **sase-zo**: `sase repo list -p sase` still exits 2 (I reproduced it); this bead has 10 independent confirmations. **Fix:** resolve `-p` through the project registry so the display name works.
4. **sase-1qj**, folding in **sase-12u**: the 11-01 athena reboot stranded 27 waiting agents. 39 of 120 in-progress epics have every child closed. **Fix:** a reconciler that runs after a reboot, frees claims held by dead agents, and relaunches each stuck epic exactly once.
5. **sase-1pw**: pytest workers waiting for test slots can starve for 45 minutes and exit without running anything. **Fix:** serve waiters in arrival order.
6. **sase-1q3**: `SASE_MODEL_OVERRIDE` leaks into pytest and causes 7 false failures. **Fix:** clear it in the test environment setup.
7. **sase-1qe**: each test's temp home gets slower to create as the run goes on. **Fix:** one parent directory per worker. Give 6 and 7 to one worker, since both edit the same file.
8. **sase-1ce**: if your editor exits with an error, the prompt you typed is deleted. **Fix:** save the changed text to the stash before deleting the temp file.
9. **sase-1qu**: this test fails every time it runs first in a fresh process (reproduced). **Fix:** first check whether the app really reads keymap files on the first keypress; if so, load them at startup.
10. **sase-172**: this test fails every time when run alone (reproduced). It may also be a real bug that deletes genuine bare-git `#git:` entries from the recent-items list when sase-github is installed. **Fix:** match the `#git:`/`#gh:` prefix before trying plugin patterns.

**Add-on:** put sase-1i6 in the same batch as 9 and 10. Its tests fail for every agent because the socket path is too long (reproduced; about a ten-line fix).

**Where I overrode the researchers:**
- **sase-1ot** (gem's #1, purging old secret-scanner hits): you rejected the history rewrite on 10-28, so it's your call, not agent work.
- **sase-1db** (cdx's #1, private attachment store): I confirmed the store is `PRIVATE`, so it's a missing safeguard, not a current leak. Ranked #14.
- **sase-15o** (agy tool-call tracking): a real bug, but agy ran only 17 of about 1,730 agent runs since 11-01.
- **sase-1r7** (credential retries): the publication epic's plan explicitly leaves it out. It's #11, to start after that epic lands.

**Two things only you can do:**
- **sase-j0**: still claimed by an agent that died on 10-26. The CI Telemetry workflow has failed all 7 runs since 11-01, wasting about 4.5 runner-hours per run. You need to release the claim and decide whether to retire or recalibrate the test-cost budgets.
- **sase-1ot**: close it, or renew it once the corrected scanner has re-checked the 27 hits.

Run three or four batches at a time, not all ten; athena already has 32 agent rows. Re-check both agent lists before each launch. I didn't edit or launch any beads and didn't run any full test suites.

The five researcher reports now sit beside the final report. The host commits the research repo after this turn.

Files are in `202611/next_ten_task_beads_live_epic_screen/`:
- next_ten_task_beads_live_epic_screen__final.md
- next_ten_task_beads_live_epic_screen__cdx.md
- next_ten_task_beads_live_epic_screen__cld.md
- next_ten_task_beads_live_epic_screen__grk.md
- next_ten_task_beads_live_epic_screen__mus.md
- next_ten_task_beads_live_epic_screen__gem.md
