# Chat History - ace-run (research.6e.final)

- **TIMESTAMP:** 2026-11-25 14:49:04 EST
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.6e.final
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_141135.md`

## Prompt

%clan(research.6e, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The decisions memory web for this project and the bob-cli project is taking up way too
much context for each sase agent. I would like to mitigate this somehow.

- These decisions should probably only be read by planner agents (i.e. agents that use
  the /sase_plan skill). Note, however, that we can not modify the /sase_plan skill
  directly with these instructions since it is used by all sase projects (most of which
  will not have this custom decisions memory web).
- It follows that we should stop rendering the full decisions roster in agent
  instruction bundles.
- The decisions memory is just a specific memory web though, which we should not add
  custom support for, so we need to be able to handle memory webs like this generically
  (i.e. for any memory web we want).
- The best solution I can think of is to configure the decisions memory so it stops
  rendering the roster and instead renders instructions that state that any agent that
  is writing a SASE plan (i.e. invoked the /sase_plan skill) MUST read the decisions
  memory roster. This "decisions memory roster" should be retrievable by running a
  `sase memory` command and should look a lot like the roster that is currently in the
  AGENTS.md file. I'm not sure if we have an appropriate `sase memory` command for this
  yet (if not, you should add one).
- We will need to make sure that we audit this memory web roster read and display it in
  the TUI in the appropriate place.
- As a part of this change, we should update the decisions memories appropriately for
  both of these projects (sase and bob-cli).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.6e.final %m:claude-fable-5
%wait:research.6e.cdx %wait:research.6e.cld %wait:research.6e.grk %wait:research.6e.mus %wait:research.6e.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The decisions memory web for this project and the bob-cli project is taking up way too
much context for each sase agent. I would like to mitigate this somehow.

- These decisions should probably only be read by planner agents (i.e. agents that use
  the /sase_plan skill). Note, however, that we can not modify the /sase_plan skill
  directly with these instructions since it is used by all sase projects (most of which
  will not have this custom decisions memory web).
- It follows that we should stop rendering the full decisions roster in agent
  instruction bundles.
- The decisions memory is just a specific memory web though, which we should not add
  custom support for, so we need to be able to handle memory webs like this generically
  (i.e. for any memory web we want).
- The best solution I can think of is to configure the decisions memory so it stops
  rendering the roster and instead renders instructions that state that any agent that
  is writing a SASE plan (i.e. invoked the /sase_plan skill) MUST read the decisions
  memory roster. This "decisions memory roster" should be retrievable by running a
  `sase memory` command and should look a lot like the roster that is currently in the
  AGENTS.md file. I'm not sure if we have an appropriate `sase memory` command for this
  yet (if not, you should add one).
- We will need to make sure that we audit this memory web roster read and display it in
  the TUI in the appropriate place.
- As a part of this change, we should update the decisions memories appropriately for
  both of these projects (sase and bob-cli).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

When you author or carry over Mermaid diagrams, load `/mermaid_diagrams` before
drafting, even when no image or diagrams companion runs. The skill has the shared
figure-selection, styling, and PDF-render review rules. If the provider skill is not
deployed, verify the edited plugin's guide with `sase macro show skill/mermaid_diagrams --format raw` (or
`sase macro show /mermaid_diagrams --format raw`) and use the form this host supports.
This guidance does not enable a companion diagrams agent.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

First run `sase repo open research -r "Write the swarm research reports"` and use
the path it prints as `<research checkout>`. The month directory is
`<research checkout>/202611`; create it if missing.

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.6e.cdx`, `research.6e.cld`, `research.6e.grk`, `research.6e.mus`, `research.6e.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Read each report through its canonical research reference (or the `ref` field's
   `file:<id>` reference if the original has
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
   agent `research.6e.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.6e.linker`, can find it:

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

## Response

I'm the lead researcher consolidating five swarm reports on deferring memory-web rosters out of agent instruction bundles. Let me start by opening the research checkout and reading the registered reports.

The checkout is ready. Now I'll read all five reports through their canonical research references.

I have grk and mus in full. The cdx, cld, and gem reports were saved to files; let me read them.

Now the gem report.

Reports are in place. Now I'll author and render the figure for the consolidated report.

The figure rendered at 614×990 px, fit 90.2% (above the 75% floor). Let me review the PNG visually.

Now registering the consolidated report as a durable artifact for the linker agent.

The report is registered. Final step: submit the SASE finalizer declaration.

The context requires one commit declaration for the research repo. Submitting it.

Consolidation complete. The final report is at `202611/on_demand_web_rosters/on_demand_web_rosters__final.md` in the research repo (registered as `file:explicit:918a3073cdc44cc4d692e922`), with all five swarm reports moved alongside it as `on_demand_web_rosters__{cdx,cld,grk,mus,gem}.md` plus their figure assets, and the commit declared for host completion.

**The verdict:** all five researchers — and I — agree your plan is right and that the architecture anticipated it: the reopen clause of `decisions:webs-render-in-their-own-section` names exactly this situation. The numbers are stark and cross-verified: the decisions roster is 38% of sase's bundle (~2.1k tokens) and 69% of bob-cli's (~6.4k tokens), bob-cli is already 4.5 KB over Codex's cap with compaction firing on every turn, and it adds ~30 records a month — so for bob-cli this is a reliability problem, not just cost.

**Where I overruled or arbitrated the swarm:**

- **Command shape** was a five-way split. I adopted grk's `sase memory read roster:<web>` selector: zero new commands, it batches in one audited event, and I verified in code that the TUI MEMORY lane already renders selector-only events and pages a generated report — so audit and TUI display come nearly free. Runner-up is gem's `sase memory web read <web> [PATTERN]`; the one thing that would flip the choice is wanting audited *filtered* roster reads in v1 (open question 4 for you).
- **AGENTS.md** gets the stub too (grk alone said keep the full roster there). I re-read `readable-agents-md` myself: AGENTS.md is "the full runtime projection" — a mirror of the bundle, and live delivery for agy/Qwen/OpenCode where decisions is 72% of bob-cli's file. The on-disk descriptor keeps its full managed roster for humans.
- **Audit encoding**: v1 stays on schema v3 (`kind="web"`, `roster:` selector, empty `included_targets`), avoiding the sase-core change entirely — three reports confirmed the Rust audit reader silently drops unknown kinds, so the no-new-kind path is both less work and less risk. First-class `kind="roster"` is queued v2 polish.

**Two requirement adjustments, clearly called out:** planner-only is too narrow (telemetry shows researchers make 46–78% of decision reads; the rule becomes planners + design researchers read the roster, plans cite governing records, implementers read what's cited), and one project-agnostic sentence should go into `/sase_plan` step 1 — it never mentions decisions, is a no-op for other projects, and fires at the moment of planning, which a standing AGENTS.md sentence does not. I also adopted gem's bare-web guard: agents have already burned 142–205 KB per accidental `sase memory read decisions`, so on-demand webs refuse the bare read without `-a/--all-strands`.

cld's `sase plan validate` enforcement backstop, titles-only compact mode, and snapshot-fidelity work are all specified but deferred with explicit triggers, per `corpus-before-mechanism`. The report ends with four open questions for you, the biggest being whether bob-cli accepts that its decision rules stop being ambient for unplanned work (recommended, paired with promoting the release-train rule into a tiny always-loaded gotchas note).
