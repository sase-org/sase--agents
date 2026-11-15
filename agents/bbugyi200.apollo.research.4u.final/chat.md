# Chat History - ace-run (research.4u.final)

- **TIMESTAMP:** 2026-11-15 17:23:09 EST
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.4u.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261115_164459.md`

## Prompt

%clan(research.4u, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] It doesn't seem like agent hijacks are working correctly. See the
~/tmp/screenshots/20261115_164112.png screenshot, which was taken on the apollo machine,
for context. Agent hijacks should work on as many types of sase turns (in as many
states) as possible. I would like to fix this issue and make agent hijacks much more
resiliant / dependable in general.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.4u.final %m:claude-fable-5
%wait:research.4u.cdx %wait:research.4u.cld %wait:research.4u.grk %wait:research.4u.mus %wait:research.4u.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

It doesn't seem like agent hijacks are working correctly. See the
~/tmp/screenshots/20261115_164112.png screenshot, which was taken on the apollo machine,
for context. Agent hijacks should work on as many types of sase turns (in as many
states) as possible. I would like to fix this issue and make agent hijacks much more
resiliant / dependable in general.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

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
   dispatch's `research.4u.cdx`, `research.4u.cld`, `research.4u.grk`, `research.4u.mus`, `research.4u.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4u.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4u.linker`, can find it:

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

I'll consolidate the five researchers' reports on agent hijack reliability and add my own research. Let me start by looking at the screenshot and opening the research repo.

Research repo is open. Now let me read each of the five registered reports through their canonical research references.

Two reports in — cdx and cld are detailed and largely agree. Reading the remaining three now.

Four down, one to go. Reading the gem report now.

Reports are in place. Now let me draft and render the consolidated report's one figure — the per-state hijack decision model — using the skill's render recipe.

The CLI works with the no-sandbox fallback, but the figure is too wide (fit 43.8%). Restructuring to a left-to-right layout with tighter labels.

Closer (64.1%) but still too wide. Tightening labels and wrapping width.

72.4% — just under the floor. One more small trim (this is my second revision, per the skill's limit).

Report written. Now registering it as a durable artifact for the linker agent.

Artifact registered (`file:explicit:da0ced694f50cb61af3a3c79`). Quick final verification of the layout, then I'll close out the turn.

Layout is correct. Now submitting the final declaration before my closing summary.

Consolidation complete. The final report is at `202611/agent_hijack_dependability/agent_hijack_dependability__final.md` in the research repo, registered as `file:explicit:da0ced694f50cb61af3a3c79`, with all five researcher reports moved alongside it under the `agent_hijack_dependability` stem. The final declaration was accepted; the host will commit the research repo after this turn.

**What the consolidated research found:**

- **Hijack is broken for every real agent on apollo, not just the screenshot's.** No hijack has ever succeeded there. Five stacked defects block the path, each sufficient alone: the TUI predicate requires `AgentType.RUNNING` but every real launch loads as `WORKFLOW`; session rows resolve to the wrong member; the `runner_capabilities: ["hijack"]` stamp is wiped moments after bootstrap by the directive-extraction rebuild (so Rust refuses everything with a misleading "launched before hijack support"); recovery reads model facts from keys runners never write (so even a successful stop would strand Continue/Escalate); and the refusal reason is hidden behind one generic toast. I verified the predicate, the capability wipe, and the key mismatch directly in the code; two researchers confirmed them against live agents.
- **The screenshot hit the hardest case on top of that**: `tailnet-t.10` was crossing a turn boundary — `--5` finalizing, `--mon-3` a live monitor — both states v1 refuses by design. (One researcher misread the selected row as WAITING; the image shows RUNNING, and I resolved that in the report.)
- **The tests passed because each one hand-fakes the exact input that's broken in production.** There's no canary through the real launch pipeline.

**Critique of your plan:** the direction is right, but "as many types/states as possible" should be amended three ways — all five researchers converged on this: (1) fix the basic path first, since widening a pipeline that has never completed one hijack multiplies untested surface; (2) make the unit of hijack the **agent/session**, with the backend resolving the live occupying turn at execution time; (3) replace "every state" with **every (kind × state) pair gets exactly one defined decision** — stop now, *latch* to the next safe hand-off (finalizers, staged handoffs, settling gates), redirect to a better operation, or refuse with a specific reason.

**Recommended solution** (detailed in the report): Phase 0 makes v1 real (the five fixes, transactional hardening, a real-pipeline canary, `--explain`); Phase 1 adds session takeover with a durable latch stored on the workspace claim (sase-core wire v2); Phase 2 adds the monitor adapter (your screenshot's case) and WAITING/QUEUED coverage via a processless stop branch; Phase 3 hardens with a boundary chaos test. Pending-gate hijack, remote execution, and home-mode custody are deferred; no rewrite — the ledger/custody/recovery design is sound and the defects are integration glue.

One process note: I drafted a Mermaid decision-model figure but it stayed below the PDF fit floor after the allowed revisions, so per the figure rules I dropped it — the per-state decision table in the report carries the same content.
