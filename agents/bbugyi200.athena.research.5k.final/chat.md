# Chat History - ace-run (research.5k.final)

- **TIMESTAMP:** 2026-10-30 17:34:55 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5k.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261030_164448.md`

## Prompt

%clan(research.5k, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The TUI has slowed down again lately. Can you do some research with the goal of helping
me speed things up again? Make sure you prioritize good architecture choices and
reliability (don't break anything). End your analysis with a recommended solution.]]) %id:research.5k.final %m:@xlarge
%wait:research.5k.cdx %wait:research.5k.cld %wait:research.5k.grk %wait:research.5k.mus %wait:research.5k.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The TUI has slowed down again lately. Can you do some research with the goal of helping
me speed things up again? Make sure you prioritize good architecture choices and
reliability (don't break anything). End your analysis with a recommended solution.

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
   dispatch's `research.5k.cdx`, `research.5k.cld`, `research.5k.grk`, `research.5k.mus`, `research.5k.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.5k.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.5k.linker`, can find it:

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

Reading the five reports is done. Next I'm checking the claims they disagree on in the code and live logs.

The lock-busy fallback scan is confirmed in the code. Now checking the stranded collector's cadence and the live load logs.

The live load log still shows 172 of 204 slow full loads with a 15 s+ index stage, which matches the fallback scan. Next I'm sampling the live TUI's thread stacks to see who holds the lock.

I'm now re-running the stranded-collector query myself to check the reported 127 s vs 1.78 s gap, which is the main claim behind the fix.

I'm fixing the report's one diagram: its first render was too wide for the PDF page, so I'm tightening the layout and re-rendering.

Figure passes (80% fit). Writing the consolidated report now.

Both references exist. Registering the consolidated report as a durable snapshot.

Registered. Submitting the final declaration.

The TUI has slowed down because of a new background bead check, not because of rendering or the GC settings. Each Agents refresh then falls back to a 24–30 s, multi-GB filesystem scan, and the resulting memory churn makes every garbage collection pause the UI for seconds. The consolidated report merging all five reports with my own checks is written and registered.

**Root cause.** The stranded-work collector, added 23–26 October, runs one artifact-index query per candidate bead. There are 218 candidates, so each report takes about 113 s. Every query holds a process-wide index lock. The report expires after 15 s and is also forced on every beads-watcher event, so the lock is busy most of the time. The Agents loader waits only 50 ms for that lock, then runs the filesystem scan instead of its normal 0.35 s index read.

**Checked against the live TUI:**
- **Scans:** 172 of 204 slow full loads (84%) show the scan signature, and that rate stays at 79–92% every hour around the clock.
- **Batching:** one batched query does the collector's work in 1.5 s and returned the same records for all 12 assignees I compared.
- **Stack samples:** the collector was mid-query in 7 of 15 readable samples, taken during a quiet period.
- **Effect:** hitches went from 3.6% to about 12–13% of the time, and GC from 5.7% to about 10–11%. Memory swings between 4 and 16 GB, with up to 7.9 GB swapped. The GC pauses are worse because the GC policy runs full collections on the UI's 1-second timer.

**Disputed claims rejected:**
- Lowering the GC threshold, or moving garbage collection to a worker thread: a collection pauses every thread anyway.
- Adding a new single-flight loader: refresh coalescing already exists.
- A "duplicate watcher thread" leak: the two watcher threads are by design.
- The large JSON registry files and the Textual render-cache cycles are real but secondary.

**Recommended fix, in small steps you can revert one at a time:**
1. **Python only, should restore most of the speed:**
   - Batch the stranded collector into one query per project.
   - When the lock is busy, show the last good snapshot marked incomplete and retry, instead of scanning the filesystem.
   - Slow the stranded refresh to about every 60 s.
   - Log the load source and fallback reason, so a fallback shows up directly in the load log.
2. **Rust core and UI thread:**
   - Do the session lookup in sase-core SQL, with a new `agent_name` index.
   - Fix the smaller UI-thread costs, starting with capacity updates that rebuild panel titles needlessly.
   - Stop the capacity feed's 17 s directory walks.
3. **Then re-measure** on a freshly restarted TUI before touching GC policy (the open `sase-1nc` work). After that, only consider moving full collections to long idle windows.

Restarting the TUI today brings temporary relief, but the collector starts again immediately.

I didn't file any beads. None of the existing ones cover this, so I can file tasks or plan an epic once you approve the direction.

The five reports and the final report are in `202610/tui_slowdown_index_lock_fallback_scans/` in the research repo. The final report is registered as `file:explicit:8dc210255fb288d0091b236b` for the linker, and the commit is declared for the host.
