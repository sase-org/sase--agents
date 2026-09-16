# Chat History - ace-run (research.1x.final)

- **TIMESTAMP:** 2026-09-14 13:09:07 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.1x.final

## Prompt

%id(final, clan=research.1x)
%m:claude-fable-5 
%wait:research.1x.cdx %wait:research.1x.cld %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I think I want to rename sase's AXE tab to "Schedule" and
make a few other renames as well.

- We should rename "lumberjacks" to "routines".
- We should rename "chops" to "jobs".
- We should replace all references to "AXE" with "sase's scheduler".
- Unrelated, but still a rename: We should rename the `sase ace` command to `sase tui`
  and replace all references to "ACE" with "sase's TUI".

Can you do some research with the goal of critiquing this change? Is it one that you
think I should make? If not, are there better names that you would recommend I use?
Include a concise list of all of the references that would need to be replaced in your
analysis. End your analysis with a set of recommended names you think I should consider.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1x.cdx` and
   `research.1x.cld` dependencies, matching by `wait_name` and the canonical research
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

I'm the lead researcher for this rename critique. First I'll open the research repo via the `/sase_repo` skill, then read both registered reports through audited artifact reads, do my own codebase research, and finally merge everything into a consolidated report.

Consolidated report is done and committed. It lives at `202609/scheduler_tui_naming/scheduler_tui_naming.md` in the research repo, alongside the two source reports moved in as `scheduler_tui_naming__a.md` and `scheduler_tui_naming__b.md`.

**Bottom line: make the rename, but with two adjustments.** Both researchers independently converged, and my own verification of their evidence confirms it:

- **`sase ace` → `sase tui`: yes.** "Agentic Change Explorer" is stale (ChangeSpecs became Patches, the TUI opens on Agents). But keep `sase ace` as a hidden alias under a sunset flag, and don't rename the `sase.ace` Python package wholesale — it's full of non-TUI domain code and you'd get `sase/tui/tui/`.
- **AXE → "the SASE scheduler": yes**, but not the literal possessive "sase's scheduler" — that phrasing collapses in compounds. CLI noun should be `sase scheduler`, not `sase schedule`. Two collisions need fixing: the `sase.ace.scheduler` package (rename to something like `sase.patch_lifecycle`) and the runner-slots doc that calls launch admission a "scheduler".
- **Tab → "Scheduler", not "Schedule".** This was the one disagreement (A wanted "Automation", B wanted "Scheduler"). I sided with Scheduler: one exact word across tab, CLI, config, and prose beats the marginal accuracy of "Automation", and moving the bgcmd rows to Procs resolves the objection. "Schedule" was the weakest option — the tab is a daemon-control console, not a timetable. The change is label-only: `_TAB_DISPLAY_NAMES` in `tab_bar.py` is separate from the internal `axe` tab ID.
- **lumberjacks → routines: no — use "lane".** Both reports rejected "routine" for the same reason: it means a *single* automation everywhere (Alexa, subroutines, and Claude Code's own `schedule` skill calls one scheduled cloud agent a "routine" — I confirmed that collision is live in your toolchain). "A routine contains jobs" reads backwards. Your own codebase already calls lumberjacks lanes — `default_config.yml` says "Fast lane", "belong in the other lanes", and your chezmoi configs say "audit lane".
- **chops → jobs: yes**, the strongest of the four — `docs/axe.md` already explains chops as "lifecycle jobs". Add "job run" for one execution, and never "task" (task beads exist).

The main risk isn't the names, it's scope: `sase_chop_*` console scripts, `SASE_CHOP_*`/`SASE_AXE_*` env vars, the `axe:` config root composed by the Rust core, the schema-versioned status wire, `chop:` artifact refs, and `~/.sase/axe/` on-disk state are all durable contracts (~19k ace lines, ~5.7k axe, ~3k chop, ~1.4k lumberjack, plus sase-core/telegram/chezmoi downstream). The report includes a 13-category replacement inventory and a 4-stage rollout — vocabulary first (cheap, most of the value), then config keys Rust-first, then dual-published script/env APIs, then optional internal cleanup — following the task→proc and ChangeSpec→Patch precedents with mandatory sunset flags.

**Recommended names:** `sase tui` / "the SASE TUI"; `sase scheduler` / "the SASE scheduler"; **Scheduler** tab; **lane** (not routine); **job** / **job run**. Canonical sentence: *the SASE scheduler runs jobs in independently supervised lanes; operators watch it in the Scheduler tab of the SASE TUI.*
