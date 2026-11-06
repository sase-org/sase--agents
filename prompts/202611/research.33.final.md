- **AGENTS:**
  - [bbugyi200.apollo.research.33.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.33.final/README.md)

%clan(research.33, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like
to add support for "hijacking" a stalled sase agent.

- An "agent hijack" (aka "hijack"--we should add a good new glossary term for this) is
  meant to describe the process of killing a sase agent without releasing its workspace
  or dismissing it.
- The agent node should then be rendered with the new "HIJACKED" status on the "Agents"
  tab.
- If the `<enter>` keymap is used when a "HIJACKED" agent is selected a new panel should
  be triggered that allows the user to select (with a single keypress) between one of
  the following options. Think hard about what other options (if any) this panel should
  support:
  - Restart the agent by dismissing it (and releasing its workspace) and relaunching it
    using the exact same prompt.
  - Dismiss (and release the workspace) and edit the agent prompt (similar to what the
    `,x` keymap does).
  - Escalate to a smarter model. We should use the `@xlarge` model alias if the `@large`
    model alias was used for the previous prompt; otherwise, we should use the `@large`
    model alias. We should NOT release the workspace in this case since the smarter
    model needs to have access to all of the previous agent's file changes.
- We may want to add support for one or more new sase config fields to support this new
  functionality, but I'll let you decide.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.33.final %m:@xlarge %wait:research.33.cdx %wait:research.33.cld
%wait:research.33.grk %wait:research.33.mus %wait:research.33.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to add support for "hijacking" a stalled sase agent.

- An "agent hijack" (aka "hijack"--we should add a good new glossary term for this) is
  meant to describe the process of killing a sase agent without releasing its workspace
  or dismissing it.
- The agent node should then be rendered with the new "HIJACKED" status on the "Agents"
  tab.
- If the `<enter>` keymap is used when a "HIJACKED" agent is selected a new panel should
  be triggered that allows the user to select (with a single keypress) between one of
  the following options. Think hard about what other options (if any) this panel should
  support:
  - Restart the agent by dismissing it (and releasing its workspace) and relaunching it
    using the exact same prompt.
  - Dismiss (and release the workspace) and edit the agent prompt (similar to what the
    `,x` keymap does).
  - Escalate to a smarter model. We should use the `@xlarge` model alias if the `@large`
    model alias was used for the previous prompt; otherwise, we should use the `@large`
    model alias. We should NOT release the workspace in this case since the smarter
    model needs to have access to all of the previous agent's file changes.
- We may want to add support for one or more new sase config fields to support this new
  functionality, but I'll let you decide.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

When you author or carry over Mermaid diagrams, load `/mermaid_diagrams` before
drafting, even when no image or diagrams companion runs. The skill has the shared
figure-selection, styling, and PDF-render review rules. If the provider skill is not
deployed, verify the edited plugin's guide with
`sase macro show skill/mermaid_diagrams --format raw` (or
`sase macro show /mermaid_diagrams --format raw`) and use the form this host supports.
This guidance does not enable a companion diagrams agent.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.33.cdx`,
   `research.33.cld`, `research.33.grk`, `research.33.mus`, `research.33.gem`
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
   `research.33.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.33.linker`, can find it:

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
└── <name>__final.md
```
