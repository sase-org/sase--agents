- **AGENTS:**
  - [bbugyi200.athena.research.58.linker](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.58.linker/README.md)

%id(linker, clan=research.58) %m:@xlarge %wait:research.58.final %wait:research.58.image
%q(1.5x, w=0.25) #gh:gh_sase-org__sase You are the linker agent for a research swarm.
The lead researcher, `research.58.final`, has written a consolidated report on the
request below. Your job is to publish that report as the canonical `<name>.md`: the file
readers open, and the one SASE renders into a Highlights PDF. You are an editor, not a
researcher. The new file must carry exactly the lead's meaning and intent. Do not do
research of your own: add no new claims or sources, settle no open questions, and
neither soften nor strengthen the conclusions or the recommendation. If the lead seems
wrong, leave it as written. The only prose you write yourself is the short
research-query summary of the request that opens the file (step 3). The only other
content you add is the image agent's diagrams and captions, copied verbatim, plus a
figure anchor and one short reference sentence for each diagram you place (step 3).

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it, but summarize it as the file's
research query in step 3):

I would like to start setting sase variables automatically whenever the /sase_questions
skill is used. The goal of this change is to make it so when the user selects an agent
session on the "Agents" tab that is associated with an agent turn that asked questions,
those questions, their recomended answers, their actual answers (if any questions have
been answered yet), and how the questions were answered (if any questions have been
answered yet) are all immediately visible (since variables are rendered in the main
deck).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The lead researcher's registered report:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

The image agent's registered images:

{% for a in wait.artifacts if a.kind == "image" %}

