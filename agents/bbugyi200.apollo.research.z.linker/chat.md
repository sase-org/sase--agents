# Chat History - ace-run (research.z.linker)

- **TIMESTAMP:** 2026-10-01 01:57:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.z.linker
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_005538.md`

## Prompt

%id(linker, clan=research.z) %m:@xlarge
%wait:research.z.final %wait:research.z.image %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the linker agent for a research swarm. The lead researcher,
`research.z.final`, has written a consolidated report on the request below. Your job
is to publish that report as the canonical `<name>.md`: the file readers open, and the
one SASE renders into a Highlights PDF. You are an editor, not a researcher. The new
file must carry exactly the lead's meaning and intent. Do not do research of your own:
add no new claims or sources, settle no open questions, and neither soften nor
strengthen the conclusions or the recommendation. If the lead seems wrong, leave it as
written.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request (context only; do not research it):

I
need a way to generate audio content from markdown files (like the research produced by
agents that is stored in the research sidecar repo, for example). I would like to listen
to this content while commuting / walking.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

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
   with `wait_name` `research.z.final` whose label has the form
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

Reading the lead's report now; next I'll check the raw file's frontmatter and links, then write the restructured canonical version.

Next I'll check every external URL in the report with curl.

The Google AI docs URLs loop through an auth redirect without cookies. I'll retry them with a cookie jar and check the redirect types.

Written. Next I'll check anchors with pandoc, relative links, the URL set, and number/code-token coverage against the lead's report.

Anchors, relative links, and all 41 URLs check out. The only numbers that dropped are the old section numbers and §-references. Next, a word-level diff to catch any wording I dropped by accident.

The diff shows only headings, links, and moved blocks; no claims were lost. I'll do a final rendering check of the nested table and the numbered lists that continue across phases.

Rendering is correct: all 10 tables are present (including the nested length-budget table), and the phase lists start at 6 and 9. Now I'll register the artifact.

Registered. Now the final declaration.

I published the canonical report at `202610/commute_audio_from_markdown/commute_audio_from_markdown.md` and registered it as `file:explicit:50784bf8bb1ddaa804f2664d`, labeled `research:202610/commute_audio_from_markdown/commute_audio_from_markdown.md`. It will be committed to the research repo after this turn ends. I did not modify `__final.md` or the drafts.

**What changed in the structure**
- The report now opens with the title and a one-line date/type note, then the bottom line. The infographic sits right after the bottom line; I confirmed the file is next to the report.
- After that, sections run in the order a reader would ask: question and scope (including what the lead verified), points all five reports agreed on, the script question and the corpus data, the narration-script contract, voice engine and monthly cost, packaging, getting audio to the phone, where the code lives and how it's triggered, existing tools to borrow from, the phased plan (each phase has its own heading, plus the live checks still owed), risks, open questions, corrections to individual reports, and sources.
- Headings are no longer numbered and there is no table of contents. Bold labels the lead used as mini-headings became `###` headings. I moved durations and version numbers out of headings into each section's first line.
- I replaced the "§2" and "Section 9" references with in-document links. I added a few more links from the bottom-line points, the Kokoro agreement, the "37 hours" figures, the phase mentions and gem's mastering details. The `(§6)` inside the quoted prototype output is unchanged, because it's a quotation.

**Content checks**
- A word-level diff against `__final.md` found only heading and link changes and moved blocks. No claim, caveat, number, table, code block or source was dropped. The only numbers removed are the old section numbers and §-references.
- I added relative links to the five drafts, the prior 202606 audio report and the admin-center report. All of them exist.

**Link checks**
- All 41 external URLs from `__final.md` are in the new file, and all work.
- The five `ai.google.dev` pages got stuck in a sign-in redirect loop until curl kept cookies, then returned 200.
- The two Tailscale help-page links and the Artificial Analysis leaderboard link redirect but load fine, so I kept the lead's URLs.
- No link was unrepairable and none needed repair.
- pandoc found every in-document anchor in both its GFM and standard Markdown modes. With `--number-sections`, the phase lists still start at 6 and 9, and all 10 tables render.
