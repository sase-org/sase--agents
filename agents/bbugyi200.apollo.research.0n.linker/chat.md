# Chat History - ace-run (research.0n.linker)

- **TIMESTAMP:** 2026-10-08 14:49:55 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0n.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_135159.md`

## Prompt

%id(linker, clan=research.0n) %m:@xlarge
%wait:research.0n.final %wait:research.0n.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.0n.final`, has written a consolidated report on the request below. Your job
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
would like to make the sase-listen repo a first-class sase plugin.

- To support this change, we should start allowing sase plugins to define sub-commands
  somehow.
- The sase-listen plugin should use this new functionality to define the `sase listen`
  command.
- This command should work exactly like the `sase-listen` command, but should support
  sase's CLI completion (make sure that completion is updated automatically when a
  plugin like this is installed).
- We should also start displaying this plugin on the "Updates" tab of the "SASE Admin
  Center" panel so users can manage its installation the same way they do for other sase
  plugins. I have already added the `sase--plugin` GitHub label on sase-listen's GitHub
  repo to support this.

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
   with `wait_name` `research.0n.final` whose label has the form
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

I've read the lead's report and confirmed the infographic exists. Now I'll write the restructured canonical file.

The source has no URLs or Markdown links, so the only link work is new in-document anchors. Writing the file now.

Validating anchors with pandoc and checking the content against the source inventory.

All anchors resolve. Now checking that every source line's content survived (normalized whitespace).

Registration worked. The research checkout now has a new untracked file, so I'll declare it in the final step.

I've published the lead's report as the canonical `202610/sase_listen_plugin_commands/sase_listen_plugin_commands.md` and registered it. It will be committed to the research repo when this turn ends.

**Source.** There was exactly one report from `research.0n.final`. I read it through `sase artifact read`. I did not touch `__final.md` or the drafts.

**Opening.** The file opens in the required order:
1. The title.
2. A short summary of your request, kept in your terms (including "label").
3. The infographic.
4. `## Bottom line`.

The infographic is `sase_listen_plugin_commands_infographic.png`, which sits beside the report, linked relatively.

**Changes to the structure:**
- **Section order:** Bottom line → What exists today → Critique of the plan → Adjusted requirements (R1–R9) → Recommended solution → Open questions for Bryan → Where the reports disagreed → Evidence base → Discovered issues.
- **Merged duplicate:** the lead's closing "Recommended solution" summary repeated most of the bottom line. I merged it into the bottom line and kept its extra points: the ~0.9 s saving, new shells versus `exec $SHELL`, the Updates-tab bullet, and the pre-rollout fixes. The detailed "Recommended solution" section is unchanged.
- **Moved to "Evidence base":** the lead's opening note about merging five reports, along with the verification table.
- **Headings:** I removed the hand numbering. Where a heading contained punctuation or code, I rewrote it as a clean link target and moved the detail into the first line. For example, "Completion freshness (R5)" became "Completion freshness" followed by "This implements R5."
- **Cross-references:** every `§x.y` reference is now an in-document link, and so are the R5, R6 and R9 mentions, the phasing steps, and links from the bottom line to the sections behind it.

**Checks:**
- **Links:** the lead's report had no URLs or relative links, so there were no external links to check and none were dropped. `pandoc` confirms every new anchor resolves, and no heading ID is duplicated.
- **Nothing dropped:** I compared the files line by line. The only differences are the reference-to-link rewrites and the merged closing summary, and each of those still has its claim, number and caveat. All 5 tables and both code blocks are intact. Nothing has a frontmatter `updated_time` to update.

The registered reference is `file:explicit:9aea76aebc74651f598f95fa`.
