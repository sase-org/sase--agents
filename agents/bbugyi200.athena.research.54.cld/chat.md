# Chat History - ace-run (research.54.cld)

- **TIMESTAMP:** 2026-10-20 09:41:41 EDT
- **MODEL:** claude/opus
- **AGENT:** research.54.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261020_090613.md`

## Prompt

%id(cld, clan=research.54)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.54.cdx`, `research.54.grk`, `research.54.mus`, `research.54.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The mermaid diagrams that the image agent in the `#research_swarm` macro swarm
recommends are difficult to understand in isolation, not very useful, and not very
visually appealing. I would like to improve this agent's instructions (using some
mermaid diagram advice that is factored out to its own macro maybe?) so it produces much
more useful, easy to understand, and beautiful mermaid diagrams.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Found the `#research_swarm` macro and its image/diagram agents in the `sase-research-artifacts` plugin; reading them now.

Reading the two diagram manifests the swarm has produced so far to see real output.

The global `mmdc` can't find its Chrome, so I'm switching to the `npx` form the macro falls back to, so I can render and look at the existing diagrams.

The PDFs come from `bob ref create`, and bob-cli has its own Mermaid renderer. Reading that next, since it decides what the reader actually sees.

Pinning down Mermaid 12.2's default look/theme/layout (it changes what "beautiful" means), then I'll prototype improved diagrams through a bob-equivalent render.

Baseline re-rendered with a bob-equivalent config (neutral theme, DejaVu Sans, locked theme keys). Checking how they look as PDF readers would see them.

Now prototyping "after" versions of the same diagrams through the PDF-equivalent renderer. First, reading the bob portfolio report passage behind its diagram so the redraw stays faithful.

The report's five numbered principles form a full routing procedure, but the existing diagram drew only one branch of principle 2. Rendering redesigned "after" versions now.

The palette holds up in dark mode: light fills with explicit dark text stay legible. One last experiment checks how much a renderer-level house theme alone would add, without any per-diagram styling.

Report written. Checking that every Mermaid block in it, including the new appendix example, parses under the PDF-mirroring config.

Every diagram parses and the sizes match what the report states. Registering the report as a durable artifact.

Registered as `research:202610/research_swarm_mermaid_diagram_quality__cld.md`. Submitting the final declaration.

I wrote the report and registered it as `research:202610/research_swarm_mermaid_diagram_quality__cld.md`. The host commits it to the research repo when this turn ends.

**Short answer:** your plan is a good idea, but factoring out Mermaid advice alone won't fix the diagrams. There are four causes, and missing advice is only one of them:

1. **The agent is told to draw the wrong things.** `#research/diagrams` asks for "drill-downs" that add detail the infographic panel lacks. That pulls it toward tiny details like a refresh trigger, or one branch of a five-step rule, instead of the picture a reader needs.
2. **The drawing rules ban what makes diagrams readable and attractive.** The drawing section is about ten lines, nearly all prohibitions: no `classDef` or `style`, labels of about four words in report jargon, no decision shapes. Nothing asks for a title, plain-language labels, grouping, or emphasis.
3. **The agent never looks at what it drew.** It only checks that `mmdc` parses the diagram and the width. It also checks with Mermaid's default look, while the Highlights PDF forces a neutral theme and a different font. The same diagram came out 10% taller under the PDF settings.
4. **Diagrams share an agent and model with the infographic.** The `@image` model was chosen for image generation. The October 18 research that designed this feature said weak diagrams from that model should trigger moving diagrams to their own agent.

**What I tested:** I rendered the existing diagrams with the PDF renderer's exact settings, then probed which features reach the PDF:
- **Works:** `classDef`/`style`, subgraphs, titles, bold labels (with Mermaid's backtick-quoted label syntax), and hexagon shapes.
- **Ignored:** any per-diagram theme setting, because the renderer locks the theme.
- **Gotchas:** several, all listed in the report.

I also redrew two of the real diagrams as before/after prototypes, which are embedded in the report. Looking at my own renders caught four layout defects and one place where I'd invented a branch the source report doesn't state. That is the case for adding a "look at it" step.

**Requirement changes I made:**
- Add a render-look-revise loop and a check that matches the PDF settings, not just better instructions.
- Ship the guidance as a skill in the `sase-research-artifacts` plugin (`skills/mermaid_diagrams.md`), not a plain macro. The research prompt can include it, and the lead or any other agent can call it as `/mermaid_diagrams`. I confirmed plugins can ship skills at the plugin's minimum sase version.
- Replace "drill-downs" with "key figures" ranked by how much the report's conclusion depends on them. This reverses an earlier explicit choice, so I kept its protections against agents ending up with zero diagrams.
- Allow a small fixed set of colour styles where each sets fill, border, and text colour, so text stays readable in dark mode.
- Replace the four-word label cap with a rule that each diagram must make sense on its own, while still enforcing size by measured pixels.
- "Beautiful" can only mean clean and purposeful under the PDF's locked theme. Changing that theme is a separate optional change in bob-cli.

**Recommended solution:**
- **Phase 1** is one plugin change: the new skill, rewritten selection and drawing sections, a fixed width check, and test updates. Several tests pin today's wording, so they'll need updating.
- **Phase 2:** run a small blind comparison on about five past reports, the current `@image` model against a strong text model. If the model matters, give diagrams their own agent, running in parallel with the infographic.
- **Phase 3 (optional):** an automatic diagram checker, and a nicer PDF theme in bob-cli.

The evidence base is small: the feature is a day old, so only two swarms and four diagrams exist. The prototypes are my redraws, not output from the swarm agent. I couldn't confirm which Mermaid version GitHub currently uses, so the report recommends sticking to older, widely supported syntax until someone checks.
