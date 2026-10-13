# Chat History - ace-run (research.4c.image)

- **TIMESTAMP:** 2026-10-13 10:43:16 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.4c.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_090356.md`

## Prompt

%id(image, clan=research.4c) %m:gpt-6-astra
%wait:research.4c.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:25d72e8c3d624cedf346e5c6fd2c8a92`

- **Node:** `agent-delta:20261013090402:8e70f3929ab126dc`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261013090402:8e70f3929ab126dc.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.4c, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] It
is taking a very long time to startup sase's TUI on my apollo machine. Can you do help
me profile that machine and sase's startup? End your analysis with a ranked list of
changes you think I should consider making in order to improve the TUI's startup on that
machine (or in general).]]) %id:research.4c.final %m:@xlarge
%wait:research.4c.cdx %wait:research.4c.cld %wait:research.4c.grk %wait:research.4c.mus %wait:research.4c.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

It
is taking a very long time to startup sase's TUI on my apollo machine. Can you do help
me profile that machine and sase's startup? End your analysis with a ranked list of
changes you think I should consider making in order to improve the TUI's startup on that
machine (or in general).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.4c.cdx`, `research.4c.cld`, `research.4c.grk`, `research.4c.mus`, `research.4c.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4c.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4c.linker`, can find it:

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

Read all five reports. They agree on the main story but disagree on a few numbers, and one researcher never touched apollo. Next I'll run my own checks on apollo to settle those disagreements.

Confirmed the plugin-registry bug in the source. Next I'm timing the prompt-catalog build on apollo without a profiler attached, to settle whether that cost is CPU or I/O.

Probes are copied to apollo. Now running the catalog build alternately with the current code and with a memoized plugin registry, two runs each.

The plugin-registry fix holds up without a profiler: the catalog build drops from about 8.4 s to 1.3 s, and the work is CPU-bound. Now timing the Patch relation-index build.

First pair at load ~21: unmodified 48.6 s to Agents-ready vs. 11.2 s with the combined fixes. Checking the harness cleaned up after itself, then running three more interleaved pairs.

Four interleaved pairs at load 21–29: unmodified averaged 42 s (27–61 s) and the combined-fix variant 12.0 s (11.2–13.8 s). Now checking where the remaining ~11 s goes in a fix run.

Narrowing the trace summary to spans that ran before Agents became ready.

Found a new bug no researcher reported: 20 copies of the ToolRun glance refresh all started within 0.1 s of Agents-ready. Checking whether the same pile-up appears in the other runs.

I have enough evidence. Writing the consolidated report.

Report written. Registering it as a durable artifact for the linker agent.

Registered (`file:explicit:6105f405e152b30146eb6ca8`). Submitting the final declaration.

The consolidated report is written and registered for the linker as `research:202610/apollo_tui_startup_slowness/apollo_tui_startup_slowness__final.md`. All five researcher reports are in that folder with their original suffixes, and the research-repo commit has been declared for the host to make.

**Why startup is slow on apollo:** the TUI appears after about 5 s; the wait is for the Agents list after that. The loader that fills it takes only 1.5–3.9 s when run alone on apollo. Inside the TUI it gets starved by other work the TUI starts itself:
- **A 3-second timer** starts every background task at once, even if Agents hasn't loaded yet. That includes rebuilding the app-wide link index (7.5–8.5 s of CPU) and the prompt catalog (8.3 s, mostly re-reading plugin metadata 624 times because of a cache bug).
- **The Patch relation index** (2.2–2.4 s per build) is rebuilt on every file change even though its tab is hidden, up to 8 times before Agents loads.
- **Refresh ticks** keep running during startup, so a slow startup gets more of them and slows down further.
- **Python's global interpreter lock (GIL)** turns this into minutes. In one slow run, a database read that takes 0.06 s alone took **47 s**, because the loader had to wait its turn for the lock after every row.
- **Apollo makes it worse:** it is 2–3× slower per thread than athena, runs Python 3.12, and agent test runs can use 14 of its 16 CPUs.

**My own checks on apollo:**
- **All three main fixes together** (cache plugin metadata, skip the hidden relation index, hold background work until Agents is ready) took Agents-ready from **42.2 s to 12.0 s** on average, over four alternating runs each at load 21–29. The large swings between runs disappeared. The fixes were temporary patches inside throwaway TUI instances; nothing on apollo was changed.
- **Some reports overstated costs:** two put the prompt catalog at about 20 s, but measured without a profiler it is 8.3 s, and the fix cuts that 6.5×.
- **Ruled out:** disk speed, memory, and the gateway. The gateway was healthy at both checks today.
- **A new bug:** a background refresh (the ToolRun glance) piles up copies of itself during a long startup. In one run, 20 copies all fired at once the moment Agents appeared. I saw it in 1 of 4 unmodified runs.
- **The test-runner setting** that lets two concurrent agent test runs take 14 of the 16 CPUs is `SASE_TEST_GATE_SLOTS`.

**Ranked changes:**
1. Stop rebuilding the Patch relation index for a hidden tab, and never build it on the UI thread.
2. Start background work when Agents is ready, not on a 3-second timer, and skip refresh ticks until startup finishes.
3. Fix the plugin-metadata cache. It's about 20 lines, the cheapest win, and it also speeds up CLI commands that load macros.
4. On apollo, set `SASE_TEST_GATE_SLOTS` to about 6–8, run agent tests and Rust builds at lower priority, and send heavy agents to athena. No code needed.
5. Move the two link-index builds into `sase-core` as one batched call.
6. Fix the piling-up ToolRun glance refresh.
7. Remove the lock-heavy loops from the Agents loader. For example, every read of the dismissed index currently also writes to it.
8. Trim slow imports, including an unconditional debug-capture import on the UI thread. Then move apollo to Python 3.14; that reinstall is yours to run.
9. Add telemetry that shows directly where a slow startup spent its time.
10. Fix slowness after startup: refresh polling, `sase tool wait` polling, garbage-collection pauses, and gateway limits.
11. A faster droplet, only after the software fixes.

Items 1–3 and 6 should get you close to the 12 s result, about 15–18 s including startup imports. Getting near athena's ~5 s needs items 4, 5, 7 and 8 as well. My probe scripts and run data are in `/tmp/sase-lead-probe-vwkeva/` on apollo and can be deleted.

---

%macros_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

I’ll use the imagegen skill to turn the report’s findings into an infographic and save it beside the report, checking for an existing file first.

I’m using the SASE repository and audited-reading skills to open the source report. The graphic will focus on the startup bottlenecks, the measured improvement, and the ranked fixes.

The destination is available. I’ll emphasize the measured improvement—42.2 s to 12.0 s—while clearly noting that these are times from app initialization, from four experimental runs per variant. I’ll also show how background work delays the Agents loader and summarize the fixes in the report’s ranked order.

The infographic is generated and includes all eleven ranked recommendations. I’m refining the chart proportions and the feedback-loop arrow, then I’ll save the PNG with exclusive creation so an existing file cannot be overwritten.

The PNG is saved beside the report without overwriting anything, and I’ve checked its contents and file integrity. I’m using the SASE finalization skill to submit the repository change for the host to commit.

Created [apollo_tui_startup_slowness_infographic.png](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202610/apollo_tui_startup_slowness/apollo_tui_startup_slowness_infographic.png) beside the report without overwriting anything.

Includes the measured improvement, bottlenecks, and all eleven ranked recommendations. Generated with built-in imagegen; [prompts saved here](/home/bryan/.cache/sase/codex_home/3368318-528a37a934bb4208988c5b89da8ae3f4/generated_images/01a135af-03fc-7862-ad96-4fc088ed020c/apollo_infographic_prompts.txt).
