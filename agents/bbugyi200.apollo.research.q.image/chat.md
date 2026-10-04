# Chat History - ace-run (research.q.image)

- **TIMESTAMP:** 2026-09-29 15:39:17 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.q.image
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260929_145445.md`

## Prompt

%id(image, clan=research.q) %model:@image
%wait:research.q.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:eb3d421827dcc7d7fa4f3b37e2d6f46a`

- **Node:** `agent-delta:20260929145451:63937b543f1e836a`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260929145451:63937b543f1e836a.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.q, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm pretty sure the
E1-E5 epics described in the sase_tool_epic_roadmap.md file in the research sidecar repo
are complete. I'm now considering whether or not to move forward with E6-E8. Can you
help me re-evaluate the worth of these epics? What new functionality do these
immediately give me and/or what functionality might it unlock in the future? End your
analysis with a recommendation.]]) %id:research.q.final %m:@xlarge
%wait:research.q.cdx %wait:research.q.cld %wait:research.q.grk %wait:research.q.mus %wait:research.q.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm pretty sure the
E1-E5 epics described in the sase_tool_epic_roadmap.md file in the research sidecar repo
are complete. I'm now considering whether or not to move forward with E6-E8. Can you
help me re-evaluate the worth of these epics? What new functionality do these
immediately give me and/or what functionality might it unlock in the future? End your
analysis with a recommendation.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.q.cdx`, `research.q.cld`, `research.q.grk`, `research.q.mus`, `research.q.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

### Assistant

I've found all five reports in the research checkout. Next I'll read each one through `sase artifact read`.

I'm writing a read-only query against athena's ToolRun store. It will re-check the Muse kill counts and split the concurrency slowdown into pytest token waiting versus other causes.

Next I'm checking whether the slower scoped test stage under concurrency just reflects larger test selections, a confound that would weaken the case for E7.

Now checking the `runner_capacity` schema version: the roadmap and two reports say v5, cdx says v7.

`runner_capacity` is now schema v7, as cdx said. Next I'll check whether any E6–E8 beads or plans already exist, and the state of the in-flight blockers.

Reports are moved. Before writing, I'm checking one more claim: whether a handed-off monitor keeps its agent's runner claim.

That claim checks out. Writing the consolidated report now.

Tidying two cells in the concurrency table so the buckets are labelled consistently.

The layout is complete. Primary workspace is clean; only the research sidecar changed. Now submitting the final declaration.

My recommendation: don't start E6–E8 as the roadmap scoped them. Build two pieces of E6 in a different form now, and hold the rest until the data justifies it. The consolidated report is at `202609/sase_tool_e6_e8_go_no_go/sase_tool_e6_e8_go_no_go.md` in the research repo, with the five researcher reports moved into the same folder.

**Your premise is almost true.** E1, E2, E3 and E5 are closed. E4 (`sase-1ah`) is still in progress: all its phases are closed, but it still needs a live prepared-completion run on athena, or you can record that step as an accepted limitation. The roadmap's E4 promise that a second `check` returns instantly also did not ship, because receipts are now proof only and never skip a run.

**Where the researchers agreed and disagreed:** all five say E8 should wait, and four of five say E7 should wait. Four said to build E6 advisory-first; one (cld) said its routing feature works better without forecasts. I re-ran cld's key measurements against athena's store and they reproduce exactly, so I sided with cld.

| Epic | What it gives you right away | What it enables later | Worth today |
| --- | --- | --- | --- |
| **E6** Forecasts and automatic routing | `sase tool stats`, `run -E`, automatic inline-vs-hand-off, overdue/stalled states, automatic timeouts | ETA chips in the TUI, spotting when durations regress, cost per agent/bead, the pricing E7 needs | **Split it.** Routing matters most but is better done reactively; `stats` is cheap and high value; forecasts are low to moderate |
| **E7** Local admission | Heavy runs queue with an expected start; pytest workers and agents share one budget | Backfill, priorities, the local numbers E8 would publish | **Low now.** The main cost of running checks concurrently is being handled, not ignored (see below) |
| **E8** Fleet surfaces | Per-machine capacity meters, "why is apollo busy?", staged rollout across machines | Choosing which machine runs a tool, if you ever want that | **Very low now.** There is nothing from E7 to publish, and athena runs 87% of all tool runs |

**What the data shows:**
- **The biggest measured cost is Muse killing inline `check` runs at 540 s.** On athena that happened 160 times, costing about 24 hours of compute. 57 of those runs were immediately rerun by the same agent, and the daily count rose from 1 to 47 over the week. Apollo had 26 more.
- **Routing also fails the other way.** 38% of `check` runs that agents handed off on athena finished in under 5 minutes, so they paid for a hand-off they didn't need.
- **Forecasts can't route well yet.** A 10th-to-90th percentile band covers 75% of runs, but the typical band is 18.6 times wide (roughly 47 seconds to 15 minutes).
- **Why the reports disagreed on E7.** Pytest already shares a host-wide worker pool: at most 32 tokens on athena, and memory currently limits it to about 24. Runs overlapping each other really are slower (cdx's point), but that is the pool splitting a fixed budget, which is why CPU pressure stays near zero (cld's point). E7 would mostly make that wait visible; it wouldn't create capacity. The sample sizes behind this are small, and grant width isn't recorded, so treat it as consistent with the data rather than proven.