- wait_name={{ a.wait_name }} label={{ a.label }} vcs_relpath={{ a.vcs_relpath }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

The image agent's diagram proposals:

{% if agents is defined %}{% for key, outputs in agents.items() if outputs.diagrams is defined %}

- agent={{ key }} diagrams={{ outputs.diagrams }} {% endfor %}{% endif %}
  {% for a in wait.artifacts if a.label and a.label.startswith("diagrams:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} path={{ a.path }} ref={{ a.ref }}
  {% endfor %}

Steps:

1. **Identify the source.** From the registered reports above, find exactly one entry
   with `wait_name` `research.58.final` whose label has the form
   `research:<YYYYMM>/<name>/<name>__final.md`. If there is not exactly one such entry,
   stop and report the missing or ambiguous input instead of guessing. Open the research
   repo with `/sase_repo`, then read the report through its canonical research reference
   (or the `ref` field's `file:<id>` reference if the original has moved) using
   `sase artifact read`. Take `<YYYYMM>/<name>/` from the label, never from the current
   date. Do not read predecessor chat transcripts. Never modify, move, or delete
   `<name>__final.md` or the drafts or `<name>.diagrams.md`. Read the `diagrams`
   variable of `research.58.image`. Only when its `status` is `ready`, take exactly one
   listed `diagrams:` entry from `wait_name` `research.58.image` whose label is
   `diagrams:<YYYYMM>/<name>/<name>.diagrams.md` for the lead's own `<YYYYMM>/<name>/`.
   Read it with `sase artifact read`, and confirm its `source` equals the lead's label.
   Publish with no proposed diagrams, and say why in the final response, if the status
   is `none` or `failed`, the variable is missing, the manifest entry is missing or
   ambiguous, or the source does not match. Diagram problems never stop publication. The
   manifest's `question` and `review` are the image agent's audit notes: never copy them
   into the report.

2. **Inventory what must survive.** Before writing, list every finding, recommendation,
   caveat, open question, confidence statement, number, date, version, code block, table
   (record its cells; step 3 converts each one into a list), and link in the lead's
   report. For each manifest diagram, record its ID against the one lead block
   (paragraph or list item) that contains its `anchor`. Mark a diagram whose anchor
   matches zero or several blocks as omitted. Mark every diagram after the fifth in
   manifest order as omitted (over the cap).
3. **Restructure** the lead's report into a well-thought-out organization:
   - Keep the frontmatter, updating `updated_time` if present.
   - **Open the file in this exact order**, with nothing else between these parts: the
     frontmatter (if any), one `#` title, the research query, the infographic, and then
     the bottom-line section.
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
     `![<alt text>](<name>_infographic.png)`. Locate it by the `<name>_infographic.png`
     convention or the image entries above. Embed only a file you have confirmed exists
     beside the report in your research checkout. If the image agent completed without
     producing one, publish without it (the research query then sits directly above the
     bottom-line section) and say so in the final response.
   - **Bottom-line section.** The first `##` section is `## Bottom line` (or
     `## Overview` when the report surveys options rather than giving one answer) and
     gives the answer first.
   - Below it, `##` and `###` sections ordered by the questions a reader will ask, with
     duplicated passages merged.
   - **Never number headings.** The PDF renderer runs pandoc with `--number-sections`,
     so hand-numbered headings render doubly numbered.
   - **No table of contents and no block of jump links.** The PDF already gets a TOC.
   - **No tables.** The PDF renderer (pandoc → XeLaTeX) prints tables with equal-width
     columns, cramped wrapped cells, and rows that jump pages. Convert every table in
     the lead's report (pipe, grid, simple, multiline, or HTML) into a list with one
     item per row, keeping every cell's content:
     - Two columns: `- **<first cell>:** <second cell>`.
     - Three or more columns: a bullet whose first line is the row's identifying cell in
       bold (merge an ID column into it, e.g. `- **A1. Restart exactly once**`), then
       one nested bullet per remaining non-empty cell, `- *<Column header>:* <cell>`, in
       column order. Labels go in italics so bold inside a value stays distinct.
     - Ordered rows (phases, steps, ranks, tiers): the same shapes as a numbered list,
       keeping the original numbers.
     - Grouped rows (a blank first cell continues the group above): nest them under one
       bullet for the group.
     - Rows whose cells are all a few words: one line,
       `- **<row>:** <header> <value> · <header> <value> · …`.
     - Numbers: keep units, periods, denominators, and the difference between zero,
       unknown, and not applicable.
     - Long code in a cell: a fenced code block inside the list item.
     - Only when the rows are about six or fewer major named options the report
       discusses at length: one `###` section per option holding the same
       italic-labelled bullets. Never turn a row into a `####` heading. Turn a table
       caption into a one-line lead-in sentence. Put a blank line before every list
       (pandoc otherwise merges it into the paragraph above). Indent nested bullets 2
       spaces under `- ` and 3 spaces under `1. `. Write URLs as `[text](url)` or
       `<url>`, never bare. Do not substitute a definition list (`Term` then
       `: definition`), an HTML table, a grid or simple table, a table in a code block,
       a callout or `:::` div, raw LaTeX, or an image, or a diagram. Never drop a cell,
       merge two rows, or add totals, rankings, or conclusions the table did not state.
   - Keep the lead's wording where it works. Never drop a claim, caveat, or source to
     save space. If the lead's report restates the question or lists its inputs, keep
     those details in a later section; the research query summarizes the request but
     does not replace them.
   - **Place proposed diagrams.** After restructuring, insert each fence byte-for-byte
     directly after the block that now carries the tagged content, even if that content
     was reordered, merged, or converted from a table into a list. Only that figure's
     reference sentence may sit between the block and its fence. Follow the fence with
     the caption as one italic line, with blank lines around both, and wrap the fence
     and caption in the figure anchor described below. Then check that the surrounding
     final text still states the `illustrates` point and that no box or edge contradicts
     it. Omit the diagram otherwise. Never place a diagram in the fixed opening
     sequence, directly under a heading, inside a list or blockquote (put it after the
     whole list), or in an appendix; bottom-line content goes at the end of that
     section; two diagrams on one block go in manifest order. Never edit, redraw, merge,
     or invent a diagram. A private scratch marker such as `<!-- D:<id> -->` may be used
     in the working draft but must be gone before writing.
   - **Anchor every placed figure.** Wrap each placed fence and its caption, and nothing
     else, in `<div id="figure-<id>">` and `</div>`, using its manifest `## <id>`.
     Convert the ID to lowercase letters, digits, and hyphens, replacing each run of
     other characters with one hyphen. Keep the resulting ID unique in the file; if it
     matches a heading anchor or another figure ID, append `-2`, `-3`, and so on. Leave
     a blank line after the opening tag and before the closing tag so GitHub and pandoc
     parse the fence and caption as Markdown. The wrapper is the figure's link target on
     both reading surfaces: GitHub keeps its ID for jumps, and the Highlights PDF gives
     it return links. Use this shape:

     ```markdown
     <div id="figure-publication-order">

     <the manifest's mermaid fence, byte-for-byte>

     _The linker publishes once, after every companion finishes._

     </div>
     ```

     Never put an ID or attribute on the fence itself, and never substitute an `<a>`
     anchor or a heading. This wrapper and the listen card are the only HTML blocks you
     write. The table rule that forbids `:::` divs is about table substitutes and does
     not cover this figure wrapper.

   - **Reference every placed figure.** Write exactly one short sentence per placed
     figure and link it with `[<link text>](#figure-<id>)`, using the final unique ID,
     so every published figure is referenced. Tell the reader what the figure makes
     visible that the prose alone does not, such as a path, order, branch, or handoff.
     Build the sentence from the manifest's `illustrates` point, phrased in the
     surrounding text's terms. Never write a bare pointer such as "See the diagram
     below." The sentence is a pointer, not a finding: add no claim, number, actor,
     step, or causal link that `illustrates` and the surrounding final text do not
     already state; keep conditional wording conditional and proposed designs distinct
     from implemented ones. Do not repeat the caption word for word. Name the figure in
     the link text, for example `the publication-order diagram`. Never use "here",
     "this", or a figure number in the link text. Keep it to about 12 to 30 words of
     plain prose. It is not italic, a heading, or a list item, and never goes inside the
     figure's `<div>`, its caption, or a blockquote. When the figure directly follows
     the paragraph that carries its anchor, make the reference sentence end that
     paragraph. Otherwise, give it its own short paragraph directly above the figure's
     `<div>`; this happens when the anchor sits in a list (so the figure follows the
     whole list) or when the figure closes the bottom-line section. Two figures after
     one block get one sentence each, in manifest order. If you omit a figure, delete
     its sentence too; no link may point to an unpublished figure. For example:
     `… so the link must be in the linker's first commit. [The publication-order diagram](#figure-publication-order) traces why the linker waits for every companion agent: the PDF hook fires only once, on the ADD of name.md.`

4. **Validate every link carried over.**
   - Relative links resolve from `<YYYYMM>/<name>/`, and in-document anchors resolve
     against the final headings and figure anchors. Both are hard requirements.
   - Check external URLs with `curl -fsSL -o /dev/null --max-time 20 <url>`, retrying a
     transient failure once. Treat 401, 403, 429, and timeouts as _unverified_ and keep
     those links.
   - Verify repository-file links through a `/sase_repo` checkout, not by fetching
     github.com.
   - Repair a link only when the right target is certain: a followed redirect, a moved
     file, an obvious typo, or a renamed heading. For an unrepairable link, keep its
     text, drop the dead URL, and list it in the final response. **Never search for a
     replacement source.**

5. **Add in-document links** so readers can jump between parts of the file. Add them
   inline and sparingly: from summary points to the sections that back them, from "see
   above" or "see below" phrases, and from mentions of a named option, phase, or finding
   to where it is discussed. Do not link every mention.
   - Every heading used as a link target must start with a letter, contain only letters,
     digits, spaces, and hyphens, and be unique. Its anchor is then the lowercased
     heading with spaces replaced by hyphens, for example
     `[the bottom line](#bottom-line)`. pandoc (the PDF) and GitHub then agree.
   - Move emoji, version numbers, and code out of such headings, into the section's
     first line.
   - When `pandoc` is available, confirm anchors with `pandoc <file> -t html`.
   - A summary point that discusses a figure's content may also link sparingly to its
     `figure-<id>` anchor. Always link a figure through that anchor, never through a
     nearby heading.

6. **Re-check against the step-2 inventory** and restore anything missing or changed.
   Every URL in `<name>__final.md` must appear in the new file unless it was listed as
   unrepairable. Then confirm the file opens in the step-3 order: title, research query,
   infographic, bottom-line section. Confirm every cell of every table in the lead's
   report appears in the new file. When `pandoc` is available, confirm no table
   survives:
   `pandoc <file> -f markdown -t json | grep -o -i -E '"t":"Table"|"t":"RawBlock","c":\["html","<table' | wc -l`
   prints `0`. Every Mermaid diagram from the lead's report is still present. Every
   manifest diagram appears exactly once, byte-identical, or is named as omitted. Every
   accepted diagram sits inside exactly one figure-anchor `<div>` holding only its fence
   and caption, and its reference sentence links to it:
   `grep -c '^<div id="figure-' <file>` equals the number of accepted diagrams; every
   `(#figure-` link names an ID that exists in the file; and `pandoc <file> -t html`
   shows each `id="figure-<id>"`. The published mermaid fence count equals the lead's
   count plus the number of accepted proposed diagrams. In the final response, list
   accepted diagram IDs with their `figure-<id>` anchors and omitted IDs with reasons.
   Never write "diagrams pending".

7. **Write** `<YYYYMM>/<name>/<name>.md` without overwrite. On a collision, stop and
   report it.

8. **Register** it as a durable snapshot:

   sase artifact create -p "<absolute-report-path>" -l
   "research:<repo-relative-report-path>"

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
