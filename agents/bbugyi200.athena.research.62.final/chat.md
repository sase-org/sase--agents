# Chat History - ace-run (research.62.final)

- **TIMESTAMP:** 2026-11-16 06:58:38 EST
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.62.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261116_061336.md`

## Prompt

%clan(research.62, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The TUI has slowed down quite a bit lately (including startup). I would like to dig into
this and speed up sase's TUI significantly.

Can you do some research with the goal of helping me decide the best/safest way to
optimize sase's TUI? Feel free to recommend extra instrumentation but only if truly
necessary to diagnose the TUI's performance. End your analysis with a recommended
solution.]]) %id:research.62.final %m:claude-fable-5
%wait:research.62.cdx %wait:research.62.cld %wait:research.62.grk %wait:research.62.mus %wait:research.62.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The TUI has slowed down quite a bit lately (including startup). I would like to dig into
this and speed up sase's TUI significantly.

Can you do some research with the goal of helping me decide the best/safest way to
optimize sase's TUI? Feel free to recommend extra instrumentation but only if truly
necessary to diagnose the TUI's performance. End your analysis with a recommended
solution.

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
   dispatch's `research.62.cdx`, `research.62.cld`, `research.62.grk`, `research.62.mus`, `research.62.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.62.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.62.linker`, can find it:

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

I'll start by opening the research repo, then read the five registered reports.

All five reports are present, one per suffix. Now I'll read each through its canonical research reference.

My verification is complete. Now I'll set up the consolidated directory, move the five reports (plus grk's figure assets so its relative image links keep working), and write the final report.

All reports are in place. Now writing the consolidated final report.

Now registering the consolidated report as a durable artifact snapshot for the linker agent.

The report is registered (`ref: file:explicit:e29d7cafdcd168f6fe697884`). Now closing out the turn with the final declaration.

Done. The consolidated report is written, registered, and declared for commit.

## What the research found (TL;DR)

The TUI didn't slow down for one reason — **three problems are stacked**, and all five researchers' evidence plus my own verification at HEAD (`0731d06c5a`) converges on them:

1. **Hijack-decision storm (acute, since `d26b581253`, Nov 16).** Every Agents footer/selection refresh schedules an unbounded background `find_named_agent` archive scan (full `scan_agent_artifacts` + a fallback over 65,875 dismissed-bundle JSONs). The cache key embeds the roster generation, which changes every refresh, and finished results are dropped when it moves — so the cache never warms and scans pile up. py-spy caught 31 of 45 threads in this stack; 9 concurrent scans × ~23.1k wire records exactly matches the 207,837-record GC census and the 20–35 GB RSS blow-ups. **I verified the mechanism is fully intact at HEAD** — the two newer hijack commits didn't touch it — and the currently running TUI (restarted ~13 min ago, 2.8 GB and climbing) is exposed.
2. **Trust/config checkout-root defect (since Nov 12).** `_checkout_root_for_local_path` resolves `<repo>/sase` instead of `<repo>`, defeating the fast identity match, so `AceApp.__init__` does ~121 full config merges + ~100 `git remote` subprocesses — construction went 1.0 s → 5.2–6.3 s. Two researchers independently patched it in-process: 6.9 s → 1.9 s. It's also a live correctness bug: trust acknowledgments and enforcement compute different keys (which is why every `sase` command in this session printed the "skipped (no-acknowledgment)" warning).
3. **Chronic heap + per-load recompute.** Fat wire graphs, full-log in-memory caches, and uncached per-agent config/alias lookups (one alias lookup ran 303× per load) grew with the archive; gen-2 GC pauses of ~3 s cause 95% of hitches, and `agents_ready` drifted ~5 s → ~11.6 s over months.

One important **correction to the grk report**: its proposed marker-true live predicate is unsafe as written — I verified `has_running_marker` is 0 for **all 23,133 index rows** (the column is never populated), so flipping the predicate would empty the inbox. Terminalize stale rows in index maintenance first.

## Recommended solution

Staged surgical fixes, no rewrite, no new diagnostic instrumentation (existing telemetry found everything): **hijack-storm hotfix today** (cheap-gate, identity-keyed single-flight cache, one bounded worker, row-local `deps` finder) → **trust-path memoization now + root-ownership fix with compat keys via the trust owners** → **loader memos** → **startup deferrals** (provider discovery post-paint, lazy imports, monitor_reconcile/AXE off the critical path) → **heap diet** (slim list DTO in sase-core, one-generation snapshot cache, bounded log caches, with `sase-1sl.4`) → interaction polish last. Projected: ~14 s → ~6–7 s to a usable Agents list from the first three stages alone, plus the memory catastrophe gone. The one instrumentation addition worth making is a default-executor saturation gauge in the existing heartbeat — it would have named the storm in minutes. Interim: quit the TUI when idle, or gate a pin to `082f2bc705`.

## Deliverables

- Final report: `202611/tui_hijack_storm_trust_root_and_heap/tui_hijack_storm_trust_root_and_heap__final.md`, registered as `file:explicit:e29d7cafdcd168f6fe697884` for the linker.
- All five swarm reports moved beside it with their suffixes preserved (plus grk's Mermaid figure assets so its image links keep working); the research-repo commit is declared and lands when this turn ends.
- No task beads filed (cld deferred that to the synthesis, and the work items should come once from whichever plan you adopt) — but the storm hotfix deserves planning immediately, coordinated with the in-progress `sase-1t2` hijack epic.
