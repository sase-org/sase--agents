# Chat History - ace-run (research.42.linker)

- **TIMESTAMP:** 2026-10-08 17:44:28 EDT
- **MODEL:** claude/opus
- **AGENT:** research.42.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_163448.md`

## Prompt

%id(linker, clan=research.42) %m:@xlarge
%wait:research.42.final %wait:research.42.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.42.final`, has written a consolidated report on the request below. Your job
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

I
need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command.

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
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
   with `wait_name` `research.42.final` whose label has the form
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

I'll start by opening the research repo via the `/sase_repo` skill.

The infographic exists alongside the report. Now I'll read the lead's report through its canonical reference.

Next I'll validate the draft: anchors against the pandoc heading ids, URL carry-over, heading constraints, and a line-level content diff against the source.

All 23 anchor links resolve, the headings meet the constraints, and all six URLs carried over. Now I'll run a word-level diff to confirm no claim was dropped or altered.

Written, and the drafts are untouched. Now I'll register the durable snapshot.

Registration succeeded. Now I'll submit the final declaration.

I published the lead's report as `202610/just_install_pypi_dev_venv_split/just_install_pypi_dev_venv_split.md` and registered it as `research:202610/just_install_pypi_dev_venv_split/just_install_pypi_dev_venv_split.md` (`file:explicit:fce19e5ea917b6b6d6754e36`). The commit is declared and the host will make it after this turn. `__final.md`, the five drafts and the image were not touched.

- **Source:** exactly one `research.42.final` entry matched, and I read it with `sase artifact read`. It had no frontmatter, so there was no `updated_time` to update.
- **Opening order:** title, then a three-sentence research query, then the infographic (`just_install_pypi_dev_venv_split_infographic.png`, confirmed to exist beside the report), then `## Bottom line`.
- **Structure:** Bottom line, Critique of the plan (what's right, what's wrong or missing (P1–P7), alternatives, and the rejected-alternatives table placed next to them), What exists today, What this consolidation adds, Changes to your requirements, Recommended design (seven subsections), Where the reports disagreed, Migration plan, Acceptance tests, Open questions, Recommended solution, Sources.
- **Wording and numbering:** I removed the hand-written heading numbers and moved code and punctuation out of headings. The lead's date and commit line now opens Sources. A word-level diff against `__final.md` shows no content dropped or changed, so the meaning and the recommendation are exactly as the lead wrote them.
- **Links:**
  - The lead's `§3`, `§5.3`, `§9`, "step 7", "P1" and "finding N" cross-references are now in-document links.
  - I added a few links from summary points to the sections behind them. There are 23 in total, and all resolve against the headings pandoc generates.
  - All six external URLs returned OK with `curl` and are all kept. The only relative link is the infographic.
  - There are no repository-file links and no links I couldn't repair.
