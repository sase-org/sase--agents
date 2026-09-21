# Chat History - ace-run (research.21.final)

- **TIMESTAMP:** 2026-09-19 08:18:36 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.21.final

## Prompt

%id(final, clan=research.21)
%m:@xlarge
%wait:research.21.cdx %wait:research.21.cld %q(10, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The `@epic` agent tribe
panel still disappears and reappears (i.e. flickers) sometimes on the "Agents" tab.
We've tried to fix this several times before now. Can you do some research with the goal
of helping me figure out what's causing this / what we need to do to mitigate this? End
your analysis with a recommended solution. Make sure to organize your contents
appropriately using markdown sections.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.21.cdx` and
   `research.21.cld` dependencies, matching by `wait_name` and the canonical research
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

I'll start by opening the research repo and reading the two registered reports, then do my own investigation into the `@epic` tribe panel flicker.

Both reports are read (B was truncated). Let me get the rest of report B.

All claims from both reports verified in the current tree. Now I'll set up the consolidated report directory in my research checkout.

Both reports exist at the month-dir root in my checkout. I'll use the stem `epic_tribe_panel_flicker_root_causes`, move the reports in, and write the consolidated report.

The consolidated report is written and the final layout is in place. Now I'll submit the final declaration.

The consolidated report is written and the final declaration was accepted. Here's the summary:

## What I did

- Read both registered reports through audited `sase artifact read` (A = `agents_epic_panel_flicker_atomicity__a.md`, B = `agents_tab_epic_tribe_panel_flicker__b.md`, matched by their existing suffixes).
- Independently re-verified every load-bearing code claim against the current master tree — all confirmed: the finalize-then-proc-sync double publication in `_loading_apply.py` (second finalize at `_proc_action_completion.py:198`), the merge-guard replacement path for bounded loads with `has_more=False`, the complete-history latch clearing on mismatched query keys (`_loading_apply.py:446-448`), index-keyed panel widgets, `clear_options()` at the start of every list rebuild, and the `active_search` row-remove bail.
- Created `202609/epic_tribe_panel_flicker_root_causes/`, moved the reports in as `__a.md` / `__b.md`, and wrote the consolidated `epic_tribe_panel_flicker_root_causes.md`.

## Key finding

The flicker is **three verified defects compounding**, and the two reports corroborate rather than conflict: report B observed the ~50 ms `17 agents → 0 → 17` restore as "two consecutive UI applies" without identifying the second; report A's proc-shell-sync ordering is exactly that mechanism. Meanwhile A didn't cover B's widget-identity findings, which explain why `@epic` flickers even when its membership never changes (sibling-tribe churn remaps the slot-indexed widget, and every full rebuild blanks it via `clear_options`).

## Recommended solution (as consolidated)

1. **Phase 1 — atomic publication:** merge the generation-stamped proc projection *before* fold/query filtering and panel-key calculation; finalize exactly once per disk apply; remove the post-finalize proc sync from the apply path.
2. **Phase 2 — tribe-stable widgets:** key `AgentList` widgets by tribe, keep configured tribes mounted at zero rows, add single-panel insert/remove to the incremental path, never clear untouched panels, and delete the nonempty-query row-remove bail (which fires constantly under the standing `NOT machine:apollo` query).
3. **Phase 3 — removal authority:** bounded loads always patch (never replace) regardless of `has_more`; a same-query bounded zero keeps the cache; the latch clears only on real query changes; converge the still-swinging `tier1_index_revalidate` path; Rust-core read-transaction + index-generation hardening as follow-up.

The report also resolves the ordering disagreement (atomic apply first, since it's the mechanism behind every traced occurrence and fixes state, not just paint), lists the regression tests and trace invariants both reports proposed, and flags the stale-TUI/second-PID check that must precede any live verification soak.
