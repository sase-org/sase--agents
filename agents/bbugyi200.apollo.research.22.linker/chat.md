# Chat History - ace-run (research.22.linker)

- **TIMESTAMP:** 2026-10-18 12:45:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.22.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_111719.md`

## Prompt

%id(linker, clan=research.22) %m:@xlarge
%wait:research.22.final %wait:research.22.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.22.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written. The only prose you write yourself is the short research-query summary of the
request that opens the file (step 3).

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it, but summarize it as the file's
research query in step 3):

Can you help me review all of the files that the previous agent just tagged in the
research sidecar repo, which are related to our efforts to make sase's PyPI releases
much more reliable? Once you've done that, you should think hard about what the best
possible solution is and how the work should be split up. It's fine if your
recommendation steals a lot from those other research files (i.e. no need to be
original). Converging on the best design/architecture is our main priority.

The lead researcher's registered report:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

The image agent's registered images:

{% for a in wait.artifacts if a.kind == "image" %}
- wait_name={{ a.wait_name }} label={{ a.label }} vcs_relpath={{ a.vcs_relpath }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}


Steps:

1. **Identify the source.** From the registered reports above, find exactly one entry
   with `wait_name` `research.22.final` whose label has the form
   `research:<YYYYMM>/<name>/<name>__final.md`. If there is not exactly one such entry,
   stop and report the missing or ambiguous input instead of guessing. Open the research
   repo with `/sase_repo`, then read the report through its canonical research reference
   (or the `ref` field's `file:<id>` reference if the original has moved) using
   `sase artifact read`. Take `<YYYYMM>/<name>/` from the label, never from the current
   date. Do not read predecessor chat transcripts. Never modify, move, or delete
   `<name>__final.md` or the drafts.

2. **Inventory what must survive.** Before writing, list every finding, recommendation,
   caveat, open question, confidence statement, number, date, version, code block,
   table (record its cells; step 3 converts each one into a list), and link in the
   lead's report.
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
       an image. Never drop a cell, merge two rows, or add totals, rankings, or
       conclusions the table did not state.
   - Keep the lead's wording where it works. Never drop a claim, caveat, or source to
     save space. If the lead's report restates the question or lists its inputs, keep
     those details in a later section; the research query summarizes the request but
     does not replace them.
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
   prints `0`.

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
├── <name>__gem.md
├── <name>__final.md
├── <name>_infographic.png
└── <name>.md
```

## Response

I've opened the research repo and read the lead's report (980 lines). Next I'll inventory it and restructure it.

All relative links resolve. Now checking the external URLs.

Link check done: all relative links resolve; all six external URLs return 200, and one (GitHub "events that trigger workflows") redirects to a new docs path. Writing the restructured report now.

Draft written. Now validating anchors, tables, and URL coverage.

Anchors all resolve, no tables remain, and the only URL change is the redirect repair. Next, a content-coverage check against the lead's report.

The remaining misses come from asterisk and link markup, plus the header cells that became labels. Rechecking with markup normalized:

Remaining misses are just restructuring seams (table rows, old headings, the replaced query) and first-column header labels. A word-level check to be thorough:

Most differences are expected (replaced query, header labels, renamed headings). Checking a few remaining tokens (`every`, `file`, `its`, `run`, `Then`):

Everything is accounted for: the replaced query, renamed headings, and header labels. Checking rendering of the nested lists and the image:

Rendering looks right. Writing the file into the research checkout without overwriting:

Registered. Now the final declaration step.

I've published the lead's report as the canonical file, `202610/pypi_release_reliability_design_and_work_split/pypi_release_reliability_design_and_work_split.md`, and registered it as a snapshot (`file:explicit:d92eb42a86d3d1b8a69c159b`). The research repo will be committed when this turn ends. I didn't touch the lead's report or the four drafts.

**Opening order:** the title, then my one-paragraph summary of your request, then the infographic (confirmed present next to the report), then `## Bottom line`.

**What changed in the layout:**
- **Tables:** all nine are now lists, and every cell is kept. The report-comparison and live-state tables put each row's values under italic labels. The phase tables (E1–E3) became numbered lists with Work and Verification items. The epic overview, file ownership and risks tables became one line per row. A pandoc check found no tables left in the file.
- **Sections:** the order now follows what a reader asks: bottom line → why releases stall (with the live-state checks) → design principles → the installable, releasable and landable promises → work split → acceptance cases → next 24 hours → what not to do → risks → how the four reports compare → method → sources.
- **Report summary line:** the lead's opening line (date, the cdx/cld/grk/gem report links, and the commits checked against) now opens "How the four reports compare". It couldn't stay above the bottom line, because nothing may sit between the infographic and that section.
- **Headings:** none are numbered, and I removed colons, code and parentheses from the headings that links point to. Promise and epic numbers, plus `sase/master`, moved into each section's first line. The lead used the same E3–E6 titles under both the design and the work split, so I renamed one side to keep every anchor unique.
- **Jump links:** I added a small number. They go from the bottom-line points to the promise, steward and epic sections, and between each epic's design section and its work-split section.

**Links:**
- All 16 relative links resolve from the report's folder, and all in-document anchors match the final headings (checked with pandoc).
- All six external URLs returned 200.
- One link changed: GitHub's "events that trigger workflows" page redirects to `https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows`, so I used that address. Because of this, the old URL no longer appears in the file, but every other URL does.
- No links were dropped.

The report's content is unchanged apart from my summary of the request. A word-by-word comparison accounted for every difference as one of: your old request summary, renamed headings, or column headers that became labels.
