# Chat History - ace-run (research.40.linker)

- **TIMESTAMP:** 2026-10-07 14:17:39 EDT
- **MODEL:** claude/opus
- **AGENT:** research.40.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_130213.md`

## Prompt

%id(linker, clan=research.40) %m:@xlarge
%wait:research.40.final %wait:research.40.image %wait:research.40.audio %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.40.final`, has written a consolidated report on the request below. Your job
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

I've been thinking that some of the builtin routines and/or jobs that exist currently
might be better suited as service procs. For example, wouldn't it be better if the
`wait_checks` job was instead a service proc that could wake up agents that are ready
sooner?

Can you do some research with the goal of recommending which jobs (if any) I should
migrate to service procs? Also, critique this plan in general. Is this a good idea?
Would you take a different approach? Make any adjustments to the requirements that you
think are justified but clearly call these out. End your analysis with a recommended
solution.

The lead researcher's registered report:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

The image agent's registered images:

{% for a in wait.artifacts if a.kind == "image" %}
- wait_name={{ a.wait_name }} label={{ a.label }} vcs_relpath={{ a.vcs_relpath }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}


The audio agent's narrated edition:

{% if agents is defined %}{% for key, outputs in agents.items() if outputs.audio is defined %}
- agent={{ key }} audio={{ outputs.audio }}
{% endfor %}{% endif %}
{% for a in wait.artifacts if a.kind == "file" and a.label and a.label.startswith("audio:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Steps:

1. **Identify the source.** From the registered reports above, find exactly one entry
   with `wait_name` `research.40.final` whose label has the form
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
   - **Open the file in this exact order**, with nothing else between these parts: the frontmatter (if any), one `#` title, the research query, the listen card, the infographic, and then the bottom-line section.
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
   - **Listen card.** Facts come from the `audio` variable of `research.40.audio`
     when `ok` is true. If the variable is missing but an `audio:<episode_id>`
     artifact is listed, recover the facts with `sase-listen ls <episode_id> --json`
     (or `uvx sase-listen …`): `audio.duration_s`, chapter count, `script.edition`.
     If `ok` is false or nothing is listed, publish with no card and no `audio:`
     frontmatter, and say so in the final response (never write "audio pending").
     Add this frontmatter mapping (create a frontmatter block if the lead's report
     has none), copying numbers verbatim, never inventing them:

     ```yaml
     audio:
       edition: brief
       duration_s: 250.34
       chapter_count: 3
       episode_id: a-listen-link-for-research-reports-d74298
     ```

     No library path, MP3 path, feed URL, artifact id, or `file:` ref — the research
     repo is public. Insert the card exactly once, directly below the research-query
     blockquote and above the infographic, with the blank lines shown (they make
     GitHub and pandoc parse the inner Markdown):

     ```markdown
     <div class="listen">

     ♫ **Brief audio edition** · 4 min · 3 chapters · [Narration
     script](<name>_narration.md)

     </div>
     ```

     Rules: edition word capitalized (`Brief` / `Full`); minutes =
     `max(1, round(duration_s / 60))`; `1 chapter` singular; drop the chapters
     segment if the count is unknown; include the script segment only when
     `<name>_narration.md` exists beside the report in the research checkout;
     nothing else inside the div; not a heading; not inside the blockquote; never
     a link to an MP3, library path, feed URL, or `highlights://` URI.
   - **Embed the infographic** exactly once, directly above the bottom-line section:
     after the listen card and before that section's `##` heading, never further
     down. Use a relative link with descriptive alt text, for example
     `![<alt text>](<name>_infographic.png)`. Locate it by the
     `<name>_infographic.png` convention or the image entries above. Embed only a file
     you have confirmed exists beside the report in your research checkout. If the
     image agent completed without producing one, publish without it (the listen
     card then sits directly above the bottom-line section) and say so in the final
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
   unrepairable. Then confirm the file opens in the step-3 order: title, research query, listen card, infographic, bottom-line section.

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
├── <name>.md
└── <name>_narration.md
```

## Response

I've read the lead's report. Next I'm checking the raw file for frontmatter, then I'll restructure it into the canonical file.

Inputs are confirmed: the report, infographic, narration script and audio facts. Next I'm writing the restructured canonical report.

I'm tidying the subsections where the bold lead-in now repeats the new heading.

Now validating anchors with pandoc and diffing the content inventory against the lead's report.

Registration succeeded. Now submitting the final declaration.

I published the lead's report as the canonical `202610/wait_wakeup_jobs_vs_service_procs/wait_wakeup_jobs_vs_service_procs.md` and registered it as `file:explicit:917da6edd54806049e634c91`. The host will commit it to the research repo after this turn ends.

**How the file opens:** frontmatter, title, a research-query summary of your request, the listen card, the infographic, then `## Bottom line`.
- **Frontmatter:** the lead's report had none, so I created one holding only the `audio:` mapping (brief, 269.6 s, 3 chapters, `waking-waiting-agents-sooner-b2b0f6`).
- **Listen card:** Brief audio edition · 4 min · 3 chapters, with a link to the narration script.
- **Infographic:** embedded once, with descriptive alt text.

**Restructure:** the sections now follow the questions a reader will ask:
1. Bottom line
2. Where the time actually goes
3. What I re-verified
4. Critique of the plan in general
5. How the five reports line up
6. Resolving the disagreements
7. Adjusted requirements
8. Recommended solution (Phase 0–3, the parallel admission track, and the "leave everything else as jobs" table)
9. Confidence and open questions
10. Scope and inputs
11. Sources

The recommended solution stays at the end of the analysis, as you asked. I took the hand numbering out of the headings. Where the lead began a paragraph with a bold label (for example the plugin aside and the job count), that label became a `###` heading and I removed the repeated bold line. The intro paragraph listing the five reports, the sase revision and the measurement window moved to "Scope and inputs".

**Links:**
- The lead's report had no external URLs, so there was nothing to check or repair.
- Both relative links (the infographic and the narration script) point to files that exist beside the report.
- I added 19 in-document links, replacing the `§5`/`§8` cross-references and linking the bottom-line points, phases, R1/R7 and "see below" mentions. pandoc confirmed every anchor resolves.

**Fidelity:** I compared every word, number and code span against the lead's file. Nothing was dropped. The only differences are the removed heading numbers, the `§` references that became links, and the bold labels that became headings. I added no claims or sources and did not change the conclusions.

The infographic, narration script and audio edition were all available, so nothing was left out. I did not modify the lead's `__final.md` or the drafts.
