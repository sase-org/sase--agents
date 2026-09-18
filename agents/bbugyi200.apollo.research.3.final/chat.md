# Chat History - ace-run (research.3.final)

- **TIMESTAMP:** 2026-09-17 14:45:10 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.3.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260917_141125.md`

## Prompt

%id(final, clan=research.3) %m:claude-fable-5
%wait:research.3.cdx %wait:research.3.cld %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to plan the work required
to add a new `sase tool` command soon, but am not sure where to start.

- Review the sase_tool_control_plane.md file in the research sidecar repo for context
  and inspiration before performing your own research.
- This is a large piece of work that seems like it should probably be split up into
  multiple epics.
- I'm also concerned that ongoing work with other epics may conflict / complement this
  work in some ways that we should be aware of before planning this work (the sase-11y
  epic bead, for example, is in-progress and works with procs just like I would expect
  the `sase tool` command will).

Can you do some research with the goal of helping me decide the best way to split this
work up? Is this work really large enough that we can split it up into multiple epics,
each with verifiable (from a normal user) results? If so, end your analysis with a
recommended solution / set of epics.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.3.cdx` and
   `research.3.cld` dependencies, matching by `wait_name` and the canonical research
   label's existing `__a.md`/`__b.md` suffix. Never reassign `__a`/`__b` from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one A report and one B report, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports inside it as `<name>__a.md` and `<name>__b.md`, preserving each report's
   existing `__a`/`__b` suffix. Each report's `source_path` is provenance for where it
   lives in your own opened research checkout; resolve its canonical repo-relative path
   there before moving it. Never modify the other agents' checkouts or the stored
   snapshot recorded at `ref` — only the copy in your own checkout moves. Preserve both
   files and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by opening the research repo and reading the two registered reports, then do my own research before consolidating.

The research repo is open. Now let me read the two registered reports through their canonical references, and locate the control-plane context doc.

Code claims verify so far. Now the bead-graph claims — `sase-zm` stalled state, `sase-11y` phase progress, and the other in-flight capacity/TUI epics.

`sase-zm` confirmed: 14 phases, all still IN_PROGRESS, none closed. Now `sase-11y` and the other in-flight epics.

Both reports are in place. Now the consolidated report.

The layout is complete. Now the final declaration before I report back.

Consolidation complete. The final report set is at `sase/repos/research/202609/sase_tool_epic_roadmap/` — `sase_tool_epic_roadmap.md` (consolidated), with both source reports moved alongside as `__a.md` and `__b.md`, and the commit declared through the host finalizer.

**The answer to your question: yes, this is genuinely multi-epic work — I recommend eight epics, and the first move is to retire `sase-zm`, not to write a plan.** Both researchers independently reached the multi-epic conclusion (A proposed seven, B six); the differences were structural, and I resolved each one against evidence I re-verified myself today:

- **Eight epics, by applying B's own bead-graph lesson consistently.** B mined 600 epic beads and showed deep remediation chains come from oversized epics, released core-contract ratchets, and multi-machine acceptance — then still left a 10–11-phase first epic and a single admission epic it predicted would "expect one child epic." I adopted A's splits where B's data supports them (hand-off execution as its own epic E2; local admission E7 split from fleet rollout E8) and B's split where it beats A (TUI surfaces as standalone E5, kept out of supervision and admission cutovers). The set: **E1** ToolRun ledger + catalog (foreground), **E2** durable hand-off, **E3** failure triage (NEW/KNOWN/FLAKY), **E4** receipts and staged reuse, **E5** surfaces, **E6** forecasts + auto inline-vs-hand-off, **E7** local admission, **E8** fleet + rollout. Each has a normal-user verification gesture spelled out in the report.
- **`sase-11y` is mostly a complement, and E2 need not wait on it.** The two primitives tool execution needs — `detach_scope` and the shared supervision library — are exactly the two phases already closed (verified: 2/10 closed). The one real conflict is `sase-11y.8`'s oneshot service procs, resolved by having standalone tool runs use plain visible durable procs (no `service` marker, link stored on the ToolRun side only, no proc-wire change while `.2` bumps that schema), and landing E5 after `.7`/`.8`.
- **Triage and receipts come before forecasting** (B's order): the measured waste is re-discovery and repetition, not mis-scheduling, and forecasting is gated by calendar time anyway — it needs ~3 weeks of load samples that nothing records today. E3–E5 fill that window.
- I independently reproduced B's most novel apollo measurements exactly (69 monitors, `elapsed_seconds` on only 30, 29 terminal `check-full` runs with zero completed) and confirmed all the load-bearing code/bead claims: no `sase tool` command, `procs.history_limit: 100`, no loadavg/PSI sampling anywhere, `sase-zm` at 14 phases / 0 closed / no landed code.

The report ends with ordered first moves (retire `sase-zm` with a concrete close command, write one decision record, land the "LLM Calls" rename, then plan E1 only) and five open questions for you — the main ones being catalog placement in `sase/sase.yml`, whether `sase tool` is the final name, and whether you'd rather merge E3+E4 into one larger intelligence epic (I recommend not).
