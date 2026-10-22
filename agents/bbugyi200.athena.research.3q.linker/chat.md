# Chat History - ace-run (research.3q.linker)

- **TIMESTAMP:** 2026-10-06 11:54:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3q.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_104840.md`

## Prompt

%id(linker, clan=research.3q) %m:@xlarge
%wait:research.3q.final %wait:research.3q.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.3q.final`, has written a consolidated report on the request below. Your job
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

I'm looking for some recent (published within the last year) articles that will inspire
me to improve sase's memory files and agent instruction files. Can you do some research
with the goal of finding the articles that are most likely to do that? End your analysis
with a ranked list of articles that you think I should consider reading.

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
   with `wait_name` `research.3q.final` whose label has the form
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
└── <name>.md
```

## Response

Reading the lead's report is done. Next I'm checking the infographic and all external links, then I'll write the canonical file.

Checking the draft: comparing it line by line against the lead's text, checking that every URL carried over, and resolving anchors with pandoc.

Registered. Now the final declaration.

I've published the lead's report as the canonical file `202610/memory_and_instruction_file_inspiration_reading_list/memory_and_instruction_file_inspiration_reading_list.md` and registered it as `file:explicit:07e6e6f87a4d5e1d0ba293e2` under the label `research:202610/memory_and_instruction_file_inspiration_reading_list/memory_and_instruction_file_inspiration_reading_list.md`. The research repo commit is declared; the host makes it after this turn ends.

**What changed from the lead's version**
- **Opening:** the file starts with the title, then a one-sentence research query, then the infographic, then `## Bottom line`. The infographic was in the research checkout and is embedded once with descriptive alt text. The lead's date, publication window and question lines moved into a new "Scope and method" section.
- **Section order:** bottom line, where sase stands today, themes, idea backlog, scope and method, where the reports agreed and disagreed, caveats, then the ranked reading list. The list goes last because you asked for the analysis to end with it, which also makes the lead's "at the end" link accurate.
- **Headings:**
  - I removed the hand numbering on the seven theme headings.
  - Headings that had colons or code in them are shorter now, and their extra wording moved to the section's first line. For example, "Staleness" now opens with "*Especially in the `decisions` web.*" and "Tier 3" opens with "*Skim for specific angles.*"
  - The numbering of the 32 reading-list items is unchanged.
- **In-document links:** I added 11 links:
  - from the bottom-line points to the themes and reconciliation sections that back them
  - from "see below", "(below)" and "the table above" to their targets
  - from "Tier 3" to the Tier 3 section
- **Content:** a line-by-line comparison against the lead's text found nothing dropped. The only differences are the heading changes above.

**Link check**
- All 41 external URLs from the lead's report are kept, and pandoc confirms all 13 in-document anchors resolve.
- 38 URLs returned 200 on the first try. The two O'Reilly links returned 403 on the first try and 200 on the retry.
- **Unverified (kept):** `https://openai.com/index/harness-engineering/` returned 403 both times. The report already says this page blocks automated fetchers.
- **Unrepairable:** none.
- Two URLs redirect but still work, so I left them as written so every original URL survives. The Steering Claude Code blog post now lives under `claude.com/resources/articles/…`, and the other redirect only adds a trailing slash.
