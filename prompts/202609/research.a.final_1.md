- **AGENTS:**
  - [bbugyi200.apollo.research.a.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.a.final/README.md)

%id(final, clan=research.a) %m:opus@xhigh %wait:research.a.cdx %wait:research.a.cld
%wait:research.a.mus %wait:research.a.gem %q(w=0.25) #gh:gh_sase-org__sase You are the
lead researcher: 4 independent researchers have reported on the request below, and you
will add your own research and merge every perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Sase's finalizers are a critical part of a sase agent's lifecycle yet they are not
represented on the "Agents" tab in any way. I want to add excellent (and beautiful)
support to this tab for finalizers.

Can you do some research with the goal of helping me decide the best way to implement
this? Review the old agents_tab_finalizer_panel.md file in the research sidecar repo for
context and inspiration before performing your own research. Make sure to think hard
about what role decks, cards, and/or card blocks (card blocks are an upcoming
feature--see the agent_data_card_blocks.md file in the research sidecar repo for
context) should play (if any) in providing the user with an excellent way to visualize
and troubleshoot their own finalizers (I have several plans for new finalizers so make
sure you don't overfit this use-case to the builtin `commit` finalizer) . End your
analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, mus, gem, belonging to this dispatch's `research.a.cdx`, `research.a.cld`,
   `research.a.mus`, `research.a.gem` dependencies, matching by `wait_name` and the
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
