- **AGENTS:**
  - [bbugyi200.athena.research.2q.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2q.final/README.md)

%clan(research.2q, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add
support for dynamic sub-tabs to the "Agents" tab.

- We should add the `%tab:<tab_name>` directive to support this.
- If the `%tab` directive is not used explicitly in the prompt used to launch a sase
  agent, then we should default to launching that agent on a special "main" tab.
- If there is only one tab that has agents on it, then we should not show any tabs at
  all (i.e. keep the current behavior).
- Machine Tabs
  - We should add a new "machine tabs" glossary memory web term that describes this
    concept.
  - When remote machines are configured on the current machine, we should automatically
    show `local` instead of `main` for the main tab for agents that were launched on the
    current machine. For remote agents, we should automatically replace `main` with
    `<machine_name>` where `<machine_name>` is that machine's configured name.
  - A good icon should be rendered next to the machine tabs in the sub-tab title bar on
    the "Agents" tab (this includes "local").
  - Any agents that are launched with the `%tab:<tab_name>` directive should always use
    `<tab_name>` as their tab (on all machines). This will allow us to, for example,
    group all agents related to a particular project on a single tab regardless of which
    machine each agent ran on.
- We should not support an "ALL" sub-tab that shows all agents. Instead, we should
  modify the `o` option in the panel that is shown when the `o` keymap is used on the
  "Agents" tab. Namely, we should add support for a 3rd view that merges all tribes and
  all tabs (instead of just all tribes) into a single panel. This option should also
  support its current behavior (merge all tribes--but do not merge tabs) by cycling
  through the 3 views. We should also add a new `O` option that does the same thing as
  the `o` option but in the opposite direction.
- Some previous research can be found in the agent_machine_tabs_and_cluster_semantics.md
  file in the research sidecar repo. This research file should be reviewed before
  performing your own research. Note, however, that this research file focuses too much
  on the specific case of machine tabs, does not prioritize dynamic tabs, and is not
  ambitious enough overall.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.2q.final %m:@xlarge %wait:research.2q.cdx %wait:research.2q.cld
%wait:research.2q.grk %wait:research.2q.mus %wait:research.2q.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to add support for dynamic sub-tabs to the "Agents" tab.

- We should add the `%tab:<tab_name>` directive to support this.
- If the `%tab` directive is not used explicitly in the prompt used to launch a sase
  agent, then we should default to launching that agent on a special "main" tab.
- If there is only one tab that has agents on it, then we should not show any tabs at
  all (i.e. keep the current behavior).
- Machine Tabs
  - We should add a new "machine tabs" glossary memory web term that describes this
    concept.
  - When remote machines are configured on the current machine, we should automatically
    show `local` instead of `main` for the main tab for agents that were launched on the
    current machine. For remote agents, we should automatically replace `main` with
    `<machine_name>` where `<machine_name>` is that machine's configured name.
  - A good icon should be rendered next to the machine tabs in the sub-tab title bar on
    the "Agents" tab (this includes "local").
  - Any agents that are launched with the `%tab:<tab_name>` directive should always use
    `<tab_name>` as their tab (on all machines). This will allow us to, for example,
    group all agents related to a particular project on a single tab regardless of which
    machine each agent ran on.
- We should not support an "ALL" sub-tab that shows all agents. Instead, we should
  modify the `o` option in the panel that is shown when the `o` keymap is used on the
  "Agents" tab. Namely, we should add support for a 3rd view that merges all tribes and
  all tabs (instead of just all tribes) into a single panel. This option should also
  support its current behavior (merge all tribes--but do not merge tabs) by cycling
  through the 3 views. We should also add a new `O` option that does the same thing as
  the `o` option but in the opposite direction.
- Some previous research can be found in the agent_machine_tabs_and_cluster_semantics.md
  file in the research sidecar repo. This research file should be reviewed before
  performing your own research. Note, however, that this research file focuses too much
  on the specific case of machine tabs, does not prioritize dynamic tabs, and is not
  ambitious enough overall.
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
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.2q.cdx`,
   `research.2q.cld`, `research.2q.grk`, `research.2q.mus`, `research.2q.gem`
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
