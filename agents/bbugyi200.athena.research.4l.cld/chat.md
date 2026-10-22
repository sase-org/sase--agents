# Chat History - ace-run (research.4l.cld)

- **TIMESTAMP:** 2026-10-15 16:38:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4l.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_161657.md`

## Prompt

%id(cld, clan=research.4l)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4l.cdx`, `research.4l.grk`, `research.4l.mus`, `research.4l.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
want to drastically simplify sase's documentation on sase.sh by making it simpler and
more intuitive while, at the same time, adding more structure to sase's documentation
process.

- Try to use the system described by https://diataxis.fr for inspiration if possible.
- Long-term agentic management (using sase agents) of this documenttion should be
  considered, but should not be the key focus of your research report.
- Instead, this report should focus on deciding the best possible documentation solution
  and structure. This report should also focus on the (related) sase.sh site, its UX,
  and how the proposed changes make the site more intuitive for user's looking to learn
  more about sase.

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

I'll start by surveying the current docs and the sase.sh site setup in this repo.

I'm surveying the current docs (65K lines across ~65 pages, with `ace.md` alone at ~9.8K lines). Next I'll look at how the docs get maintained, the site's UX, and Diátaxis itself.

I have enough evidence. Writing the report now.

Fixing one figure: the keybinding table-row count in `ace.md` is about 475, not 460.

Now registering the report as a durable artifact.

Registration succeeded. Now submitting the final declaration.

The report is written and registered as an artifact (`file:explicit:50591b084dcdda200bd15abf`); the host commits it after this turn.

**Report:** `sase/repos/research/202610/sase_sh_docs_simplification_diataxis__cld.md`

**Verdict:** yes, do it. But the docs aren't mainly badly organized. They are a detailed behavior spec, written by agents as part of feature work, published as a user manual, and growing about 37% a month.

**What I measured:**
- **Size:** 518K words across 57 pages, about 36 hours of reading. The PDF handbook is 1,151 pages.
- **Concentration:** `ace.md` (103K words) and `configuration.md` (71K) hold 34% of all words.
- **Growth:** 119K words in mid-June to 518K now. The 15-minute tutorial nearly tripled, to 4.1K words.
- **Who writes it:** 450 of the 617 docs commits in the last 30 days were `feat:` commits, i.e. agents adding text alongside features.
- **Comparison:** uv has 72K hand-written words across 81 pages and generates its CLI, settings and environment-variable references from code.
- **Site UX:** the sidebar shows about 60 always-open links, mostly sase-specific names ("Mentors", "Beads", "SDD Storage"). The homepage offers about 25 cards but no install command and no demo.
- **Internal detail in user pages:** 741 history phrases ("formerly", "no longer", "legacy"…), 148 bead IDs and 382 `src/` paths.
- **Platform:** Material for MkDocs is in maintenance mode, with critical fixes until May 5, 2027. Its successor, Zensical, is alpha, reads `mkdocs.yml`, and has no PDF export.

**Recommendation:**
- **Two tiers.**
  - A small, curated, tested *Guide*: Get started, Guides and Concepts, about 60K words, with goal-named how-tos.
  - A *Reference*: CLI, config and keymaps generated from code; TUI and format pages split into small pages; contributor internals in their own section.
  - Agents keep all the detail they rely on; newcomers only meet the Guide.
- **Five tabs:** Get started · Guides · Concepts · Reference · Blog. The homepage becomes one screen with an install block, a demo GIF and three clear starting points.
- **Process contract enforced by lint:** a page's folder sets its type, plus templates, word limits per type that can only tighten, nav and link validation, and present-tense-only Guide pages (history goes to the CHANGELOG). A routing table tells feature agents to write reference entries rather than adding prose to Guide pages.
- **Tested tutorials:** run them against the built-in `fakey` test provider, and regenerate screenshots from the existing demo tooling.

**Requirement adjustments I made (each flagged in the report):**
- "Drastically simplify" means simplify what readers see, not delete the spec.
- Apply Diátaxis top-down for the front door but bottom-up for the reference. This partly disagrees with today's earlier docs-memory research, which advised against a top-down Diátaxis tree.
- Retire the 1,151-page PDF.
- Keep the setup portable to Zensical and migrate after its 0.1.0 release.
- Treat a guard against regrowth as required, not optional.

**Rollout:**
1. **Phase 0, about 1–2 days:** tabs, regrouped nav, new homepage. Mostly config and homepage edits, with no page moves or content rewrites.
2. **Write the Guide as new files,** which avoids conflicts with the roughly 20 docs commits a day landing on `master`.
3. **Generate the CLI, config and keymap references.**
4. **Split the oversized pages one at a time,** each move in its own commit with redirects.
5. **Move to Zensical** after its 0.1.0 release, before May 2027.
