# Chat History - ace-run (research.54.final)

- **TIMESTAMP:** 2026-10-20 10:06:13 EDT
- **MODEL:** claude/opus
- **AGENT:** research.54.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261020_090613.md`

## Prompt

%clan(research.54, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The mermaid diagrams that the image agent in the `#research_swarm` macro swarm
recommends are difficult to understand in isolation, not very useful, and not very
visually appealing. I would like to improve this agent's instructions (using some
mermaid diagram advice that is factored out to its own macro maybe?) so it produces much
more useful, easy to understand, and beautiful mermaid diagrams.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.54.final %m:@xlarge
%wait:research.54.cdx %wait:research.54.cld %wait:research.54.grk %wait:research.54.mus %wait:research.54.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The mermaid diagrams that the image agent in the `#research_swarm` macro swarm
recommends are difficult to understand in isolation, not very useful, and not very
visually appealing. I would like to improve this agent's instructions (using some
mermaid diagram advice that is factored out to its own macro maybe?) so it produces much
more useful, easy to understand, and beautiful mermaid diagrams.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.54.cdx`, `research.54.cld`, `research.54.grk`, `research.54.mus`, `research.54.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.54.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.54.linker`, can find it:

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

I've opened the research repo. Next I'll read the five reports, running the reads from the workspace root.

I've read all five reports. Next I'll check the main disagreements against the source: the plugin macros, the PDF renderer's Mermaid config, and sase's skill loader.

Still checking whether `sase skill init` deploys plugin-shipped skills to providers. That decides whether the skill-source option works outside the swarm.

Reports moved. Now I'll write the consolidated report.

Report written. I'll check that all three Mermaid figures in it render under the PDF config and that the sizes I quoted match.

All three render and the sizes match. Registering the consolidated report:

Layout is complete and the primary workspace is clean. Submitting the final declaration.

I've written and registered the consolidated report, and the research repo commit is declared for the host to make after this turn. I found exactly one report per suffix (cdx, cld, grk, mus, gem), read each through `sase artifact read`, and moved them into `202610/research_swarm_mermaid_diagram_craft/`. The final report is `research_swarm_mermaid_diagram_craft__final.md`, registered as `file:explicit:2044c475647e2b3745223fb4` for the linker.

**Verdict:** your instinct is right, but moving the Mermaid advice into its own macro is the smallest part of the fix. Three things in the current `#research/diagrams` instructions cause the bad diagrams:
- **Wrong subject:** it asks for "drill-downs" ranked by how much detail they reveal, so it draws minor mechanisms instead of the figure a reader needs.
- **Flat output by rule:** the drawing rules are mostly bans — no `classDef`, labels of about four words, no decision shapes, and nothing asking for a title.
- **No real check:** the agent never looks at its render, and its one size check can't fail. Under the PDF's settings it reads an internal 200 px value for every diagram.

I tested the reports' disagreements by rendering under the PDF renderer's exact Mermaid 12.2.0 config:
- **Colour:** `classDef` colours do render in the PDF, so grk and gem were wrong to keep the ban. Theme directives (`%%{init}%%` or a frontmatter `theme`) are silently ignored, so mus's and gem's theme proposals do nothing there.
- **`<br/>` line breaks** work, contrary to grk.
- **Decision shapes:** hexagons came out 24% shorter than diamonds on the same graph. Long text in either shape makes it balloon.
- **New diagram types (mus):**
  - `timeline` drops its title and printed at 66% for three dates.
  - `pie` and `quadrantChart` need numbers the report usually doesn't state.
  - `mindmap` is just a nested list.
- **Forcing structure (gem):** gem's redraw prints at 77% and adds start and end steps the source report doesn't contain.
- **The model:** your `#rsa` alias runs the image agent on `gpt-6-astra`, the same general model it uses for the cdx researcher. So the "wrong model" theory is weaker than two reports claimed.
- **Who draws the diagrams:** only 4 of the 20 Mermaid figures in published reports came from the diagrams agent; lead researchers wrote the other 16.

**Recommended solution:**
1. **Package the advice as a plugin skill.** Add `skills/mermaid_diagrams.md` to `sase-research-artifacts`. The diagrams macro includes it as `#skill/mermaid_diagrams`, and any agent, including the lead, can load it as `/mermaid_diagrams`. I confirmed sase loads plugin skills and `sase skill init` deploys them to every provider.
2. **Change what gets drawn.** Pick figures that answer a named reader question, ranked by how much the report's conclusion depends on them. Zero diagrams for a survey report counts as success.
3. **Replace the bans with positive rules:**
   - an in-figure title;
   - a bold name plus a short gloss on each node, up to about eight words;
   - at most three colour classes, each setting fill, stroke and text colour.
4. **Add a look step.** Render with the PDF's settings, look at the image, and revise at most twice. Fail any figure that would print below 75% scale.
5. **Measure before anything bigger.** Run a small blind before/after comparison before splitting diagrams into their own agent or changing the PDF renderer's theme.

**Requirement changes I made:**
- I redefined "beautiful" as clean structure plus a small colour palette, because the PDF locks the theme.
- Fixing the instructions alone isn't enough; the plan has to add the look step.
- It reverses the earlier drill-down design choice.
- "More useful" may mean fewer diagrams.
- Optionally, let the lead researcher use the same skill.

The report includes a draft outline of the skill and an example figure I drew in the recommended style. It printed at 81% on the first draft and 100% after one revision, which shows why the look step matters. All three figures in the report render under the PDF config.

Not verified: which Mermaid version GitHub uses and how the diagrams look in GitHub dark mode, whether Mermaid's default layout beats `dagre` in general (two samples disagree), and the full Highlights PDF pipeline. I computed page fit from the renderer's code rather than producing a PDF.
