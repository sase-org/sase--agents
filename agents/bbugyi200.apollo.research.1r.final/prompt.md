%clan(research.1r, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
recently did some research related to the creation of a new `sase project stats` command
(see the project_stats_cli_design.md file in the research sidecar repo for context).

- This research was performed before I had fully fleshed out the requirements.
- This command should be named `sase stats project` instead of `sase project stats` (the
  `sase stats` command will be new).
- My long-term goal (the entirety of which is out-of-scope for your research) is to make
  it so the data from every sub-tab on the "Statistics" tab of the "SASE Admin Center"
  panel is accessible via a `sase stats` sub-command that fetches the data using the
  same code paths as the TUI.
- As a part of this initial change, we will set ourselves up for this work by migrating
  the "Projects" sub-tab to use the same data source as the new `sase stats project`
  command.
- I forgot to mention that this command should also track how many commits were made by
  each model/provider and how many plans were committed by each model/provider.
- I also forgot to mention that sidecar repos should not be counted by default (for most
  stuff at least--we are still interested in which models were used to create approved
  plans though). A CLI option should be added that specifies that this command should
  count statistics for sidecar repos as well.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.1r.final %m:@xlarge
%wait:research.1r.cdx %wait:research.1r.cld %wait:research.1r.grk %wait:research.1r.mus %wait:research.1r.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
recently did some research related to the creation of a new `sase project stats` command
(see the project_stats_cli_design.md file in the research sidecar repo for context).

- This research was performed before I had fully fleshed out the requirements.
- This command should be named `sase stats project` instead of `sase project stats` (the
  `sase stats` command will be new).
- My long-term goal (the entirety of which is out-of-scope for your research) is to make
  it so the data from every sub-tab on the "Statistics" tab of the "SASE Admin Center"
  panel is accessible via a `sase stats` sub-command that fetches the data using the
  same code paths as the TUI.
- As a part of this initial change, we will set ourselves up for this work by migrating
  the "Projects" sub-tab to use the same data source as the new `sase stats project`
  command.
- I forgot to mention that this command should also track how many commits were made by
  each model/provider and how many plans were committed by each model/provider.
- I also forgot to mention that sidecar repos should not be counted by default (for most
  stuff at least--we are still interested in which models were used to create approved
  plans though). A CLI option should be added that specifies that this command should
  count statistics for sidecar repos as well.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.1r.cdx`, `research.1r.cld`, `research.1r.grk`, `research.1r.mus`, `research.1r.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1r.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1r.linker`, can find it:

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
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```