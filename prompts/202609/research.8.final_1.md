- **AGENTS:**
  - [bbugyi200.apollo.research.8.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.8.final/README.md)

%clan(research.8, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add
a new `"` keymap to the "Agents" tab that opens a new panel which makes it very easy to
navigate to any node, regardless of whether or not it is show. We should be able to jump
to hidden agent session shells and hidden agent clan members, for example. Don't include
agent shell Bash/Python steps.

- This panel should have similar (but more powerful) functionality to the panel that is
  triggered by the backtick keymap in that hints will always be rendered next to nodes
  that the user can jump to by pressing the corresponding keys.
- This functionality will be more powerful in that we will support filtering the list
  (by node name) via a query input bar at the top of the panel.
- By default, the query input bar should not be selected (so the user can press hint
  keys). The `<tab>` keymap should be able to be used to focus the query input bar and
  then unfocus it again to press hint keys.
- The user should also be able to use the `<enter>` keymap to select (and jump to) the
  currently selected node.
- This panel should be large so we can show a good (but fast) preview of the currently
  selected node
- The user should be able to cycle through the nodes listed in the panel using the
  `<ctrl+n/p>` keymaps.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.8.final %m:@xlarge %wait:research.8.cdx %wait:research.8.cld
%wait:research.8.mus %wait:research.8.gem %q(w=0.25) #gh:gh_sase-org__sase You are the
lead researcher: 4 independent researchers have reported on the request below, and you
will add your own research and merge every perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to add a new `"` keymap to the "Agents" tab that opens a new panel which makes it
very easy to navigate to any node, regardless of whether or not it is show. We should be
able to jump to hidden agent session shells and hidden agent clan members, for example.
Don't include agent shell Bash/Python steps.

- This panel should have similar (but more powerful) functionality to the panel that is
  triggered by the backtick keymap in that hints will always be rendered next to nodes
  that the user can jump to by pressing the corresponding keys.
- This functionality will be more powerful in that we will support filtering the list
  (by node name) via a query input bar at the top of the panel.
- By default, the query input bar should not be selected (so the user can press hint
  keys). The `<tab>` keymap should be able to be used to focus the query input bar and
  then unfocus it again to press hint keys.
- The user should also be able to use the `<enter>` keymap to select (and jump to) the
  currently selected node.
- This panel should be large so we can show a good (but fast) preview of the currently
  selected node
- The user should be able to cycle through the nodes listed in the panel using the
  `<ctrl+n/p>` keymaps.
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
   cdx, cld, mus, gem, belonging to this dispatch's `research.8.cdx`, `research.8.cld`,
   `research.8.mus`, `research.8.gem` dependencies, matching by `wait_name` and the
   canonical research label's existing `__<suffix>.md` suffix. Never reassign suffixes
   from list order. Open the research repo with `/sase_repo`, then read each report
   through its canonical research reference (or the `ref` field's `file:<id>` reference
   if the original has moved) using `sase artifact read`. Do not read predecessor chat
   transcripts. If the records above do not identify exactly one report per expected
   suffix, stop and report the missing or ambiguous input instead of guessing.
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
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```
