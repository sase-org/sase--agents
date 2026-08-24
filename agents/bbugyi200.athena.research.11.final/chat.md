# Chat History - ace-run (research.11.final)

- **TIMESTAMP:** 2026-08-24 14:59:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.11.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_141250.md`

## Prompt

%id(final, clan=research.11) %m:@research_lead
%wait:research.11.cdx %wait:research.11.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to start making better use of sase's artifact links.
For one I have a strong feeling that we are not linking artifact files like plans and
research files consistently or in an ideal way. It would be nice if we could improve
this somehow without increasing the average agent's context too much (e.g. by telling
every agent to always look for ways they can create artifact links in agent instruction
files, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? While you're at it, do some research on how we can improve artifact links in
general and use them in the best way. End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.11.cdx` -> `__a`, `research.11.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
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

I'll start by reading both researcher transcripts to identify their report files.

Confirmed mapping: `cdx` → `artifact_link_adoption_and_quality.md` (`__a`), `cld` → `artifact_link_adoption.md` (`__b`). Now reading both reports.

Both reports are substantive with real disagreements. Now let me do my own research, prioritizing the conflicts and gaps.

Significant finding — the live graph has **shrunk** since both researchers measured. Let me verify the mechanism.

This is the headline finding — a defect neither report identified. Let me pin down the remaining questions.

I have my independent findings. Let me verify stem availability and open the research sidecar properly.

Live reproduction confirmed — the rename just broke 6 link rows. Now writing the consolidated report.

Only the research sidecar changed; the sase repo is untouched, so no `just check` is needed. Finalizing.

Declaration accepted. Report written to `sase/repos/research/202608/artifact_link_derivation/`.

## Consolidation

**Report mapping:** `research.11.cdx` → `__a` (architecture, relation semantics, external prior art); `research.11.cld` → `__b` (live measurement, defect discovery, injection-point analysis).

Both researchers converged on the same answer from opposite directions — **derive links from data SASE already owns; don't add instruction** — which is the strongest result in either report. My verification confirmed their central claims and resolved four disagreements.

## What my own research added

**A defect neither found, and it changes the sequencing.** The link index is lossy. `preview_aggregate()` rebuilds the machine-global aggregate from *the current workspace's* sidecar clone plus bead events, carrying forward only rows where **neither** endpoint owns sidecar JSON. Every `plan:`/`research:` edge is therefore dropped unless the triggering workspace's clone can see it — so any agent in any ephemeral workspace can silently shrink the graph by writing one link.

Measured right now from `sase_22`: committed sidecar truth holds **134 rows**, the index holds **84** — **66 rows of durable, committed truth are missing**. `derives-from` is 35 in truth vs 2 in the index. The graph fell from the 137 both researchers measured to 84 in a few hours.

This falsifies **b**'s "the storage design is sound; it is the *inflow* that is broken" and makes its Phase 0 insufficient — committing read rows doesn't help if a stale-clone rebuild deletes them anyway.

**Disagreements resolved:**

- **`/sase_final` finalizer** — **a** recommended one, **b** rejected it. Finalizer selection resolves from a *config plan*, not run state, so **b** is right on cost. But **a**'s instinct holds: the boundary is `sase plan propose` / `sase artifact create`, which **a** itself required for plans anyway.
- **`artifact read` stripping links** — **a** called it a context-saving feature, **b** the top defect. Both right; the fix is a one-line typed footer, not un-stripping the block.
- **`plan implements bead`** — **b** asserts it, **a** flags the direction as genuinely ambiguous. **a** is right, and 602 derived rows depend on the answer. Flagged as the first open question.

**Live reproduction:** the rename defect fired on this very consolidation. The two reports carried six link rows; `git mv` recorded clean `R100` renames, and all six are now dangling with two orphaned `links/*.json` companions. I left them broken — they're a reproducible test case, and the report recommends automating the repair rather than hand-patching this instance.

**Corrections to reported numbers:** the `RELATED:` migration is **269** auto-convertible of 303 notes (88.8%), not ~290; plans with `bead_id` is 602, not 589. Both reports' other measurements verified within a day's drift, including **b**'s bead-dependency contrast (~3,097 edges vs 84 artifact links).

**Recommendation:** Phase 0 is now *fix the lossy index* — deriving ~1,700 edges into a store that drops committed rows is building on sand. Then derive at three zero-context injection points (creation-time commands, file hooks, the hourly `housekeeping` chop), then make links pay at retrieval. Net agent-facing text: one line each in `/sase_plan` and `#research_swarm`, both stating a fact rather than adding an obligation. Nothing to `AGENTS.md`, nothing to `/sase_final`.
