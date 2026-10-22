# Chat History - ace-run (research.38.linker)

- **TIMESTAMP:** 2026-10-01 15:47:01 EDT
- **MODEL:** claude/opus
- **AGENT:** research.38.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_145619.md`

## Prompt

%id(linker, clan=research.38) %m:@xlarge
%wait:research.38.final %wait:research.38.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.38.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it):

Can you help me
understand what the new sase-listen repo will actually provide to users that install it?
See the sase-1e3 epic bead for context. Make sure the report you produce is useful,
concise, and beautiful.

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
   with `wait_name` `research.38.final` whose label has the form
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

Source is located and read. There's no frontmatter and no external URLs. Next I'll check the infographic, then write the restructured report.

Written. Now I'll check the anchors with pandoc and compare the new file against the source to confirm nothing was lost.

The only differences are the added in-document links, the moved metadata, and the "Type" line reworded into a sentence. Next I'll register the snapshot.

Registration succeeded. Next I'll check the repo state and submit the final declaration.

I've published the restructured report as `202610/sase_listen_what_you_get/sase_listen_what_you_get.md` and registered it as `research:202610/sase_listen_what_you_get/sase_listen_what_you_get.md` (ref `file:explicit:b8eeb338b16d865e1fe18082`). The host commits it to the research repo after this turn. I did not change `__final.md` or the drafts.

**Structure**
- It opens with the title, a short Date · Context · Type line, then **Bottom line**: the lead's one-sentence summary and the four numbered points.
- The infographic is embedded once, right after the bottom line, with descriptive alt text. I confirmed `sase_listen_what_you_get_infographic.png` exists in the same folder.
- The sections follow the questions a reader would ask: how the pieces fit, what each install adds, the episode, who writes the words, setup, the CLI, cost, where you'll listen, what's not in v1, status on 2026-10-01, and what's worth deciding. **About this report** comes last and holds what the lead verified, where the reports disagreed, and the sources.
- I split some long sections into subsections: why the agent edition exists, what the normalizer does, planned quickstart, requirements, JSON output and exit codes, and feed privacy.
- I renamed three headings so they work as link targets: "Who writes the words: editions", "The CLI: planned versus today" and "Where you'll listen". The removed words now open the section text or the table instead.
- I added a few in-document links: from each bottom-line point to its section, and from the decisions, disagreements and narration-script text to the sections they refer to.

**Checks**
- All 10 in-document links resolve, and pandoc gives the same heading IDs in both the GitHub-flavored and standard Markdown modes. No heading is numbered and there's no table of contents.
- Every number and code block from the source is in the new file. The only text changes are the added links, the moved metadata line, and the "Type" line reworded into a sentence.
- The source has no external URLs (the `https://<host>:8443` inside a code block is a placeholder) and no links to repo files, so nothing needed checking and nothing was dropped as unrepairable.
- The source had no frontmatter, so there was no `updated_time` to update.
