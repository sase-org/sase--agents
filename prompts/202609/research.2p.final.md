- **AGENTS:**
  - [bbugyi200.athena.research.2p.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2p.final/README.md)

%clan(research.2p, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add
a new way of grouping agents on the Agents tab using sub-tabs.

- The motivation behind this change is to allow sase to scale up the number of agents
  that the user can manage from a single TUI instance.
- This will be useful, for example, in the case of nodes running on remote machines,
  where I would like them to use a tab that is named after the machine the node is
  running on (agents that are running on the apollo machine should show up on a sub-tab
  named something like "apollo", for example).
- This will require migrating the exisint `[` / `]` keymaps which are used for card
  blocks to `(` / `)` (so we can use the square bracket keys to navigate the new
  sub-tabs on the "Agents" tab).
- It's come to my attention that agent clans and agent tribes, just like these new
  sub-tabs, are really just a way of grouping a bunch of nodes together, unlike agent
  sessions, for example, which have a deeper conceptual meaning. I don't think that this
  codebase's logic reflects that. Agent clans in particular have some unique
  requirements that I think we should remove in order to unify the concept of agent
  groups/clusters (this new "agent clusters" term should be added to the glossary) that
  can be moved to and from clans/tribes/tabs in a seamless and intuitive way.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.2p.final %m:@xlarge %wait:research.2p.cdx %wait:research.2p.grk
%wait:research.2p.mus %wait:research.2p.gem %q(1.5x, w=0.25) #gh:gh_sase-org__sase You
are the lead researcher: 4 independent researchers have reported on the request below,
and you will add your own research and merge every perspective into one consolidated
report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to add a new way of grouping agents on the Agents tab using sub-tabs.

- The motivation behind this change is to allow sase to scale up the number of agents
  that the user can manage from a single TUI instance.
- This will be useful, for example, in the case of nodes running on remote machines,
  where I would like them to use a tab that is named after the machine the node is
  running on (agents that are running on the apollo machine should show up on a sub-tab
  named something like "apollo", for example).
- This will require migrating the exisint `[` / `]` keymaps which are used for card
  blocks to `(` / `)` (so we can use the square bracket keys to navigate the new
  sub-tabs on the "Agents" tab).
- It's come to my attention that agent clans and agent tribes, just like these new
  sub-tabs, are really just a way of grouping a bunch of nodes together, unlike agent
  sessions, for example, which have a deeper conceptual meaning. I don't think that this
  codebase's logic reflects that. Agent clans in particular have some unique
  requirements that I think we should remove in order to unify the concept of agent
  groups/clusters (this new "agent clusters" term should be added to the glossary) that
  can be moved to and from clans/tribes/tabs in a seamless and intuitive way.
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
   cdx, grk, mus, gem, belonging to this dispatch's `research.2p.cdx`,
   `research.2p.grk`, `research.2p.mus`, `research.2p.gem` dependencies, matching by
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