**Recommended order:**
1. Close or waive E4.
2. Fix `sase-1bo` (small): stage rows are never pruned, and athena's tool store grows about 30 MB/day.
3. Build one "reactive routing" epic from the two existing ready beads, `sase-17e` and `sase-17g`. Every run starts inline; a run still going near the provider's time limit moves into a monitor without restarting. This removes both routing failures without any forecast.
4. Build a small read-only `sase tool stats` unit. It should record pytest grant width, CPU seconds and peak memory per run, which any future E7 would need.
5. Park the rest of E6, all of E7 and all of E8, each with a measurable condition for reconsidering. Those conditions are written out in the report.

E8 is only worth building if you want tools to run on whichever machine has room. Also keep an eye on receipt reuse ("E4b"): athena's repeated runs already pass its threshold for one week. Re-measure after step 3, because killed-then-rerun runs may be inflating that number.

I didn't change any beads, including adding the Muse-kill evidence to `sase-17e`/`sase-17g`; tell me if you want that recorded. The research changes are declared for commit.

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<source-stem>_infographic.png` in the same directory.


## Response

An infographic illustrating the core findings, telemetry evidence, epic evaluations, and actionable recommendations from [`sase_tool_e6_e8_go_no_go.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/sase_tool_e6_e8_go_no_go/sase_tool_e6_e8_go_no_go.md) has been generated and saved:

- **Infographic Path:** [`sase_tool_e6_e8_go_no_go_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/sase_tool_e6_e8_go_no_go/sase_tool_e6_e8_go_no_go_infographic.png)  
  *(1920×1080 high-resolution PNG, dark technical engineering dashboard theme)*

---

### Core Structure & Findings Illustrated

1. **Executive Verdict & Summary KPIs**
   - **Verdict:** Do not launch E6–E8 as scoped. Split E6 into reactive routing (`sase-17e` + `sase-17g`) and read-only `sase tool stats`; hold E7 (admission) and E8 (fleet surfaces) behind explicit measurable triggers.
   - **160 Muse Ceiling Kills (~24h Lost):** Muse's 540s command timeout killed 160 inline checks on athena and 26 on apollo (100% Muse/unattributed); 57 were immediately restarted by the same agent within 30 minutes. Daily kill counts escalated from 1 to 47.
   - **38% Short Hand-offs:** 38% of handed-off runs finished in under 5 minutes (15% in <2 min), paying unnecessary agent turn boundary and follow-up prompt costs.
   - **18.6× Forecast Band Uncertainty:** Median p10–p90 spread spans 47s to 15 min; 94% fail rate means models predict time-to-first-failure rather than duration.
   - **≤ 0.4% CPU PSI Under Load:** Pytest worker-token pool already governs heavy test stages; concurrency narrows token grants rather than thrashing host CPUs.

2. **Empirical Ground Truth & Contention Paradox Reconciled**
   - **The Dual Routing Breakdown:** Visualizes the ceiling kill loop versus premature hand-off waste, contrasted with the **Reactive Escalation** fix (`--detach` + `monitor start --join` at the ceiling margin without restarting).
   - **Pytest Worker Pool (`tests/_suite_gate*.py`):** Explains why cdx observed 2–2.6× elapsed duration inflation while cld observed flat CPU PSI (≤ 0.4%). Memory limits the pool to ~24 tokens on athena; overlapping runs share tokens via smaller grants, lengthening execution cleanly without thrashing. Pre-run queuing merely moves the wait.

3. **Epic Evaluation & Strategic Matrix**
   - **E6 (Forecasts & Auto-Routing) &rarr; [SPLIT IT]:** Deliver routing reactively via `sase-17e`/`17g`; ship a lightweight read-only `sase tool stats` unit; park wide-band quantile forecasting.
   - **E7 (Local Tool Capacity Admission) &rarr; [HOLD]:** Low value today as pytest is already pool-rationed; avoids introducing the first fail-closed scheduler into an intentionally fail-open host.
   - **E8 (Fleet Surfaces & Coordinated Rollout) &rarr; [HOLD / DEFER]:** Athena carries 87% of fleet ToolRuns (Mac has 0); option value only exists if cross-machine placement becomes a product goal.
   - **Consensus & Factual Corrections:** Reconciles the 5 researchers (cdx, cld, grk, mus, gem), corrects root bead status (`sase-1ah` remains IN_PROGRESS), and notes `runner_capacity` schema is at v7.

4. **Actionable 5-Step Order & Reconsider Triggers**
   - **Step 1:** Close E4 (`sase-1ah`) via live athena run or accepted limitation waiver.
   - **Step 2:** Fix `sase-1bo` store row pruning (SQLite growing +30 MB/day).
   - **Step 3:** Ship Reactive Routing epic (`sase-17e` + `sase-17g`) to stop ceiling kills.
   - **Step 4:** Ship read-only `sase tool stats` + demand telemetry (grant width, CPU sec, peak RSS).
   - **Step 5:** Park rest behind written triggers (E6: stage-level band ≤3× & ≥80% cov; E7: mem PSI >10%; E8: remote goal).
   - **Competing Opportunity:** Highlights E4b Receipt Reuse (~5h/wk repeated compute on athena) as a higher-ROI investment than the parked epics.
