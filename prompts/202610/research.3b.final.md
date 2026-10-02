- **AGENTS:**
  - [bbugyi200.athena.research.3b.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3b.final/README.md)

%id(final, clan=research.3b) %m:@xlarge %wait:research.3b.cdx %wait:research.3b.cld
%wait:research.3b.grk %wait:research.3b.mus %wait:research.3b.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to improve the "Agents" tab deck panel and the sase pager's split view
support (see the sase-1eg epic bead for context on the latter).

- We currently only support two views, each of which support just two panes: horizontal
  and vertical.
- I want to add a support for two additional views that each use three panes. Namely:
  - A horizontal split 3-pane view should be triggered when the `|` keymap is used if a
    horizontal split is already shown by splitting the currently focused pane
    vertically. Pressing `|` again should switch to the 3-pane view described in the
    bullet below. Alternatively, pressing `\` closes the larger horizontal pane which
    switches us to the 2-pane vertical view.
  - A vertical split 3-pane view should be triggered when the `\` keymap is used if a
    vertical split is already shown by splitting the currently focused pane
    horizontally. Pressing `\` again should switch to the 3-pane view described in the
    bullet above. Alternatively, pressing `|` closes the larger vertical pane which
    switches us to the 2-pane horizontal view.
- The `<ctrl+b>` keymap should be added that worked like the `<ctrl+f>` keymap (i.e.
  changes which pane is focused) but in the reverse direction.
- The new `<ctrl+shift+b/f>` keymaps should be added to give the user the ability to
  swap the current pane with the previous/next pane.
- A new `<ctrl+shift+d>` keymap should be added that deletes the current pane. This
  keymap should only be active when at least two panes are visible. We should still
  support switching back to a single-pane view when the `\` keymap is used but the
  2-pane horizontal view is already active or when the `|` keymap is used but the 2-pane
  vertical view is already active.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.3b.cdx`,
   `research.3b.cld`, `research.3b.grk`, `research.3b.mus`, `research.3b.gem`
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
   `research.3b.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3b.linker`, can find it:

   `sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"`

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
└── <name>__final.md
```
