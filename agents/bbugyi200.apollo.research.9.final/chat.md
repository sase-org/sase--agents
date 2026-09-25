# Chat History - ace-run (research.9.final)

- **TIMESTAMP:** 2026-09-25 14:27:31 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.9.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_135331.md`

## Prompt

%clan(research.9, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to rename the `%proc` directive to
`%tool` and add some features to it to better support the `sase tool` command (see the
sase_tool_epic_roadmap.md file in the research sidecar repo for context).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? End your analysis with a recommended solution.]]) %id:research.9.final %m:@xlarge
%wait:research.9.cdx %wait:research.9.cld %wait:research.9.mus %wait:research.9.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to rename the `%proc` directive to
`%tool` and add some features to it to better support the `sase tool` command (see the
sase_tool_epic_roadmap.md file in the research sidecar repo for context).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, mus, gem, belonging to this
   dispatch's `research.9.cdx`, `research.9.cld`, `research.9.mus`, `research.9.gem` dependencies, matching by `wait_name` and the canonical research
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

## Response

I'll start by reading the research and repo skills, then open the research sidecar and pull each registered report.

The four reports map cleanly to cdx, cld, mus, and gem. Next I’ll open the research sidecar and read each report plus the tool-epic context.

The four suffix mappings are unique. I’ll read each report and the tool-epic roadmap through audited artifact refs.

The four reports disagree on rename vs. add, ad-hoc bodies, and reservation policy. I’ll verify those seams in the live tree and related beads.

The four reports are tracked and unique by suffix. I’ll group them under `tool_launch_directive` and write the consolidated analysis.

Add `%tool` as a **new named ToolRun launch unit**. Do not mechanically rename `%proc`.

The four independent reports and a pass over the live tree agree on the diagnosis: `%proc` authors a raw durable process, while `sase tool` records a ToolRun (catalog identity, fingerprints, stages, a followable id). A ToolRun may be owned by a proc; it is not a proc. Calling today’s `%proc` surface `%tool` would make “tool” mean “detached script” just as the rest of the product has given the word a narrower meaning.

The full write-up is `research:202609/tool_launch_directive/tool_launch_directive.md`, with the four source reports beside it.

**Is the rename a good idea?** The goal is. `%tool:check` is the prompt surface `sase tool run check` has been missing, and it is the way named tools enter `%wait` / `%if::` / AXE graphs without bypassing the ledger. A spelling change with unchanged `%proc` behavior is worse than leaving `%proc` alone.

**What I would do instead**

- Grammar: `%tool:check` and `%tool(test, extra...)`. Owner options only: `timeout=`, `idle_timeout=`, `label=`, `workspace=`.
- Execution: implicit durable hand-off through the existing E2 reserve/`_adopt` path. One ToolRun, one proc owner, fail-closed (the `-H` contract). Approve against a catalog snapshot; re-check the digest in the leased workspace.
- Keep `%proc` in this epic. `sase-s6` is still landing, and `%proc` usage is currently zero. Retiring it is a later `typed_launch_units` decision, and it has to happen *before* `sase-s7` (due 2026-11-20), not after.
- Named tools only in v1. Ad-hoc `bash=` / fences stay on `%proc` (and on `sase tool run --`).
- New `LaunchUnitPayloadWire::Tool(ToolUnitWire)` in sase-core. Stay behind `typed_launch_units`; no second flag.
- Fold `sase-11k` for tool units: same-plan waits currently resolve when the proc is *submitted*, so “run check, then fix” races today.
- Leave receipts, continuation flags, remote dispatch, and `%wait(tool=<run-id>)` out. Gemini’s `reuse=` / `keep_going=` / `handoff=` pull later epics into this one.

Default `workspace=true` (fresh leased checkout) is the post-land / witness pipeline; show that checkout in the approval preview.

This is one five-phase epic now, pin-serialized with in-progress E3 (`sase-18j`), with E2 already landed as the substrate.
