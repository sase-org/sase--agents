- **AGENTS:**
  - [bbugyi200.apollo.research.h.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.h.final/README.md)

%clan(research.h, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] We currently
support collapsing the nav sidebar on the "Agents" tab via the `<ctrl+s>` keymap.

- We also support zooming in on a single deck using the `Z` keymap, in which case the
  sidebar is also collapsed.
- When the sidebar is collapsed, it is completely invisible currently.
- This is the correct behavior when zoomed, but should not be the default format used
  when collapsing the sidebar using the `<ctrl+s>` keymap.
- Instead, every tribe, agent group (e.g. "Running"), and node should be represented
  still, just in a collapsed, fixed width state.
- I'm thinking we can use some of the icons we already support (and maybe add a few more
  if needed--for example, I'm not sure if every type of agent group has a corresponding
  icon) to accomplish this, but you should decide. Think hard about what the best UX for
  this is.
- As a part of this change, let's make it clearer (in a visually appealing way) when a
  deck is zoomed (so the user can't mistakenly think the sidebar is just collapsed).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.h.final %m:@xlarge %wait:research.h.cdx %wait:research.h.cld
%wait:research.h.grk %wait:research.h.mus %wait:research.h.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

We currently support collapsing the nav sidebar on the "Agents" tab via the `<ctrl+s>`
keymap.

- We also support zooming in on a single deck using the `Z` keymap, in which case the
  sidebar is also collapsed.
- When the sidebar is collapsed, it is completely invisible currently.
- This is the correct behavior when zoomed, but should not be the default format used
  when collapsing the sidebar using the `<ctrl+s>` keymap.
- Instead, every tribe, agent group (e.g. "Running"), and node should be represented
  still, just in a collapsed, fixed width state.
- I'm thinking we can use some of the icons we already support (and maybe add a few more
  if needed--for example, I'm not sure if every type of agent group has a corresponding
  icon) to accomplish this, but you should decide. Think hard about what the best UX for
  this is.
- As a part of this change, let's make it clearer (in a visually appealing way) when a
  deck is zoomed (so the user can't mistakenly think the sidebar is just collapsed).
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
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.h.cdx`,
   `research.h.cld`, `research.h.grk`, `research.h.mus`, `research.h.gem` dependencies,
   matching by `wait_name` and the canonical research label's existing `__<suffix>.md`
   suffix. Never reassign suffixes from list order. Open the research repo with
   `/sase_repo`, then read each report through its canonical research reference (or the
   `ref` field's `file:<id>` reference if the original has moved) using
   `sase artifact read`. Do not read predecessor chat transcripts. If the records above
   do not identify exactly one report per expected suffix, stop and report the missing
   or ambiguous input instead of guessing.
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
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```
