# Chat History - ace-run (research.4h.final)

- **TIMESTAMP:** 2026-10-14 13:40:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4h.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_125612.md`

## Prompt

%clan(research.4h, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
want to start instructing the `#research_swarm` macro swarm's linker agent to make sure
that the final research file that it creates does not contain any markdown tables, but
I'm not sure what to tell that agent to convert markdown tables into. The problem is
that these markdown files are converted into PDFs and that doesn't work well with
markdown tables. Can you do some research with the goal of recommending the best
alternative to markdown tables that will render beautifully when converting that
markdown file to a PDF file? End your analysis with a recommended solution.]]) %id:research.4h.final %m:@xlarge
%wait:research.4h.cdx %wait:research.4h.cld %wait:research.4h.grk %wait:research.4h.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
want to start instructing the `#research_swarm` macro swarm's linker agent to make sure
that the final research file that it creates does not contain any markdown tables, but
I'm not sure what to tell that agent to convert markdown tables into. The problem is
that these markdown files are converted into PDFs and that doesn't work well with
markdown tables. Can you do some research with the goal of recommending the best
alternative to markdown tables that will render beautifully when converting that
markdown file to a PDF file? End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.4h.cdx`, `research.4h.cld`, `research.4h.grk`, `research.4h.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4h.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4h.linker`, can find it:

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
├── <name>__gem.md
└── <name>__final.md
```

## Response

Confirmed the real PDF path is `bob ref create` (pandoc → XeLaTeX). Now I'm copying its exact filters and flags into a scratch harness so I can render the competing formats myself.

Corpus counts match cld closely: 1,201 tables across 208 of 213 published reports. Checking how often bare URLs appear, then I'll write the merged report.

Report drafted. A corpus check confirms the italic-label choice: about a quarter of table rows have a value cell that starts in bold. Making three small accuracy fixes, then registering the report.

The check command works in both shells. Registering the consolidated report for the linker now.

Registered. Now the required end-of-turn declaration.

**Recommendation:** have the linker turn every table into a **record list**: one bullet per table row, in plain Markdown.

- **Two-column tables** become `- **Term:** explanation`.
- **Tables with three or more columns** become a bullet with the row's name in bold. Each other cell becomes a nested bullet labelled with its column header in italics, like `- *Main risk:* …`.
- **Ordered rows** (phases, steps, ranks) become a numbered list in the same shapes.
- **Rows of short values** collapse to one line: `- **Healer:** effort high · risk medium · reversible`.
- **Headings per row** are allowed only when the rows are about six or fewer major options that the report discusses at length. A row never becomes a `####` heading.

All four researchers agreed a list-based form is the right replacement. The other candidates all render badly or not at all in this pipeline: definition lists, HTML tables, grid tables, tables inside code blocks, callouts, and images.

**Why tables look bad:** the research PDFs come from `bob ref create`, which runs pandoc → XeLaTeX on US Letter. Agents almost always write `| --- | --- |`, so pandoc gives every column the same width. A 2-character `#` column takes as much space as a prose column, cells wrap every few words, and rows can jump to the next page. 208 of the 213 published reports contain tables, about 1,200 in all.

**Settling the two disagreements:** I copied Bob's exact pandoc filters and flags and rendered each candidate format myself.
- **Headings vs. nested bullets:** headings per row (two researchers' default) add an entry to the PDF's table of contents for every row. `####` headings run into the paragraph that follows them. So nested bullets are the default.
- **Bold vs. italic labels:** with bold labels, `**Verdict:** **Rejected.**` prints as one indistinguishable bold run. About a quarter of table rows in the corpus have a cell after the first one that starts in bold, so italic field labels are needed.

**Three formatting rules the instruction must include, or the PDF breaks silently** (all checked by rendering):
- **Blank line before every list.** Without one, Bob's pandoc prints the bullets as one run-on paragraph, even though GitHub shows them fine.
- **3-space indent for bullets nested under `1.`.** With 2 spaces, the numbered list splits in two.
- **No bare URLs.** A bare URL runs off the page, in a list just as in a table. Use `[text](url)` or `<url>`.

**Things to know:**
- **Self-check:** the linker can run a pandoc command that prints `0` when no table survives. A simple `grep '<table'` would give false alarms on reports that mention HTML tables in code, so the report gives the exact command.
- **Swarms without a linker:** the linker only runs when `linker`, `image`, or `audio` is true (`linker` defaults to false). Otherwise the lead publishes the rendered file and its tables reach the PDF. To cover every swarm, the lead's prompt needs the same rule in that case.

The consolidated report includes paste-ready text for steps 2, 3 and 6 of the linker prompt in `sase-research-artifacts/.../xprompts/research_swarm.md`. I didn't edit the prompt itself.

**Housekeeping:**
- Moved the four researcher reports into `202610/pdf_friendly_markdown_table_alternatives/`, each keeping its `__<suffix>.md`.
- Wrote `pdf_friendly_markdown_table_alternatives__final.md` there.
- Registered the report for the linker as `research:202610/pdf_friendly_markdown_table_alternatives/pdf_friendly_markdown_table_alternatives__final.md` (ref `file:explicit:fd4ecc8035940b212304a912`).
- Submitted the commit declaration; the host commits the research repo after this turn.
