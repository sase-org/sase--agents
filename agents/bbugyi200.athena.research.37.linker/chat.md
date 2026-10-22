# Chat History - ace-run (research.37.linker)

- **TIMESTAMP:** 2026-10-01 14:31:03 EDT
- **MODEL:** claude/opus
- **AGENT:** research.37.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_130220.md`

## Prompt

%id(linker, clan=research.37) %m:@xlarge
%wait:research.37.final %wait:research.37.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.37.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it):

Can you do some
research with the goal of helping me come up with ideas to improve the `#research_swarm`
xprompt swarm? Think hard about how this swarm can produce better research (e.g. by
digging into what it means to build a good research agent swarm) and think hard about
how this xprompt swarm can take better advantage of existing features provided by sase
(you can also recommend new sase features if they are truly justified). End your
analysis with a ranked list of improvements you think I should consider making.

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
   with `wait_name` `research.37.final` whose label has the form
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

I've opened the research repo and read the lead's report (503 lines). Next I'll inventory it, then restructure it.

Now I'll validate the anchors with pandoc, check that every URL and link survived, and run a word-level diff against the lead's text.

All 17 anchors resolve under both pandoc and GFM. Next, a word-level diff to confirm nothing from the lead's text was dropped or changed.

The layout matches and only the new file is untracked; the drafts and `__final.md` are unchanged. Now the final declaration.

I published the lead's report as `202610/research_swarm_improvement_roadmap/research_swarm_improvement_roadmap.md` in the research repo and registered it as `file:explicit:5c270f170c48b3464c2558b4`. The host will commit it after this turn ends.

- **Source:** exactly one `research.37.final` entry matched. I read it through `sase artifact read`, and it was identical to the copy in the checkout. The lead's `__final.md` and the five drafts are unchanged. The report had no frontmatter, so I added none.
- **Order:** the bottom line comes first, followed by the infographic. Then come the question and inputs, the evidence on what makes a swarm good, what this run showed about itself, the defects to fix first, and the recommendations. The disagreements table, rejected options, ranked improvements (kept at the end as the user asked), open questions, and sources follow.
- **Headings:** none are numbered and there is no table of contents. The failure-handling section's "Today / Now / Later / A risk to test now" lead-ins became four subheadings so they can be linked.
- **Wording changes:** a word-level diff against the lead's file shows the only changes are heading wording. I removed commas and one apostrophe so the headings work as anchors, for example "Make the lead an adjudicator rather than a merger" and "Telemetry cannot see the research of two providers". Every finding, number, table, bead, caveat and source is still there.
- **Infographic:** `research_swarm_improvement_roadmap_infographic.png` exists beside the report. It is embedded once, right after the bottom line, with descriptive alt text.
- **Links:**
  - All 18 external URLs returned HTTP 200, and all appear in the new file. The nature.com link only redirected to add a cookie parameter, so I kept the original URL.
  - All 6 relative links resolve: the five drafts and the 2026-09 linker report.
  - I added 15 in-document links: from bottom-line points, "see below" phrases, the disagreement rulings and each of ranked items 1–8 to their sections. All 17 anchors in the file resolve under both pandoc and GitHub-style rendering.
  - No link was dead or needed repair.
