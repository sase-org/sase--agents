# Chat History - ace-run (research.09.linker)

- **TIMESTAMP:** 2026-10-04 11:06:55 EDT
- **MODEL:** claude/opus
- **AGENT:** research.09.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_095726.md`

## Prompt

%id(linker, clan=research.09) %m:@xlarge
%wait:research.09.final %wait:research.09.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.09.final`, has written a consolidated report on the request below. Your job
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

I need to think of a new name for sase (which conflicts with the Secure Access Service
Edge project). I doubt that I will go with a name that is longer than 8 characters.
Bonus points for any names shorter than 8 characters, but how well the name matches with
what sase is/does as a product is more important than name length (up to around 8
characters, that is).

Can you do some research with the goal of helping me pick the best possible new name for
sase? Also, critique this plan in general. Is this a good idea? End your analysis with a
ranked list of the 10 best names that you think that I should consider (and a
recommendation on whether I should move forward with this rename or not).

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
   with `wait_name` `research.09.final` whose label has the form
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
     image agent completed without producing one, publish without it (the research
     query then sits directly above the bottom-line section) and say so in the final
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
├── <name>__gem.md
├── <name>__final.md
├── <name>_infographic.png
├── <name>.md
└── <name>_narration.md
```

## Response

Read the lead's report and confirmed the link targets and infographic exist. Next I'm looking at the infographic for alt text and checking a prior published report for its conventions.

Draft written. Now validating anchors with pandoc and diffing the URL set against the lead's report.

All 16 anchors resolve and the link set matches the lead's exactly. Next: a word-level diff to catch any dropped content, plus external URL checks.

23 of 26 return 200. Three need a closer look: Cisco investor (429, so it stays as unverified), Check Point (404), and NRI Senju (DNS failure). Rechecking those two and the GitHub repo links.

Opening order is correct and no heading is numbered. One rendering issue to check: the lead's literal `<condition>` placeholder may be parsed as raw HTML and vanish from the PDF.

The placeholder now renders. Final URL reconciliation, then a no-clobber copy into place.

The file is written and the only URLs missing are the two unrepairable ones. Now verifying relative links from the file's own directory, then registering it.

Registered. Now submitting the final declaration.

I've published the lead's report as `202610/sase_rename_new_name_shortlist/sase_rename_new_name_shortlist.md` in the research repo and registered it as `file:explicit:7e83974c578774c29686478c`. The host commits the file after this turn ends.

**How it opens:** the title, then a two-sentence research-query blockquote, then the infographic (it exists beside the report), then `## Bottom line`.

**What changed from the lead's version:**
- **Section order:** Bottom line → Is renaming a good idea → What the name has to carry → Ranked top 10 → Recommendation and two-week decision procedure → Where the researchers disagreed → Consolidated graveyard → Method and limits → Sources.
- **Headings:** none are numbered. Each of the ten names has its own `###` heading, and its rank and tagline (e.g. "#1 · `handful` — recommended") moved to the first line under it.
- **Date and type line:** it used to sit above the bottom line, so it moved to the top of "Method and limits".
- **Section references:** the lead's "§" references became anchor links. "See below" for `stichos` now says "see its entry above", because the graveyard now comes after the top 10.
- **New in-document links:** from the bottom-line points to the sections behind them, and from the top-10 table to each name's section.
- **`<condition>` placeholder:** I escaped it, because pandoc treated it as HTML and dropped it from the output.
- **Content:** a word-level diff against the lead's report shows only expected changes (heading case and numbering, words now inside link text, dropped `---` dividers). No claim, number or caveat was lost.

**Link checks:**
- All 16 anchors resolve under pandoc, and all 7 relative links resolve from the report's folder.
- The six GitHub repo links were confirmed by opening each repo with `sase repo open`.
- 23 of the 26 other external links return 200.
- One is unverified but kept: the Cisco "AI-Aware SASE" investor page returned 429 (rate-limited) twice.
- Two are dead. I kept their text, removed the URLs, and didn't look for replacements:
  - **Check Point SASE Agent** (`sc1.checkpoint.com/.../Using-Agent.htm`): the server returns a real 404.
  - **NRI Senju Family** (`senjufamily.nri.com/sen/`): the domain doesn't resolve (NXDOMAIN on 1.1.1.1).

Apart from those two, every URL in the lead's report is in the new file. I didn't modify the lead's report or the drafts.

One thing I left alone because it isn't my call as editor: the report says "Days 1–7: live with each name", but the infographic's timeline says "Days 1–13".
