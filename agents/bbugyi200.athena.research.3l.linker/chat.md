# Chat History - ace-run (research.3l.linker)

- **TIMESTAMP:** 2026-10-04 16:43:08 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3l.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_145503.md`

## Prompt

%id(linker, clan=research.3l) %m:@xlarge
%wait:research.3l.final %wait:research.3l.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.3l.final`, has written a consolidated report on the request below. Your job
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

Can you help me dig into the research sidecar repo for all research swarms that Gemini
models contributed to (the files they produced end with `__gem.md`) and find ones (if
any) where Gemini provided unique insights that the other models in the swarm did not
that were actually included in the final research report? End your analysis with a list
of those research files and a summary of what unique contributions Gemini made to them.

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
   with `wait_name` `research.3l.final` whose label has the form
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

I've opened the research repo and read the lead's final report. Next I'll inventory it and restructure it.

Every relative link in the lead's report resolves. It has no external URLs and no frontmatter, the infographic exists, and nothing sits at the target path yet. Now I'll write the restructured report.

Now I'll validate the anchors, links, and content against the original.

The structure renders correctly, and the Tier B list continues at 13. Registering the snapshot:

Registration succeeded. Now the final declaration.

I published the lead's report as the canonical file at `202610/gemini_only_insights_in_research_swarm_finals/gemini_only_insights_in_research_swarm_finals.md` in the research sidecar. It's registered as `file:explicit:0334dcd95040c12b02cfde89`, and the host will commit it after this turn ends. I didn't change, move or delete the lead's `__final.md` or the drafts.

**Opening order:** title, a two-sentence research query, the infographic, then `## Bottom line`. The infographic exists next to the report and is embedded once, by relative link. The lead's report had no frontmatter, so I added none.

**Restructuring (wording otherwise kept):**
- **Header block:** the lead's Date / "Lead synthesis of" / Question lines moved into a new "Question and inputs" subsection under "Scope and method".
- **Subsection headings:** the bold labels Corpus, Rules, Verification, the five kinds of kept work, the rejected proposals and Swarm size became `###` headings.
- **Renamed headings:** I removed colons, counts and letter prefixes so the headings work as link targets and the PDF doesn't number them twice:
  - "A. Clear cases (12)" became "Tier A clear cases".
  - "B. Qualified cases (5)" became "Tier B qualified cases".
  - "Final list: …" became "Final list of research files".
- **Counts:** moved from the headings into each section's first line, using the lead's own wording.
- **Final list:** stays at the end, as the request asked. Items 1–17 keep their numbering, and Tier B still starts at 13 in the rendered output.
- **Links between sections:** I added a few, mostly from the bottom line to the sections that back it, and from the method and limits sections to the swarm lists.

**Checks:**
- **Content:** I compared every line of the lead's report against the new file. The only differences are the intended ones: inserted links, renamed headings and re-wrapped lines. No claim, number, table row, caveat or link was dropped.
- **Links:** all 21 relative links from the lead's report are kept and resolve: the 4 drafts and the 17 swarm reports. The lead's report has no external URLs, and no link needed repair.
- **Anchors:** all 11 in-document links resolve under both pandoc and GitHub. A pandoc run with `--number-sections` showed no double numbering.
