# Chat History - ace-run (research.3p.final)

- **TIMESTAMP:** 2026-10-05 15:01:50 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3p.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_141626.md`

## Prompt

%clan(research.3p, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md,
  instruction_bundles_provider_parity_and_memory_ledger.md, and
  fresh_clone_bootstrap_and_native_subagent_instructions.md files in the research
  sidecar repo for context before performing your own research. I agree with all of the
  recommendations made in these research files for the most part, but you should call
  out any issues that you are able to identify.
- I think I want to split this work up into multiple epics with clear completion/exit
  criteria and verifiable results that are easy for me to confirm, but I'm not sure how
  this work should be split up or if it is even advisable to split this work up at all.

Can you do some research with the goal of helping me decide the best way to split this
work up (if at all)? End your analysis with a recommended set of epics (with clear
completion/exit criteria and verifiable results) or justification for why you don't
think that I should split up this work.]]) %id:research.3p.final %m:@xlarge
%wait:research.3p.cdx %wait:research.3p.cld %wait:research.3p.grk %wait:research.3p.mus %wait:research.3p.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md,
  instruction_bundles_provider_parity_and_memory_ledger.md, and
  fresh_clone_bootstrap_and_native_subagent_instructions.md files in the research
  sidecar repo for context before performing your own research. I agree with all of the
  recommendations made in these research files for the most part, but you should call
  out any issues that you are able to identify.
- I think I want to split this work up into multiple epics with clear completion/exit
  criteria and verifiable results that are easy for me to confirm, but I'm not sure how
  this work should be split up or if it is even advisable to split this work up at all.

Can you do some research with the goal of helping me decide the best way to split this
work up (if at all)? End your analysis with a recommended set of epics (with clear
completion/exit criteria and verifiable results) or justification for why you don't
think that I should split up this work.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3p.cdx`, `research.3p.cld`, `research.3p.grk`, `research.3p.mus`, `research.3p.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3p.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3p.linker`, can find it:

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
├── <name>__final.md
└── <name>_narration.md
```

## Response

Read cdx and cld reports; now reading grk, mus, and gem reports.

Read all five reports and the three prior reports. Now verifying the disputed claims myself: flag/epic rules, Rust boundary, monitor/gate provider calls, and CLI/TUI collisions.

Now registering the consolidated report as a durable artifact.

Yes, split it. The consolidated report recommends **five core epics, run in order, plus two optional ones**, and ends with exit criteria for each and commands you can run to confirm them.

## Recommended epics

| # | Epic | Changes agent behavior? | You can stop here |
|---|---|---|---|
| E1 | Instruction scoreboard and stopgaps (fix Grok getting no instructions, stop Claude helpers from finalizing) | Grok and Claude helpers only | Yes: the measured harms stop |
| E2 | Build instruction bundles in shadow mode (render and record, don't deliver) | No | — |
| E3 | Switch every provider to explicit delivery, with a kill switch per provider | Yes | **Yes: every SASE agent's instructions are built from memory at launch** |
| E4 | Retire the committed full files in sase: stub, sync, nested notes, Memory History | No | — |
| E5 | Home files (chezmoi), `bob-cli`, `actstat`, and `sase tmux-agent` | Interactive sessions only | **Yes: no full render committed or deployed anywhere** |
| E6 | *Optional:* TUI instruction visibility | No | — |
| E7 | *Only once a measured need exists:* audiences (`when:`) | Yes | — |

**Why split.** Size isn't the reason: epics here close in hours (median 3.3 h for 1–4 phases, 19 h for 9 or more). The reason is that an epic launches all its phases and its land agent at once, so it can't pause for days to watch real runs. The flag rules agree: a `beta` flag must be removed before its epic lands. Two points need several days of watching, after E1 and after E3, so those become epic boundaries. E2 keeps a renderer bug from reaching every agent before its output has been checked against today's files. E5 keeps your home environment out of the repo epic. If you'd rather approve fewer plans, three epics (E1; E2+E3; E4+E5) also works.

**Confirming each epic.** E1 builds one scoreboard command that reads what each provider actually loaded. Every later exit criterion is a specific change in its output, or a file count or fresh-clone check. The report includes a table of what the scoreboard should show after each epic. The whole program takes about 2–3 weeks, mostly the two waits and your reviews.

## Problems in the three earlier reports

The overall design holds. The report lists 15 issues; the five that change the plan most:
- **Grok stopgap:** the proposed fix would send Grok the SASE rules twice and still leave out the single-turn directive.
- **Per-provider flags:** "one epic with a flag per provider, then measure" breaks the flag rules. Use a `sunset` flag per provider instead.
- **Unscoped dependents:** none of the reports plans for the code that reads the tracked files: Memory History in sase-core, validators, CI, and the memory-write skill.
- **Claude auto-memory:** what an agent "remembers" depends on which `sase_<N>` workspace it got. This session loaded `sase_12`'s 15 notes. Claude 2.1.289 has a setting to turn it off.
- **Lean monitor/gate render:** monitor and gate turns never call a provider, so this audience doesn't exist.

## Things I found that no researcher mentioned
- An open bead, **`sase-1gj`**, already covers the Grok fix. Fold it into E1 rather than launching it as written: its suggested fix includes a setting that has no effect.
- `sase/memory/sase.md` is generated from a packaged template, so moving it into the package base costs little.
- Grok has its own memory store too: on in 77 of the 148 recent sessions, empty so far.
- grk's objection that the proposed TUI deck key is taken is wrong: `p` opens the picker and `y` is free.

## Housekeeping
- The five reports are in `202610/memory_built_instruction_migration_epics/` with their suffixes kept. I didn't edit them, so their relative links to the earlier reports now point one directory too shallow.
- The consolidated report is registered as `research:202610/memory_built_instruction_migration_epics/memory_built_instruction_migration_epics__final.md`.
- I did not create `<name>.md` or `<name>_narration.md`; those come from the later publishing step.
- The research-repo changes are declared for the host to commit.

Files are in `202610/memory_built_instruction_migration_epics/` in the research repo:
- memory_built_instruction_migration_epics__final.md
