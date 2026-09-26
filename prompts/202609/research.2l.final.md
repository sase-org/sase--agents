- **AGENTS:**
  - [bbugyi200.athena.research.2l.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2l.final/README.md)

%clan(research.2l, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Once card
blocks are fully implemented (see the sase-19x epic bead for context), I want to improve
the UX to make it clear whether the spread or paged view is enabled for a deck and/or
card. I also want to add one or more new keymaps that allow the user to toggle through
the 3 states (fully spread, paged deck and spread card, paged deck and paged card).

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about what the best UX for this functionality is. End your analysis
with a recommended solution.]]) %id:research.2l.final %m:@xlarge %wait:research.2l.cdx
%wait:research.2l.grk %wait:research.2l.mus %wait:research.2l.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 4 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Once card blocks are fully implemented (see the sase-19x epic bead for context), I want
to improve the UX to make it clear whether the spread or paged view is enabled for a
deck and/or card. I also want to add one or more new keymaps that allow the user to
toggle through the 3 states (fully spread, paged deck and spread card, paged deck and
paged card).

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about what the best UX for this functionality is. End your analysis
with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, grk, mus, gem, belonging to this dispatch's `research.2l.cdx`,
   `research.2l.grk`, `research.2l.mus`, `research.2l.gem` dependencies, matching by
   `wait_name` and the canonical research label's existing `__<suffix>.md` suffix. Never
   reassign suffixes from list order. Open the research repo with `/sase_repo`, then
   read each report through its canonical research reference (or the `ref` field's
   `file:<id>` reference if the original has moved) using `sase artifact read`. Do not
   read predecessor chat transcripts. If the records above do not identify exactly one
   report per expected suffix, stop and report the missing or ambiguous input instead of
   guessing.
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```
