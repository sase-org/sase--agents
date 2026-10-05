- **AGENTS:**
  - [bbugyi200.apollo.research.0c.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0c.final/README.md)

%clan(research.0c, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm thinking
about adding / completing a major new faeature named "goals", which is partially
completed already (but that part may need modifications). My latest thinkng on this
subject can be found in the incomplete research prompt that I've stored in the
~/tmp/incomplete_goals_prompt.md file.

But I don't want you to design or research this feature. Instead, can you do some
research with the goal of finding some recent (<=1 year old) articles that you think are
likely to improve / inspire my thinking on this topic? End your analysis with a ranked
list of ten articles you think I should consider reading, with justification for
each.]]) %id:research.0c.final %m:@xlarge %wait:research.0c.cdx %wait:research.0c.cld
%wait:research.0c.grk %wait:research.0c.mus %wait:research.0c.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about adding / completing a major new faeature named "goals", which is
partially completed already (but that part may need modifications). My latest thinkng on
this subject can be found in the incomplete research prompt that I've stored in the
~/tmp/incomplete_goals_prompt.md file.

But I don't want you to design or research this feature. Instead, can you do some
research with the goal of finding some recent (<=1 year old) articles that you think are
likely to improve / inspire my thinking on this topic? End your analysis with a ranked
list of ten articles you think I should consider reading, with justification for each.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.0c.cdx`,
   `research.0c.cld`, `research.0c.grk`, `research.0c.mus`, `research.0c.gem`
   dependencies, matching by `wait_name` and the canonical research label's existing
   `__<suffix>.md` suffix. Never reassign suffixes from list order. Open the research
   repo with `/sase_repo`, then read each report through its canonical research
   reference (or the `ref` field's `file:<id>` reference if the original has moved)
   using `sase artifact read`. Do not read predecessor chat transcripts. If the records
   above do not identify exactly one report per expected suffix, stop and report the
   missing or ambiguous input instead of guessing.
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
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest
   findings from every report above and your own research, resolve conflicts, cut
   duplication, and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker agent
   `research.0c.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0c.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l
   "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails, report
   that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
├── <name>__final.md
└── <name>_narration.md
```
