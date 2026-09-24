# Chat History - ace-run (research.2i.final)

- **TIMESTAMP:** 2026-09-24 15:56:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2i.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_142941.md`

## Prompt

%clan(research.2i, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm thinking about moving
forward with the E3 and E4 epics described in the sase_tool_epic_roadmap.md file in the
research sidecar repo now that E2 (see the sase-17p epic bead) is almost complete. Can
you do some research with the goal of helping me determine if these epics are still
correct and appropriate? Should we make any changes to the epic? Flesh these epics out
enough that the epic landing criteria for both of these is crystal clear (the sase
agents that plan/implement/land these epics are likely to read this research).]]) %id:research.2i.final %m:opus
%wait:research.2i.cdx %wait:research.2i.cld %wait:research.2i.mus %wait:research.2i.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about moving
forward with the E3 and E4 epics described in the sase_tool_epic_roadmap.md file in the
research sidecar repo now that E2 (see the sase-17p epic bead) is almost complete. Can
you do some research with the goal of helping me determine if these epics are still
correct and appropriate? Should we make any changes to the epic? Flesh these epics out
enough that the epic landing criteria for both of these is crystal clear (the sase
agents that plan/implement/land these epics are likely to read this research).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, mus, gem, belonging to this
   dispatch's `research.2i.cdx`, `research.2i.cld`, `research.2i.mus`, `research.2i.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

I've opened the research sidecar and read the cdx report. Next I'm reading the other three researcher reports.

Checking the status of the E2 epic bead and its neighbors, using the audited `sase bead read` command.

I'm computing pass rates, how often the test stage is reached, and repeat-fingerprint counts from the ledger directly.

Found a data-quality problem: pytest fixtures inherit `SASE_TOOL_RUN_EVENTS` and write fake stages (e.g. "stage one") into the parent `check` run's timeline. Measuring how widespread it is.

That's 37 of the 101 `check` runs that reached the test stage. Next I'm opening sase-core to check how the E2 wire contract handles claims, attempts, and definition identity.

Still verifying claims before writing. Right now I'm reading the host-completion code to see what gates a prepared completion's commit.

I'm checking the existing test-selection health store: it already records per-test outcomes with a git-ancestry oracle, which E3 could reuse instead of building a second store.

Now reading the CLI rules and the relevant decision records so the proposed commands and scope fit the project's conventions.

Content-addressed matching also finds 0 repeats after a pass. I'm re-running with toolchain and env excluded from the key to rule out version noise.

Still 0 with toolchain and env excluded, so there's no measured pass-reuse opportunity at all. Now checking cld's claim that `_setup` already skips `install` when nothing is stale.

I have enough evidence to resolve the disagreements. Before writing, I'll file the stage-event contamination bug I found, using the `/sase_new_task` flow.

`sase-114` has the same root cause: the fixture's environment boundary leaks into the enclosing run. Adding a +1 with the new ToolRun-ledger evidence instead of filing a duplicate.

Filed as a +1 on `sase-114` rather than a new bead. Now I'm moving the four reports into a new topic directory in my research checkout.

Reports moved into `sase_tool_e3_e4_landing_criteria/`. Now writing the consolidated report.

The consolidated report is written. Checking the research checkout state before the final declaration.

Layout is correct and only the research checkout changed. Submitting the final declaration.

The consolidated report is written. The four researcher reports have been moved alongside it, and the commit for the research repo has been submitted. Short version: **E3 is still right but needs four changes. E4 as written is not supported by the data.** I recommend narrowing E4 to "verified completion", pending one policy decision from you.

**E3 (failure triage): plan it next, with four changes**
- **Target `check`, not `check-full`.** Athena recorded 497 sase `check` runs in 4.3 days against 1 `check-full` run. 86% of the `check` runs failed, and none passed today.
- **Let agent runs continue past stages whose failures are all KNOWN.** `just check` stops at the first failure, and master-red lint stages come first. So the test stage ran in only 20% of `check` runs, and 76% of agents ended on a run whose tests never ran. Your exit codes stay the same, and human and CI output stays byte-identical.
- **Use a precise, evidence-carrying rule for KNOWN.** The same failure must have been seen in another workspace, in a file that run didn't touch, at an ancestor commit, and not cleared since. Anything uncertain is labeled UNKNOWN. Landing is gated on a hand-audited backtest showing at least 95% of KNOWN labels are genuinely pre-existing.
- **Drop `rerun`.** Repeated runs on the same tree already reveal flaky tests without it. It also conflicts with E2's rule that a run id is claimed only once. The report states when to reconsider it.

**E4 (receipts and reuse): the reuse half has nothing to save**
- **No reuse opportunity.** Zero re-runs of an already-passing fingerprint in 527 runs. cld's count was keyed on the exact commit. I re-counted by file content, so a tree that is checked, committed, then checked again still counts, and it's still zero. The "lander re-runs the same tree" waste doesn't happen.
- **Refusing to re-run after a failure would be wrong.** In sase-core, 9 of 11 unchanged-tree re-runs after a failure passed, because of flaky tests.
- **The lint stages are not the cheap part.** It takes a median 247 s to reach the tests, which themselves take 52 s.
- **Recommendation:** make E4 a receipt that proves "this exact tree passed, or had no NEW failures". Prepared host completion would commit exactly that tree. It has never committed on athena: 6 uses, 5 blocked by a red `check`. Nothing is ever skipped.
- **The reuse part moves to a conditional E4b.** It opens only if at least 2 h/week of repeat runs on unchanged content show up for two consecutive weeks.

**Things I found that none of the four reports had**
- **Test fixtures write fake failed stages into real `check` runs.** 37 of the 101 runs that reached the test stage are affected. That's where gem's "stage one" failures came from. Rather than file a duplicate, I added this evidence as a +1 on the existing bug `sase-114`. It and `sase-182` (linked-repo runs recorded under the wrong project) are now listed as E3 prerequisites.
- **An existing pytest failure store has been overlooked.** `~/.sase/test-selection` holds 1,846 records with commit, workspace, and changed files. E3 should reuse it rather than build a second flaky-test store.
- **New catalog fields are costly.** Older sase-core versions reject unknown catalog fields, and adding one changes every tool's definition digest. So E3 needs no catalog changes, and E4's policy block must be excluded from the digest.
- **`parent_run_id` already means "nested run".** Any future retry link needs its own field.

gem's report contains several wrong numbers, and one of its landing tests uses `check-full`. The report lists them so planners don't cite them. Each epic has a full phase table and a numbered landing checklist.

**Decisions for you**
1. May prepared host completion commit when every remaining failure is KNOWN or flaky? This decides E4. I recommend yes, because it's stricter than today's normal path, where the agent just declares failures "unrelated". If no, defer E4.
2. Should continuation for agents be KNOWN-gated (recommended), always on, or opt-in only?
3. Do you accept dropping `rerun` from E3?
4. Should the triage decision record be written now or at landing?
5. Do you want the roadmap updated? I left it unedited; the report includes replacement rows for it.

Everything here comes from athena only. The test-selection reuse and the E3 backtest should be re-checked on apollo before E4 is planned.

Files are in `sase/repos/research/202609/sase_tool_e3_e4_landing_criteria/`:
- sase_tool_e3_e4_landing_criteria.md
- sase_tool_e3_e4_landing_criteria__cdx.md
- sase_tool_e3_e4_landing_criteria__cld.md
- sase_tool_e3_e4_landing_criteria__mus.md
- sase_tool_e3_e4_landing_criteria__gem.md
