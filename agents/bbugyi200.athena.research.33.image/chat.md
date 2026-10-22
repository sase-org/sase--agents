# Chat History - ace-run (research.33.image)

- **TIMESTAMP:** 2026-10-01 03:40:26 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.33.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_025457.md`

## Prompt

%id(image, clan=research.33) %m:@image
%wait:research.33.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:848051c4a66d28ad8e587d37f6156246`

- **Node:** `agent-delta:20261001025502:de3fbd3957e9368a`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261001025502:de3fbd3957e9368a.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.33, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you critique
sase against the standards / best practices / learnings described in
https://openai.com/index/harness-engineering/? End your analysis with a set of
actionable takeaways (i.e. some advice on how I could improve sase).]]) %id:research.33.final %m:@xlarge
%wait:research.33.cdx %wait:research.33.cld %wait:research.33.grk %wait:research.33.mus %wait:research.33.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you critique
sase against the standards / best practices / learnings described in
https://openai.com/index/harness-engineering/? End your analysis with a set of
actionable takeaways (i.e. some advice on how I could improve sase).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.33.cdx`, `research.33.cld`, `research.33.grk`, `research.33.mus`, `research.33.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.33.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.33.linker`, can find it:

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

I've read the cdx report and am reading the other four reports before doing my own verification research.

I've read all five reports and the article itself. Now I'm checking the claims where the reports disagree against the sase repo.

Confirmed several disputed facts so far (toobig split share, routine config location, AGENTS.md size). Still checking the mentor config, landing path, and verification rules.

Found something no researcher reported: the ToolRun ledger shows `check` failing on the vast majority of runs. Drilling into that now.

Confirmed `sase screenshot` captures the primary checkout's editable install, not the agent's workspace. Checking architecture and docs-drift claims next.

Quantifying how often failures go unowned and how many agents each master breakage hits.

I've verified the key disputed claims and found new evidence from the ToolRun ledger. Now organizing the research directory and writing the consolidated report.

Now registering the consolidated report as an artifact.

I've written and registered the consolidated report, merging all five researcher reports with my own checks against the repo. Its headline finding is new: none of the five researchers looked at the ToolRun ledger, and it changes which gap matters most.

**What the ledger shows.** Over the last 7 days on athena, `check` ran 1,084 times and exited 0 only 31 times. That is 3.6% of the runs that finished.
- There are more than 1,000 distinct failure patterns (the query capped at 1,000), and none has an owner.
- 123 of them were hit by 10 or more different agents. Examples: one lint failure hit 66 agents over 17.5 hours, and one test stayed red across 36 agents for 105 hours.
- About 52.5 agent-hours a week went to killed, timed-out or repeated `check` runs. 185 runs were killed at the provider's time limit.
- `ci_watch` only notifies you; it never launches a repair agent. Feature work is pushed straight to master (0 merge commits in 30 days), no reviewer agent is configured, and an `unverified` landing is not blocked.

The article's "corrections are cheap, waiting is expensive" assumes someone actually makes the correction. SASE built the part that classifies failures but not the part that fixes them.

**Other confirmed gaps**
- **File-size limit enforced after the fact.** 341 of 1,897 commits (18%) in the last 30 days are cleanup agents splitting files that grew too big.
- **No checked architecture.** Nothing enforces which Python packages may import which, `docs/development.md` admits a large import cycle, and the Rust-core boundary exists only as an instruction.
- **Screenshots show the wrong code.** `sase screenshot` relaunches the primary checkout's install, not the agent's workspace, against your real `~/.sase` state.
- **Instruction files too big.** The always-loaded `AGENTS.md` is 283 lines, about 4.3k tokens, and 57% of it is lists of decisions, glossary terms and task types. The home-level `CLAUDE.md` repeats about 1k tokens of the same sections.
- **Key routines live off-repo.** `toobig_split`, `refresh_docs` and `ci_watch` are in machine-local config, so agents can't read them.

**Disagreements resolved.** Several of `__gem`'s claims didn't hold up (a 330-line `AGENTS.md` costing "tens of thousands" of tokens, a human bottleneck on every change, single-turn agents preventing quick fix loops). `__mus` was wrong that there is no recurring doc-updating agent, and overstated how well layering is enforced. Section 7 of the report lists each verdict with its evidence.

**If you do only three things**
1. **Make master green and keep it green.** Give every failure hit by several agents exactly one owner, either a bounded repair agent or an owned bead. Then refuse landings that add *new* failures only, following your `guarded-recipes` precedent.
2. **Move rules into the authoring agent's check.** Add a size check that fails only when this diff pushes a file over the limit, plus declared, checked package-layering rules (import-linter or tach).
3. **Add a bounded agent review loop on risky landings** (epic phases, large diffs, core paths), capped at two rounds and escalating through a gate.

Cheap wins alongside those: cut the always-loaded instructions to about 2k tokens with a budget check, and move the project routines into `sase/sase.yml`.

The ledger figures cover only athena for the last 7 days. "Failed" includes runs that failed only on old, already-known problems, because triage deliberately never changes exit codes.

The five reports are now under `202610/openai_harness_engineering_vs_sase/` with the summary beside them. The host will commit the research repo changes after this turn.

Files are in `202610/openai_harness_engineering_vs_sase/`:
- openai_harness_engineering_vs_sase__final.md (artifact `file:explicit:f67960e8b22fd861987d6ac7`)

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

The infographic illustrating the main findings and takeaways from the research report has been generated, saved, and registered.

### Output Details
- **File:** [openai_harness_engineering_vs_sase_infographic.png](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/openai_harness_engineering_vs_sase/openai_harness_engineering_vs_sase_infographic.png)
- **Dimensions:** 848 × 1264 PNG
- **Artifact Reference:** `file:explicit:61f7cd96b99891c14666c023` (`research:202610/openai_harness_engineering_vs_sase/openai_harness_engineering_vs_sase_infographic.png`)
- **Collision Check:** Confirmed `openai_harness_engineering_vs_sase_infographic.png` did not previously exist; created cleanly without overwrite.

---

### Key Points Illustrated in the Infographic

1. **The Core Architectural Contrast**
   - **OpenAI:** Fast iteration, self-correcting fleets, minimal blocking gates backed by cheap and fast corrections.
   - **SASE:** Deep outer control plane (numbered workspaces, host-owned completion, triage receipts, progressive disclosure), but with a broken closure loop at landing.

2. **The Unowned Master Crisis (The ToolRun Ledger Evidence)**
   - **3.6% Check Pass Rate:** 31 of 860 settled runs passed over 7 days.
   - **123 Shared Red Signatures:** Hit by 10+ distinct agents without an assigned owner (some persisting red for 100+ hours).
   - **52.5 Hours/Week Wasted:** Burned on provider ceiling timeouts and redundant test cycles.
   - **18% of Commits Are File Splits:** 341 of 1,897 commits spent on retroactive `toobig` file splitting.

3. **Key Architectural Gaps**
   - **Landing Path & Ownership:** Master pushes bypass review and gates; triage classifies failures into `KNOWN`/`NEW` but nothing fixes them.
   - **Invariants Enforced Late:** Taste rules (size, layering) enforced post-merge or described purely in prose instructions.
   - **Inner Loop Friction:** p90 test latency stretches to 27–40 minutes, causing provider ceiling kills.
   - **Observability Mismatch:** `sase screenshot` relaunches against the primary checkout's editable install rather than the agent workspace diff.

4. **Actionable Recommendations (Prioritized)**
   - **Step 1 (Immediate): Make & Keep Master Green:** Assign owners (bounded repair agents or `ci` beads) to red signatures; gate landing against *new* breakages only.
   - **Step 2: In-Loop Invariants:** Diff-aware size ratchets and declared import layering in the authoring check.
   - **Step 3: Bounded Agent-to-Agent Review:** Multi-turn mentor agents reviewing risky diffs before landing.
