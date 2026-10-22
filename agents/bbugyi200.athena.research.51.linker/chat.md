# Chat History - ace-run (research.51.linker)

- **TIMESTAMP:** 2026-10-19 15:37:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.51.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_142606.md`

## Prompt

%id(linker, clan=research.51) %m:@xlarge
%wait:research.51.final %wait:research.51.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.51.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written. The only prose you write yourself is the short research-query summary of the
request that opens the file (step 3). The only other content you
add is the image agent's diagrams and captions, copied verbatim.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it, but summarize it as the file's
research query in step 3):

Can you review the Obsidian tasks in the ~/bob/sase.md file with the goal of helping me
split out some child project notes? Also, if there are any duplicates, call those out as
well. End your analysis with a recommended project split and an overall summary of the
tasks that live in this file.

The lead researcher's registered report:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

The image agent's registered images:

{% for a in wait.artifacts if a.kind == "image" %}
- wait_name={{ a.wait_name }} label={{ a.label }} vcs_relpath={{ a.vcs_relpath }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}


The image agent's diagram proposals:

{% if agents is defined %}{% for key, outputs in agents.items() if outputs.diagrams is defined %}
- agent={{ key }} diagrams={{ outputs.diagrams }}
{% endfor %}{% endif %}
{% for a in wait.artifacts if a.label and a.label.startswith("diagrams:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}


Steps:

1. **Identify the source.** From the registered reports above, find exactly one entry
   with `wait_name` `research.51.final` whose label has the form
   `research:<YYYYMM>/<name>/<name>__final.md`. If there is not exactly one such entry,
   stop and report the missing or ambiguous input instead of guessing. Open the research
   repo with `/sase_repo`, then read the report through its canonical research reference
   (or the `ref` field's `file:<id>` reference if the original has moved) using
   `sase artifact read`. Take `<YYYYMM>/<name>/` from the label, never from the current
   date. Do not read predecessor chat transcripts. Never modify, move, or delete
   `<name>__final.md` or the drafts or `<name>.diagrams.md`.
   Read the `diagrams` variable of `research.51.image`. Only when its `status` is
   `ready`, take exactly one listed `diagrams:` entry from `wait_name`
   `research.51.image` whose label is
   `diagrams:<YYYYMM>/<name>/<name>.diagrams.md` for the lead's own
   `<YYYYMM>/<name>/`. Read it with `sase artifact read`, and confirm its `source`
   equals the lead's label. Publish with no proposed diagrams, and say why in the
   final response, if the status is `none` or `failed`, the variable is missing, the
   manifest entry is missing or ambiguous, or the source does not match. Diagram
   problems never stop publication.

2. **Inventory what must survive.** Before writing, list every finding, recommendation,
   caveat, open question, confidence statement, number, date, version, code block,
   table (record its cells; step 3 converts each one into a list), and link in the
   lead's report. For each manifest diagram, record its ID against
   the one lead block (paragraph or list item) that contains its `anchor`. Mark a
   diagram whose anchor matches zero or several blocks as omitted.
3. **Restructure** the lead's report into a well-thought-out organization:
   - Keep the frontmatter, updating `updated_time` if present.
   - **Open the file in this exact order**, with nothing else between these parts: the frontmatter (if any), one `#` title, the research query, the infographic, and then the bottom-line section.
   - **Research query.** Directly below the title, add one blockquote that summarizes
     the research request above in one to three sentences, for example
     `> **Research query:** <summary>`. Phrase it as the question or task being
     answered, in the requester's own terms: keep the questions, named subjects, and
     explicit scope or constraints; drop instructions aimed at agents, such as output
     paths, macro or directive syntax, and formatting requests. Summarize what was
     asked, not material the request quotes or attaches. Use a request that is already
     one short sentence verbatim. Never fold findings, answers, or scope the request
     does not state into it. It is not a heading, so it gets no section number and no
     TOC entry.
   - **Embed the infographic** exactly once, directly above the bottom-line section:
     after the research query and before that section's `##` heading, never further
     down. Use a relative link with descriptive alt text, for example
     `![<alt text>](<name>_infographic.png)`. Locate it by the
     `<name>_infographic.png` convention or the image entries above. Embed only a file
     you have confirmed exists beside the report in your research checkout. If the
     image agent completed without producing one, publish without it (the research query then sits directly above the bottom-line section) and say so in the final
     response.
   - **Bottom-line section.** The first `##` section is `## Bottom line` (or
     `## Overview` when the report surveys options rather than giving one answer) and
     gives the answer first.
   - Below it, `##` and `###` sections ordered by the questions a reader will ask, with
     duplicated passages merged.
   - **Never number headings.** The PDF renderer runs pandoc with `--number-sections`,
     so hand-numbered headings render doubly numbered.
   - **No table of contents and no block of jump links.** The PDF already gets a TOC.
   - **No tables.** The PDF renderer (pandoc → XeLaTeX) prints tables with equal-width
     columns, cramped wrapped cells, and rows that jump pages. Convert every table in the
     lead's report (pipe, grid, simple, multiline, or HTML) into a list with one item per
     row, keeping every cell's content:
     - Two columns: `- **<first cell>:** <second cell>`.
     - Three or more columns: a bullet whose first line is the row's identifying cell in
       bold (merge an ID column into it, e.g. `- **A1. Restart exactly once**`), then one
       nested bullet per remaining non-empty cell, `- *<Column header>:* <cell>`, in column
       order. Labels go in italics so bold inside a value stays distinct.
     - Ordered rows (phases, steps, ranks, tiers): the same shapes as a numbered list,
       keeping the original numbers.
     - Grouped rows (a blank first cell continues the group above): nest them under one
       bullet for the group.
     - Rows whose cells are all a few words: one line,
       `- **<row>:** <header> <value> · <header> <value> · …`.
     - Numbers: keep units, periods, denominators, and the difference between zero,
       unknown, and not applicable.
     - Long code in a cell: a fenced code block inside the list item.
     - Only when the rows are about six or fewer major named options the report discusses
       at length: one `###` section per option holding the same italic-labelled bullets.
       Never turn a row into a `####` heading. Turn a table caption into a one-line lead-in
       sentence. Put a blank line before every list (pandoc otherwise merges it into the
       paragraph above). Indent nested bullets 2 spaces under `- ` and
       3 spaces under `1. `. Write URLs as `[text](url)` or `<url>`, never bare. Do not
       substitute a definition list (`Term` then `: definition`), an HTML table, a grid
       or simple table, a table in a code block, a callout or `:::` div, raw LaTeX, or
       an image, or a diagram. Never drop a cell, merge two rows, or add totals, rankings, or
       conclusions the table did not state.
   - Keep the lead's wording where it works. Never drop a claim, caveat, or source to
     save space. If the lead's report restates the question or lists its inputs, keep
     those details in a later section; the research query summarizes the request but
     does not replace them.
   - **Place proposed diagrams.** After restructuring, insert each fence byte-for-byte
     directly after the block that now carries the tagged content, even if that content
     was reordered, merged, or converted from a table into a list. Follow it with the
     caption as one italic line, with blank lines around both. Then check that the
     surrounding final text still states the `illustrates` point and that no box or
     edge contradicts it. Omit the diagram otherwise. Never place a diagram in the
     fixed opening sequence, directly under a heading, inside a list or blockquote
     (put it after the whole list), or in an appendix; bottom-line content goes at the
     end of that section; two diagrams on one block go in manifest order. Never edit,
     redraw, merge, or invent a diagram. A private scratch marker such as
     `<!-- D:<id> -->` may be used in the working draft but must be gone before
     writing.
