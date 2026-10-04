# Chat History - ace-run (research.w.linker)

- **TIMESTAMP:** 2026-09-30 19:37:19 EDT
- **MODEL:** claude/opus
- **AGENT:** research.w.linker
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_183649.md`

## Prompt

%id(linker, clan=research.w) %m:@xlarge
%wait:research.w.final %wait:research.w.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.w.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it):

One
of the best reads I've ever had related to sase was actually the SASE paper
(2509.06216). It has been a while since I've delved into relevant literature (e.g.
papers, articles) and I am curious as to what related progress has been made in the
industry over the last 6-12 monthes.

Can you do some research with the goal of recommending 10 high-value, recent papers
and/or articles on similar topics that I am likely to understand, appreciate, and learn
from? Prioritize quality over recency but do not recommend any papers or articles that
were published more than a year ago.

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
   with `wait_name` `research.w.final` whose label has the form
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
   - One `#` title, then the bottom line or answer first.
   - `##` and `###` sections ordered by the questions a reader will ask, with
     duplicated passages merged.
   - **Never number headings.** The PDF renderer runs pandoc with `--number-sections`,
     so hand-numbered headings render doubly numbered.
   - **No table of contents and no block of jump links.** The PDF already gets a TOC.
   - Keep the lead's wording where it works. Never drop a claim, caveat, or source to
     save space.
   
   - Embed the infographic exactly once, where it best supports the text (usually
     right after the bottom line). Use a relative link with descriptive alt text, for
     example `![<alt text>](<name>_infographic.png)`. Locate it by the
     `<name>_infographic.png` convention or the image entries above. Embed only a file
     you have confirmed exists beside the report in your research checkout. If the
     image agent completed without producing one, publish without it and say so in the
     final response.
   
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
   unrepairable.

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

Read the lead's report (647 lines, 10 picks plus companions). Next I'll check the raw file for frontmatter, then inventory the links and validate them.

All 46 non-OpenAI URLs return 200; openai.com returns 403 on both tries, so I'll keep it as unverified. Now I'll check the infographic so I can write accurate alt text.

The infographic matches the report. Next I'll write the restructured report.

Now I'll check the anchors against pandoc's heading IDs and confirm every source URL made it into the new file.

Anchors, headings, URLs, and the image link all check out. Next I'll compare the numbers and emphasis in both files to make sure nothing was dropped.

Registration worked. Last step is the final declaration.

I've published the lead's report as `202609/sase_paper_followup_reading_list/sase_paper_followup_reading_list.md` and registered it as `research:202609/sase_paper_followup_reading_list/sase_paper_followup_reading_list.md` (ref `file:explicit:e7206e97770c46c7c9c45bb2`). The host commits it after this turn; `__final.md` and the drafts were not touched.

**What changed:**
- **Order:** bottom line, infographic, anchor and window, the ten at a glance, suggested reading order, the ten recommendations, beyond the ten (the SASE authors' follow-ups and honorable mentions), how the five reports were reconciled, then method and confidence.
- **Headings:** I removed all heading numbers. Where a pick's full title had punctuation that can't be in an anchor, I shortened the heading and put "Pick #N:" plus the full title on the section's first line.
- **Byline:** there was no frontmatter. The lead's byline (lead researcher synthesis · 2026-09-30, the five inputs, about 45 citations checked) moved to the start of "Method and confidence" so the bottom line comes first.
- **Cross-references:** the lead's "§6" and "§4/§5" references are now links to the renamed sections.

**New links inside the document:** the five bottom-line findings link to the picks that back them, "If you read only one" links to #1 and #3, each title in the at-a-glance table links to its section, and a few "see below" style mentions link to their sections. Every anchor resolves in `pandoc -t html` with no duplicate IDs.

**Infographic:** `sase_paper_followup_reading_list_infographic.png` exists beside the report and is embedded once, right after the bottom line, with descriptive alt text.

**Checks against the lead's report:**
- All 47 URLs are carried over, with none dropped or added.
- 46 of them returned 200 with no redirects.
- `https://openai.com/index/harness-engineering/` returned 403 on both tries. I kept it as unverified; the lead also noted that openai.com blocks direct fetches.
- No link was unrepairable.
- The table cells match the lead's exactly.
- Every other sentence and number is carried over. The only rewording is the removed heading numbers, the "§" references now written as links, and the byline and two heading parentheticals moved into body text.
