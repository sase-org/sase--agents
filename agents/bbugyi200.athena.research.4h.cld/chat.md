# Chat History - ace-run (research.4h.cld)

- **TIMESTAMP:** 2026-10-14 13:13:44 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4h.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_125612.md`

## Prompt

%id(cld, clan=research.4h)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.4h.cdx`, `research.4h.grk`, `research.4h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

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
want to start instructing the `#research_swarm` macro swarm's linker agent to make sure
that the final research file that it creates does not contain any markdown tables, but
I'm not sure what to tell that agent to convert markdown tables into. The problem is
that these markdown files are converted into PDFs and that doesn't work well with
markdown tables. Can you do some research with the goal of recommending the best
alternative to markdown tables that will render beautifully when converting that
markdown file to a PDF file? End your analysis with a recommended solution. 
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

Locating the research_swarm macro and the PDF conversion pipeline before researching alternatives.

Found the converter: `bob ref create` in bob-cli. Reading its pandoc rendering code now.

Now reading the exact pandoc invocation and header-includes in `create.rs`.

Surveying how often published research reports use tables (counts only, excluding drafts so I never touch peer reports).

Setting up an exact replica of bob's pandoc/XeLaTeX pipeline so I can render alternatives side by side.

Evidence is in hand. Writing the report now (itself table-free, using the recommended format).

The report renders cleanly through the replica pipeline: 7 pages, 0 tables, 4 in-document links paired, none dead. Registering it now.

Registration succeeded. Submitting the final declaration.

I recommend telling the linker to turn every table into a **record list**: one bullet per table row, starting with the row's identifying cell in bold.

- **Two-column tables:** `- **<first cell>:** <second cell>`.
- **Three or more columns:** the bold lead line (for example `**A1. Restart exactly once**`), then one nested bullet per remaining cell, labelled with its column header in italics (`*Why:* …`).
- **Rows in a set order** (phases, steps, tiers): a numbered list in the same shapes.
- **Rows of a few words each** (`Low`, `Yes`): one line joined with ` · `.

This is plain Markdown, so it looks the same on GitHub, in Obsidian, and in the PDF. Google's developer documentation style guide describes the same format ("bulleted run-in headings").

**What I checked:**
- **The pipeline.** `bob ref create` runs pandoc → XeLaTeX on the linker's `<name>.md` only; drafts and the lead's `__final.md` are never turned into PDFs. I rebuilt its exact pandoc command, filters included, and rendered seven versions of the same content.
- **Why tables look bad.** 208 of the 213 published reports contain tables, 1,204 in all. In 92% of them a source line is longer than 72 characters, and pandoc then sizes columns by the dashes in the `|---|` separator row. 92% use equal dashes, so every column gets the same width. In the sample report, a 2-character `#` column took a quarter of the page, the prose columns wrapped every few words, and four rows ran across a page break.
- **Record lists versus the table.** The same four rows took 57% of the height and stayed on one page.
- **Definition lists** run the bold term into the definition in the PDF, and GitHub doesn't support them.
- **A heading per row** comes out as numbered "1.1.0.1"-style headings.
- **HTML `<table>`** loses all structure in the PDF; the cell text runs together.
- **Grid tables and tables inside code blocks** render poorly too.

**Two pandoc details the instruction must cover**, because each breaks the output without any error:
- **A blank line before every list.** bob uses pandoc's `markdown` reader, which merges a list into the paragraph above it unless a blank line separates them. GitHub shows it correctly, so the problem only appears in the PDF.
- **Nested bullets indented 3 spaces under `1.` items.** With 2 spaces the numbered list splits in two.

The report includes ready-to-paste text for step 3 of the linker section in `research_swarm.md`. It also has a self-check for step 6: `pandoc <file> -f markdown -t json | grep -o '"t":"Table"' | wc -l` must print `0`.

**Things to know:**
- I also tried an automatic pandoc filter that converts every table to a list. It worked, taking the sample from 22 to 20 pages, but read noticeably worse than converting by hand. It could still serve as a safety net in bob-cli for tables that slip through. I didn't file a task for that; it's your call.
- The test renders were scratch files under `/tmp` and weren't kept, so the report describes what the pages looked like instead of including images.
- About 8% of tables (every line under 72 characters) do render well. A no-tables rule gives up very little there.

The report is at `202610/markdown_table_alternatives_for_pdf_reports__cld.md` in the research repo and is registered as `file:explicit:d7f7267ec242843666153730` with label `research:202610/markdown_table_alternatives_for_pdf_reports__cld.md`. It contains no tables itself, and I rendered it through the same pipeline: 7 pages, all in-document links working.