4. **Validate every link carried over.**
   - Relative links resolve from `<YYYYMM>/<name>/`, and in-document anchors resolve
     against the final headings. Both are hard requirements.
   - Check external URLs with `curl -fsSL -o /dev/null --max-time 20 <url>`, retrying
     a transient failure once. Treat 401, 403, 429, and timeouts as _unverified_ and
     keep those links.
   - Verify repository-file links through a `/sase_repo` checkout, not by fetching
     github.com.
   - Repair a link only when the right target is certain: a followed redirect, a moved
     file, an obvious typo, or a renamed heading. For an unrepairable link, keep its
     text, drop the dead URL, and list it in the final response. **Never search for a
     replacement source.**

5. **Add in-document links** so readers can jump between parts of the file. Add them
   inline and sparingly: from summary points to the sections that back them, from "see
   above" or "see below" phrases, and from mentions of a named option, phase, or
   finding to where it is discussed. Do not link every mention.
   - Every heading used as a link target must start with a letter, contain only
     letters, digits, spaces, and hyphens, and be unique. Its anchor is then the
     lowercased heading with spaces replaced by hyphens, for example
     `[the bottom line](#bottom-line)`. pandoc (the PDF) and GitHub then agree.
   - Move emoji, version numbers, and code out of such headings, into the section's
     first line.
   - When `pandoc` is available, confirm anchors with `pandoc <file> -t html`.

