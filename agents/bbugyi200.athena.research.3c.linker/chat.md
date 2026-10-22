# Chat History - ace-run (research.3c.linker)

- **TIMESTAMP:** 2026-10-02 14:03:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3c.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124120.md`

## Prompt

%id(linker, clan=research.3c) %m:@xlarge
%wait:research.3c.final %wait:research.3c.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.3c.final`, has written a consolidated report on the request below. Your job
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

I would like to add
excellent support for the recently added memory file history functionality to the TUI
(see the sase-1dr epic bead for context). I'm pretty sure sase's pager is the only thing
that supports memory history at the moment. Can you do some research with the goal of
helping me decide the best way to implement this? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! End your analysis with a
recommended solution.

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
   with `wait_name` `research.3c.final` whose label has the form
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
     paths, xprompt or directive syntax, and formatting requests. Summarize what was
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
├── <name>__mus.md
├── <name>__gem.md
├── <name>__final.md
├── <name>_infographic.png
└── <name>.md
```

## Response

I've opened the research repo and read the lead's final report through `sase artifact read`. Next I'll read the full text so I can list everything that has to carry over.

I've confirmed the infographic exists beside the report and matches the registered image. Now I'm writing the restructured canonical report.

The canonical report is written with no collision, and pandoc renders it cleanly. Next I'll register it as a durable artifact.

Registration worked. I'll finish with the final declaration.

I've published the canonical report and registered it as a durable artifact. The host will commit it to the research repo after this turn.

- **File:** `202610/memory_history_tui_support/memory_history_tui_support.md`, written without overwriting anything. The lead's `__final.md` and the drafts are untouched.
- **Registration:** `sase artifact create` succeeded with label `research:202610/memory_history_tui_support/memory_history_tui_support.md` and ref `file:explicit:4e79facd2cdd8eae4acc08d2`.
- **Opening order:** title, then a one-blockquote research query, then the infographic, then `## Bottom line`. The infographic is `memory_history_tui_support_infographic.png`, linked relatively with descriptive alt text. It sits beside the report and is byte-identical to the image agent's registered image.

**What I changed in the structure:**
- **Merged sections:** the lead's "Decision brief" and its closing "Recommended solution" said much the same thing, so I merged them into one Bottom line. It keeps:
  - the five parts ordered by value;
  - the shared-history-service paragraph;
  - the three deferrals;
  - the four things not to build;
  - the closing intuitive/reliable/beautiful rationale.

  Each detail that appeared in only one of the two (such as the violet past frame, the `AGENTS.md as launched` row, "o always edits now", and "never audited") went into the merged items.
- **Moved provenance:** the opening paragraph about the swarm's five reports, the `8d1ac50c51` revision, and `sase-1dr` now heads the Evidence ledger.
- **New order:** the "Where the reports disagreed" section now comes after the design, as the rationale for it.
- **Section numbers removed:** every heading number and internal `§` reference is gone. I replaced the references with 12 in-document links, and all of them resolve. Pandoc's markdown and GitHub-flavoured anchor generation agree on every heading, there are no duplicate anchors, and the file renders with `--number-sections`.
- **Headings cleaned up:** I took code and parentheses out of headings used as link targets. The removed details now open their sections instead, for example "Lead measurements: warm, this checkout, in-process `HistoryService`" and "The Timeline lens opens with `@`."

**Inventory check:** all 5 code blocks and 9 tables carried over. The only table cells that changed are the four that used `§` references, which are now links. A scripted comparison of code spans, numbers, and words against the lead's file found no lost content beyond the intended changes: the merged duplicates, the removed section numbers, and the renamed headings. References to the original plan's own sections (§4.5, §4.8, §16, §18) stay as written.

**Links:** the lead's report had no external URLs and no relative or repository-file links, so there was nothing to check with curl and no link was unrepairable.
