# Chat History - ace-run (research.1g.final)

- **TIMESTAMP:** 2026-10-15 10:05:36 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1g.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091709.md`

## Prompt

%clan(research.1g, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
have been thinking that some of sase's memories should be migrated to documentation in
markdown files in the docs/ directory (the sase/memory/macros.md memory file, for
example), that I should consider making project documentation a first-class
representation of memory (we should manage it in a similar way, for example), and that I
should do a better job of structuring my documentation so its maintainance is more
intuitive and scriptable (via agents).

Can you do some research with the goal of finding some articles/papers that will help
inspire me on this front? End your analysis with a ranked list of articles/papers that
you think I should consider reading.]]) %id:research.1g.final %m:@xlarge
%wait:research.1g.cdx %wait:research.1g.cld %wait:research.1g.grk %wait:research.1g.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
have been thinking that some of sase's memories should be migrated to documentation in
markdown files in the docs/ directory (the sase/memory/macros.md memory file, for
example), that I should consider making project documentation a first-class
representation of memory (we should manage it in a similar way, for example), and that I
should do a better job of structuring my documentation so its maintainance is more
intuitive and scriptable (via agents).

Can you do some research with the goal of finding some articles/papers that will help
inspire me on this front? End your analysis with a ranked list of articles/papers that
you think I should consider reading.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.1g.cdx`, `research.1g.cld`, `research.1g.grk`, `research.1g.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.1g.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1g.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

Reading the four researcher reports now (two of four done); next I'll do my own gap research and write the consolidated report.

I've read all four reports; now checking the local `macros.md` memory and the doc-refresh routine so I can settle the factual disagreements between them.

Verified the uncertain citations (all real; two were mischaracterized by one report). Now checking Bryan's reading library before ranking.

Moved the four reports into `202610/project_docs_as_managed_memory_reading_list/`. Writing the consolidated report now.

Now registering the consolidated report as a durable artifact.

Registration succeeded. Submitting the final declaration.

I've written the consolidated report and registered it for the linker agent (`file:explicit:a5b92e4c436203b735ca209d`). The host will commit the research repo after this turn ends.

**Layout:** `202610/project_docs_as_managed_memory_reading_list/` holds the four researcher reports, renamed to `…__cdx.md`, `…__cld.md`, `…__grk.md` and `…__gem.md`, plus `…__final.md`. I matched each report to its `wait_name` before moving it.

**Main conclusions:**
- **"First-class" means giving docs what memory already has, not moving files.** That means a stable path plus anchor, a `type:`, a trigger-style description, an owner and review date, audited reads, authored links, a reviewed write path, and mechanical drift checks.
- **"Migrating `macros.md`" is really three moves:**
  - Delete the policy lines that core memory and the `decisions` web already hold.
  - Keep a smaller cheat sheet in memory, tied to the sections of `docs/macros.md` it summarizes so changes there get flagged.
  - Make `docs/macros.md` the single full reference, split by Diátaxis type one page at a time.
- **Don't retire the memory note.** Agents rarely open classical docs on their own: 10.6% of their documentation interactions (Gao & Chen). In Vercel's evals, an on-demand docs skill was never invoked in 56% of cases. The memory note is what points agents into `docs/` today.
- **For scriptable maintenance, cheap mechanical checks come first.** Their findings should feed one-page agent tasks, not today's whole-repo `refresh_docs` passes. Agent-written docs keep a human review gate: in one industrial study, 11 of 13 practitioners rejected agent output nobody had reviewed.

**Disagreements I resolved:**
- **Folders:** gem wanted to reorganise `docs/` into four Diátaxis directories. I went with a `type:` field and page-at-a-time changes, because Diátaxis itself warns against building empty structure first.
- **Always-loaded index:** Vercel's evals and Cochran's study seem to conflict. They measure different things. The answer is a short pointer in always-loaded text, not a full catalogue of docs.
- **Automation papers:** gem ranked RepoAgent and DocAgent highly, but they generate per-function code docs, not prose user docs. I demoted them.

**Corrections made:**
- gem misdescribed three sources. CODESYNC is about updating LLMs' knowledge of changing APIs, not documentation drift, so I dropped it. ReadMe.LLM's "up to 100%" is a success rate in one case study, not an improvement. "Cascade" is real (Kiecker et al., FSE 2026) but was cited without authors or a link.
- grk was wrong that `docs/llms.md` is an llms.txt-style file; it's the LLM-provider integration page. grk also called `cli.md` and `configuration.md` generated; they're hand-maintained.
- cld's count of top-level docs pages was off: there are 55, not 65.
- All the new 2026 arXiv papers the reports cite, including A-SAW from six days ago, are real. I checked their abstract pages.

**Ranked list, top items:**
1. Diátaxis
2. *Software Engineering at Google*, ch. 10, with Google's docs style guide
3. Gao & Chen, *From Agent Behaviour to Agent-Friendly Documentation*
4. Karpathy's LLM Wiki
5. Tan, Wagner & Treude on detecting outdated code references, plus their DOCER GitHub Action

Then KCS "Reuse is Review", A-SAW, Baker's *Every Page is Page One*, Cochran (with the Vercel post), and AdDoc.

I added two practical items the researchers didn't have: **cog** (auto-generated sections inside hand-written Markdown, with `--check` in CI) and **Swimm**'s docs that stay tied to the code they describe.

Library check: 5 of 49 candidates already in your library (1 finished).

Four other reports on a related question appeared in `202610/` from a different dispatch. I didn't read or move them.