6. **Re-check against the step-2 inventory** and restore anything missing or changed.
   Every URL in `<name>__final.md` must appear in the new file unless it was listed as
   unrepairable. Then confirm the file opens in the step-3 order: title, research query, infographic, bottom-line section.
   Confirm every cell of every table in the lead's report appears in the new file. When
   `pandoc` is available, confirm no table survives:
   `pandoc <file> -f markdown -t json | grep -o -i -E '"t":"Table"|"t":"RawBlock","c":\["html","<table' | wc -l`
   prints `0`. Every Mermaid diagram from the lead's report is still present. Every manifest diagram appears exactly once, byte-identical,
   or is named as omitted. The published mermaid fence count equals the
   lead's count plus the number of accepted proposed diagrams. In the final response, list accepted and omitted diagram IDs
   with reasons. Never write "diagrams pending".

7. **Write** `<YYYYMM>/<name>/<name>.md` without overwrite. On a collision, stop and
   report it.

8. **Register** it as a durable snapshot:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the report's actual absolute path and its path relative to the research repo
   root, for example `research:202609/<name>/<name>.md`. Use no `--move`. If
   registration fails, report it and do not claim full completion.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
├── <name>__final.md
├── <name>_infographic.png
├── <name>.diagrams.md (optional)
└── <name>.md
```

## Response

I've opened the research repo and read the lead's final report. Next I'll read it in full, plus the diagram manifest.

Lead report and the one-diagram manifest are read (status ready, source matches). Next I'll check the infographic so the alt text is accurate, then build the restructured file.

The anchor matches exactly one block, and the lead has no external URLs or markdown links. Writing the draft now.

Draft written. Next: splice in the diagram fence and caption, then run the checks (tokens, anchors, tables, pandoc).

Only table headers and section numbers dropped, as expected. Every L-number, code span, quote, star, and arrow survived. Next: pandoc checks for tables, anchors, and mermaid count.

No tables, all 32 internal links resolve, headings are compliant and unique, and the opening order is right. Next I'll check that the nested lists and `$20` render correctly in pandoc.

Registered. Now the final declaration.

I've published the lead's report as `202610/bob_sase_task_portfolio_split/bob_sase_task_portfolio_split.md` in the research repo and registered it (`file:explicit:64d1b8f67b2150f8df86561a`). The commit is declared; the host makes it after this turn ends. The lead's final, the drafts and the diagram manifest were left untouched.

- **Opening order:** the title comes first, then a two-sentence research query, then the infographic (it's in the same folder), then `## Bottom line`. The lead's report had no frontmatter, so there was no `updated_time` to update.
- **Restructure:** the content follows the lead's order. The line explaining the inputs, snapshot and line numbers is now a short "About this review" section after the bottom line. I removed the section numbers. Each "§2.3"-style reference is now a link to the named section, and I made headings link-safe by moving code out of them, for example "Merge groups inside `sase.md`" became "Merge groups". In total there are 32 links within the file, and all of them resolve under pandoc.
- **Tables:** all 16 tables are now lists, with no cells dropped. pandoc finds 0 tables in the new file. A check against the lead's text found every line number, code span, quoted string, number, ★ and → still present. The only things missing are column headers and section numbers, which the list format drops by design.
- **Diagrams:** I accepted the one proposed diagram, `existing-child-scope`. Its source matches the lead's report, and its anchor appears in exactly one place (Principle 2). It sits right after the whole Principles list, copied unchanged, with its caption. No diagrams were omitted. The lead's report had no Mermaid diagrams of its own, so the file has exactly 1.
- **Links:** the lead's report contains no external URLs or markdown links, so there was nothing to check and nothing that couldn't be repaired.

The only text I added besides the research query, diagram and caption is a few connecting phrases: "Each bold line is the `sase.md` side," "in open tasks" on the summary list, and "These moves cover N tasks," which comes from the lead's own section headings.
