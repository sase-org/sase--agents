# Chat History - ace-run (research.4k.final)

- **TIMESTAMP:** 2026-11-13 18:13:22 EST
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.4k.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261113_174022.md`

## Prompt

%clan(research.4k, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add support to sase for Google's new Argon and Hydrogen models.

- We should update all model completion surfaces to include these models.
- As a part of this change, we should update the `#research_swarm` macro to use the new
  Hydrogen model instead of the current Gemini model that we use for that macro swarm.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.4k.final %m:claude-fable-5
%wait:research.4k.cdx %wait:research.4k.cld %wait:research.4k.grk %wait:research.4k.mus %wait:research.4k.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to add support to sase for Google's new Argon and Hydrogen models.

- We should update all model completion surfaces to include these models.
- As a part of this change, we should update the `#research_swarm` macro to use the new
  Hydrogen model instead of the current Gemini model that we use for that macro swarm.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

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
   dispatch's `research.4k.cdx`, `research.4k.cld`, `research.4k.grk`, `research.4k.mus`, `research.4k.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4k.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4k.linker`, can find it:

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

I'll start by opening the research repo, then read the five registered reports, do my own research into the sase codebase, and finally merge everything into a consolidated report.

The research repo is open at my workspace checkout. Now I'll read all five registered reports through their canonical references.

Files are in place. Now writing the consolidated report.

Now registering the consolidated report as a durable artifact for the linker agent.

The consolidated report is registered. Now I'll submit the final declaration before closing out.

Consolidation complete. The final report is at `202611/argon_hydrogen_completion_and_swarm/argon_hydrogen_completion_and_swarm__final.md` in the research repo, registered as `file:explicit:1695dbb95ad247786f3bb914` for the linker, with all five researcher reports (and grk's figures) moved alongside it. The final declaration was accepted; the host will commit the research repo after this turn.

**What the consolidated report recommends** — two commits in two repos:

1. **sase** (`src/sase/llm_provider/models.yml` + small edits): add `gemini-4-hydrogen-{xhigh,high,medium,low}` after the Argon block with `hydrogen4x/h/m/l` aliases and **no advisory**; rewrite the stale Argon "Ultra-only" advisory to "needs Google AI Pro or Ultra"; move the **live-broken** agy tier defaults from 3.7 Flash to 3.8 Flash; add `"hydrogen"` to `short_model_name`; regenerate docs and update ~8 pinned test files.
2. **sase-research-artifacts**: change `#research_swarm`'s `gemini_model` default to `agy/gemini-4-hydrogen-xhigh` (matching every other researcher's top-rung effort), update the `@image` pool's agy member to match, and fix the plugin's docs/tests. Land sase first.

**Key conflicts I resolved with my own verification:**

- **Hydrogen entitlement** (the biggest split): I re-fetched Google's current Antigravity model docs — Hydrogen is listed on **all plans with no footnote**, so it gets no advisory (grk's Pro-gated advisory and mus's copied Ultra advisory were based on the launch blog, which the docs table now supersedes). Argon is Pro†/Ultra/Enterprise, confirming sase's current advisory is stale.
- **Shell `--model` completion**: mus and gem claimed it was manifest-driven; I confirmed it's a compiled-in five-alias tuple with a pinning test (cdx/cld were right). Since it lists no concrete models for *any* provider by design, the report recommends deferring it to a feature bead, with cdx's `importlib.resources` design recorded for that bead.
- **Live tier break**: I independently reproduced cld's finding — `agy --model gemini-3.7-flash-high` errors out, so bare agy-tier launches fail today. That's why the tier repair is included as a flagged scope addition (3.8 Flash now; Hydrogen promotion deferred until Free-plan access is confirmed from a Free account).
- **Swarm effort**: xhigh over high (3–2 researcher split), decided on swarm design parity — every other member defaults to its provider's top rung, and Hydrogen's xhigh is the first agy slug that can reach it.

Deferred follow-ups are listed in the report: `agy --effort` passthrough (upstream now supports it; sase's adapter doesn't), Carbon/Orchestrator, agy catalog drift (Claude 5.5 missing, five stale families, Nov 18 removals), and the stale 3.7-Flash pins in `reads.md`, doc examples, and chezmoi snippets.
