- **AGENTS:**
  - [bbugyi200.apollo.research.0o.linker](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0o.linker/README.md)

%id(linker, clan=research.0o) %m:@xlarge %wait:research.0o.final %wait:research.0o.image
%wait:research.0o.audio %q(1.5x, w=0.25) #gh:gh_sase-org__sase You are the linker agent
for a research swarm. The lead researcher, `research.0o.final`, has written a
consolidated report on the request below. Your job is to publish that report as the
canonical `<name>.md`: the file readers open, and the one SASE renders into a Highlights
PDF. You are an editor, not a researcher. The new file must carry exactly the lead's
meaning and intent. Do not do research of your own: add no new claims or sources, settle
no open questions, and neither soften nor strengthen the conclusions or the
recommendation. If the lead seems wrong, leave it as written. The only prose you write
yourself is the short research-query summary of the request that opens the file (step
3).

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it, but summarize it as the file's
research query in step 3):

I would like to make the case that Hermes can do everything that sase can and that the
smart move (for just about any user except for many me) would be to not bother with
sase.

Can you do some research with the goal of supporting/refuting that claim? Make sure that
this analysis / comparison is based on the feature sets of each product. Do not consider
popularity / adoption. End your analysis with a recommendation. If you think sase
realistically might have a role to play (as a tool used by many, not just me), justify
why and describe what that role is.

The lead researcher's registered report:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

The image agent's registered images:

{% for a in wait.artifacts if a.kind == "image" %}

- wait_name={{ a.wait_name }} label={{ a.label }} vcs_relpath={{ a.vcs_relpath }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

The audio agent's narrated edition:

{% if agents is defined %}{% for key, outputs in agents.items() if outputs.audio is defined %}

- agent={{ key }} audio={{ outputs.audio }} {% endfor %}{% endif %}
  {% for a in wait.artifacts if a.kind == "file" and a.label and a.label.startswith("audio:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} path={{ a.path }} ref={{ a.ref }}
  {% endfor %}

Steps:

1. **Identify the source.** From the registered reports above, find exactly one entry
   with `wait_name` `research.0o.final` whose label has the form
   `research:<YYYYMM>/<name>/<name>__final.md`. If there is not exactly one such entry,
   stop and report the missing or ambiguous input instead of guessing. Open the research
   repo with `/sase_repo`, then read the report through its canonical research reference
   (or the `ref` field's `file:<id>` reference if the original has moved) using
   `sase artifact read`. Take `<YYYYMM>/<name>/` from the label, never from the current
   date. Do not read predecessor chat transcripts. Never modify, move, or delete
   `<name>__final.md` or the drafts.

2. **Inventory what must survive.** Before writing, list every finding, recommendation,
   caveat, open question, confidence statement, number, date, version, code block,
   table, and link in the lead's report.
3. **Restructure** the lead's report into a well-thought-out organization:
   - Keep the frontmatter, updating `updated_time` if present.
   - **Open the file in this exact order**, with nothing else between these parts: the
     frontmatter (if any), one `#` title, the research query, the listen card, the
     infographic, and then the bottom-line section.
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
   - **Listen card.** Facts come from the `audio` variable of `research.0o.audio` when
     `ok` is true. If the variable is missing but an `audio:<episode_id>` artifact is
     listed, recover the facts with `sase listen ls <episode_id> --json` (or
     `sase-listen ls <episode_id> --json`, or `uvx sase-listen ls <episode_id> --json`):
     `audio.duration_s`, chapter count, `script.edition`. If `ok` is false or nothing is
     listed, publish with no card and no `audio:` frontmatter, and say so in the final
     response (never write "audio pending"). Add this frontmatter mapping (create a
     frontmatter block if the lead's report has none), copying numbers verbatim, never
     inventing them:

     ```yaml
     audio:
       edition: brief
       duration_s: 250.34
       chapter_count: 3
       episode_id: a-listen-link-for-research-reports-d74298
     ```

     No library path, MP3 path, feed URL, artifact id, or `file:` ref — the research
     repo is public. Insert the card exactly once, directly below the research-query
     blockquote and above the infographic, with the blank lines shown (they make GitHub
     and pandoc parse the inner Markdown):

     ```markdown
     <div class="listen">

     ♫ **Brief audio edition** · 4 min · 3 chapters · [Narration
     script](<name>_narration.md)

     </div>
     ```

     Rules: edition word capitalized (`Brief` / `Full`); minutes =
     `max(1, round(duration_s / 60))`; `1 chapter` singular; drop the chapters segment
     if the count is unknown; include the script segment only when `<name>_narration.md`
     exists beside the report in the research checkout; nothing else inside the div; not
     a heading; not inside the blockquote; never a link to an MP3, library path, feed
     URL, or `highlights://` URI.

   - **Embed the infographic** exactly once, directly above the bottom-line section:
     after the listen card and before that section's `##` heading, never further down.
     Use a relative link with descriptive alt text, for example
     `![<alt text>](<name>_infographic.png)`. Locate it by the `<name>_infographic.png`
     convention or the image entries above. Embed only a file you have confirmed exists
     beside the report in your research checkout. If the image agent completed without
     producing one, publish without it (the listen card then sits directly above the
     bottom-line section) and say so in the final response.
   - **Bottom-line section.** The first `##` section is `## Bottom line` (or
     `## Overview` when the report surveys options rather than giving one answer) and
     gives the answer first.
   - Below it, `##` and `###` sections ordered by the questions a reader will ask, with
     duplicated passages merged.
   - **Never number headings.** The PDF renderer runs pandoc with `--number-sections`,
     so hand-numbered headings render doubly numbered.
   - **No table of contents and no block of jump links.** The PDF already gets a TOC.
   - Keep the lead's wording where it works. Never drop a claim, caveat, or source to
     save space. If the lead's report restates the question or lists its inputs, keep
     those details in a later section; the research query summarizes the request but
     does not replace them.

4. **Validate every link carried over.**
   - Relative links resolve from `<YYYYMM>/<name>/`, and in-document anchors resolve
     against the final headings. Both are hard requirements.
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

6. **Re-check against the step-2 inventory** and restore anything missing or changed.
   Every URL in `<name>__final.md` must appear in the new file unless it was listed as
   unrepairable. Then confirm the file opens in the step-3 order: title, research query,
   listen card, infographic, bottom-line section.

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
├── <name>.md
└── <name>_narration.md
```
