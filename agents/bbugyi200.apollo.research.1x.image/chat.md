# Chat History - ace-run (research.1x.image)

- **TIMESTAMP:** 2026-10-17 01:22:47 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.1x.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215631.md`

## Prompt

%id(image, clan=research.1x) %m:gpt-6-astra
%wait:research.1x.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:7dc2e44313db147821b5e7fdb99d1e8f`

- **Node:** `agent-delta:20261016215637:676c39d380f1b21e`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261016215637:676c39d380f1b21e.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.1x, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research with the goal of comparing sase with gascity (see recent
research in the research sidecar repo related to gascity and gastown for context)? In
particular, in what ways is gascity superior to sase? End your analysis with a ranked
list of recommended improvements you think I should consider making to sase based on
your report's findings.]]) %id:research.1x.final %m:@xlarge
%wait:research.1x.cdx %wait:research.1x.cld %wait:research.1x.grk %wait:research.1x.mus %wait:research.1x.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research with the goal of comparing sase with gascity (see recent
research in the research sidecar repo related to gascity and gastown for context)? In
particular, in what ways is gascity superior to sase? End your analysis with a ranked
list of recommended improvements you think I should consider making to sase based on
your report's findings.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.1x.cdx`, `research.1x.cld`, `research.1x.grk`, `research.1x.mus`, `research.1x.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1x.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1x.linker`, can find it:

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

### Assistant

All five reports are present in the research checkout, one per suffix. Next I'll read them, plus the earlier Gas City and Gastown finals.

All five reports are read. They agree on the core gap but disagree on several facts, so I'm now checking those directly against the Gas City and SASE source and live CI data.

Prior work is cross-referenced. One recent SASE commit, "workflow resume recovery", could weaken the reports' "workflows always restart from step 0" claim, so I'm checking it before writing.

Report claims are checked. Two quick SASE spot-checks remain before writing: the global event log format, and how a failed epic phase is handled.

Every claim I plan to use is now checked. Next I'm creating the consolidation directory and moving the five reports into it.

Reports are in place. Now writing the consolidated report.

Report written, and the five inputs are moved under the new stem. Registering the consolidated report as a durable artifact for the linker.

The artifact is registered (`file:explicit:11d20a0cd0a17d5d74c3fb7c`). Submitting the final declaration now. The research repo has changes that need committing.

The consolidated report is written and registered as an artifact. The research repo changes are declared for commit and land when this turn ends.

**Report:** `202610/gascity_advantages_over_sase_and_what_to_borrow/gascity_advantages_over_sase_and_what_to_borrow__final.md`, with the five researcher reports (cdx, cld, grk, mus, gem) moved beside it. The artifact ref is `file:explicit:11d20a0cd0a17d5d74c3fb7c`.

**Where Gas City is better than SASE:**
- **Biggest measured gap: its main branch stays green.** This is how the Gas City repository is run, not a feature of its product. GitHub branch rules plus a merge queue mean nothing lands until it passes. I re-pulled the numbers today:
  - **Gas City:** merge-queue runs passed 37 of 38, and pushes to `main` passed 35 of 35.
  - **SASE:** `master` has no protection rules. Master Gate passed 8 of its last 60 runs and 49 of its last 300.
  - **The failures are spread out:** the 12 newest failed runs hit lint and all eight test shards, not one stuck test.
- **Biggest product gap: the workflow is data that a controller runs.** Gas City's controller runs the checks, retries and fan-outs itself, saves progress to disk, and picks up again after a crash. In SASE:
  - workflows always restart from step 0;
  - a failed epic phase sits parked until you retry it by hand;
  - "done" means the agent said so and the commit passed its checks.
- **Smaller advantages:** cron and event triggers that fire whole workflows, a typed and numbered event log, workflows that fan out over lists produced at runtime, shareable bundles of workflows, 18 harness presets, and dollar cost estimates.
- **Where SASE is ahead:** completion integrity, human approvals and gates, goals and memory, admission control, and lighter operations (no Dolt database server, no tmux).

**Corrections to the five reports, checked against the code:**
- **Retry budgets:** mus and gem said a check that fails for infrastructure reasons doesn't use up a retry attempt. That protection exists only on Gas City's legacy code path. The path that compiled workflows actually use spends the attempt anyway.
- **Gem's errors:** SASE workspaces already share Git objects with the main clone, so they are not full copies. SASE's scheduler has no cron trigger, and `%dispatch` already runs agents on other machines.
- **Stale Gas City docs:** quorum voting was removed, and crash-loop quarantine is never triggered, yet the docs still describe both.

**Ranked recommendations:**
1. **Protect `master` and land through a verified merge queue.** Don't redesign this. A report published today, `merge_queue_fenced_master_and_exact_sha_releases`, already has the plan, and none of the five researchers cited it. Gas City shows the approach works at SASE's commit rate, but the flaky-test fixes in that plan have to come before enforcing it.
2. **Have the host run a verification check after each epic phase,** and launch a new attempt when it fails. Track three outcomes (pass, fail, no verdict) so killed or timed-out checks don't count as failures. Add typed failure handling (park, degrade, or escalate).
3. **Make workflow and epic runs durable and resumable** in `sase-core`, with crash-injection tests as the acceptance bar.
4. **Add a typed, numbered event log,** which also lets the mobile gateway's event stream survive a restart.
5. **Add cron and event triggers to scheduler jobs,** and let jobs launch workflows.
6. **Add a job that keeps epics moving, plus a "why is this waiting?" view.**
7. **Optionally auto-launch ready beads of approved types,** with leases on claimed work.
8. **Add runtime fan-out and a multi-provider review workflow.**
9. **Record usage and estimate dollar costs.**
10. **Package one complete workflow as a plugin** before designing any bundle format.
11. **Add an inbox that agents read at the start of their next turn.**
12. **Add a conformance test suite for providers, then custom API endpoints, then an Agent Client Protocol (ACP) adapter.**
13. **Borrow a few cheap governance habits,** such as "last verified against code" headers on docs.

Items 1–3 need new decision records, including one replacing the merge-queue rejection in `ci-two-speed-split`. I didn't write those; they need to go through `/sase_memory_write`.

---

%macros_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

I’ll read the research report and use the imagegen skill to create an infographic beside it, first checking that the target filename is available.

I’m using the SASE repo and memory-read skills to access the source report through its audited reference.

The filename is available. I’ll center the infographic on Gas City’s durable workflow controller, the report’s CI findings, SASE’s strengths, and the highest-priority improvements. The CI figures will be labeled as an October 2026 snapshot.

The infographic is generated and checked. It includes the comparison, CI caveats, and all 13 ranked recommendations. I’ll now save it under the requested filename without overwriting anything and register it as a SASE artifact.

The 1024 × 1536 PNG is saved beside the report and registered as a durable artifact. I’m using the SASE final skill to declare the new image for the host’s commit step.

Created [gascity_advantages_over_sase_and_what_to_borrow_infographic.png](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202610/gascity_advantages_over_sase_and_what_to_borrow/gascity_advantages_over_sase_and_what_to_borrow_infographic.png) beside the report without overwriting anything.

1024 × 1536 PNG, generated with imagegen. [Generation prompt](/home/bryan/.cache/sase/codex_home/2583317-88ec6302d5ca44b98fe609be137b359b/generated_images/01a14848-4819-7c63-8f13-fbc3cd4400d4/exec-f0a2e595-03a6-4e87-ace6-a5b3060f3570.prompt.txt).

Registered artifact: [file:explicit:3514699b52f31ad6f5253d94](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261016215638/gascity_advantages_over_sase_and_what_to_borrow_infographic-72549daf4ef8.png).
