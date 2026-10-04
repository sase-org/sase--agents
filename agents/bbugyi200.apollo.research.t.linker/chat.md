# Chat History - ace-run (research.t.linker)

- **TIMESTAMP:** 2026-09-30 14:35:29 EDT
- **MODEL:** claude/opus
- **AGENT:** research.t.linker
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_132759.md`

## Prompt

%id(linker, clan=research.t) %m:@xlarge
%wait:research.t.final %wait:research.t.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.t.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it):

It
is important that memory file changes are tracked, versioned, and easy to navigate /
understand. I would like to add support for this to sase.

- All agent instruction file changes and all memory file changes should be tracked. It's
  fine if we use git history for this to get this version-control data for free, but we
  need to be able to navigate between the different versions for each supported file
  very quickly (so we might need to create an index or something--think hard about the
  best way to solve this).
- I was thinking that we could add some sort of special support to sase's pager for
  memory files / agent instruction files and make that the main interface for navigating
  / viewing memory change history. Think hard about what the best UX for this looks
  like.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

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
   with `wait_name` `research.t.final` whose label has the form
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

Reading the lead's report is done. Next I'm checking the infographic and frontmatter, then restructuring the report into the canonical `memory_and_instruction_file_history.md`.

Links all return 200 and the infographic is present. Writing the restructured report now.

Every anchor and relative link resolves. The only non-conforming heading is the H1 title, and nothing links to it. Registering the artifact now.

Registered. Now submitting the final declaration.

I've published the lead's report as the canonical `202609/memory_and_instruction_file_history/memory_and_instruction_file_history.md` and registered it as `file:explicit:4a677d5bb57461853f2d4fdc`, with label `research:202609/memory_and_instruction_file_history/memory_and_instruction_file_history.md`. The host commits it to the research repo when this turn ends. I didn't touch `__final.md` or the drafts.

**Structure changes**
- The bottom line comes first, followed by the infographic. The infographic is embedded once, with descriptive alt text, and I confirmed the file is next to the report.
- The critique ("Is this a good idea") now comes before the requirement adjustments, because that's the reader's next question. I changed "the adjustments above" to a link to the adjustments below it.
- The rest follows the lead's order: evidence, data model and index, reliability rules, UX, where the reports disagreed, the phased plan, and the recommended solution with the open decisions. Sources are last, so the report still ends on the recommendation, as the user asked.
- Headings are no longer numbered, and punctuation, code and parentheticals moved out of them into each section's first line. Each phase now has its own subheading. The adoption-gate line moved to the top of the Phases section, and the "mockups are illustrative" note moved to the top of the UX section.
- Every "§N" cross-reference is now an in-document link. I added a few more sparse links: to the feed, the key map, phase 0 and 3, persistence, the reliability rules and the recommended solution. In Sources, I added relative links to the five swarm reports.
- The lead's report has no frontmatter, so there was no `updated_time` to update.

**Checks**
- A script compared the new file with the lead's: all 6 code blocks are byte-identical, all 77 table rows and all 6 URLs are present, and no code spans or numbers are missing. The only text differences are the planned heading, cross-reference and link edits.
- `pandoc -t html` builds cleanly. All 12 in-document anchors match headings, and all 6 relative links (five reports and the infographic) resolve.
- There is one H1 and no duplicate headings. The only heading that breaks the anchor rules is the lead's H1 title, which has an em dash, and nothing links to it.
- All 6 external URLs returned HTTP 200, so none needed repair or removal.
