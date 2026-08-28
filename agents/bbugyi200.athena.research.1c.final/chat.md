# Chat History - ace-run (research.1c.final)

- **TIMESTAMP:** 2026-08-28 16:13:12 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1c.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260828_150907.md`

## Prompt

%id(final, clan=research.1c) %m:@research_lead
%wait:research.1c.cdx %wait:research.1c.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about migrating sase's memory files, which are
currently treated like configuration, into sase artifacts, which would require, for
example, adding a new "Memory" subtab to the "Artifacts" tab. Can you do some research
with the goal of critiquing this idea, helping me decide whether it is worth doing, and
(if so) how? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1c.cdx` -> `__a`, `research.1c.cld` -> `__b`), then read both reports.
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

I'll start by reading both transcripts to identify which report each researcher wrote.

The `cld` agent already did a conflict resolution that created a topic directory. Let me check the actual state of the research repo.

Provenance confirmed: `50167df` (research.1c.**cdx**) → `__a`; `a82e179` (research.1c.**cld**) → `__b`. The existing naming already matches. Now let me read all three files in full.

Now let me read cld's premature consolidation, then verify the key claims myself.

I have all three. Now let me do my own research, targeting the crux: both reports priced **different things** for P3.

Found a factual error in report A already. Let me dig into the built-in adapter table — the crux of the P3 cost disagreement.

Critical finding: `compile_builtin_contract` **asserts** a compiled query profile exists. Let me quantify what a built-in pane actually requires.

Verified. Now let me test a hypothesis neither report examined: **where the 625 raw-path citations actually come from.**

Confirmed — `AGENTS.md` renders each Tier 2 note as a heading containing its **raw path**, in every agent's always-loaded context. Let me find the generator and check the timing.

The evidence is pointing somewhere neither report went. Let me test the echo hypothesis directly against the plans corpus.

Decisive: **reference notes (whose raw path AGENTS.md renders as an H3 heading) are cited ~4× more than core notes.** Let me check the existing reference-validation machinery.

Two sharp findings. Let me quantify the live dangling-citation instance.

Found a factual error in report B that cld's consolidation adopted. Let me verify the last two items.

I have enough. Let me check the link indexes before restructuring.

Now let me restructure to the required layout.

Layout is clean. Now writing the consolidated report.

Layout is correct and no references dangle. Finalizing the turn.

Consolidated report written to `202608/memory_as_source_artifacts/memory_as_source_artifacts.md`.

## Layout

`memory_as_artifacts/` already existed — the `cld` researcher hit a merge conflict with `cdx` and pre-emptively built a topic directory plus its own two-way consolidation. Since the stem collided, I used `memory_as_source_artifacts/`, verified both drafts byte-identical against their original commits before moving them, and repointed both link indexes. `cld`'s intermediate consolidation is superseded by this one and removed (recoverable at `a82e179`).

`__a` = `research.1c.cdx` (`50167df`), `__b` = `research.1c.cld` (`a82e179`) — confirmed from commit provenance, not filesystem order.

## Where the reports agreed

Both independently reached **"promote, don't relocate"**: give memory an artifact *identity*, never move its bytes into the store. Both found the same critical constraint — managed `Links`/`Referenced By` tables render *into* the Markdown, and memory bodies are inlined into `AGENTS.md` plus four shims, so a naive migration ships a link table to every agent on every turn.

## What my own pass changed

**1. The demand signal is largely SASE talking to itself.** Report B's headline is 625 documents hand-citing `sase/memory/<note>.md`. Neither report asked where the string comes from: `render_long_memory_sections` (`src/sase/memory/notes.py:534`) emits every Tier 2 note as an H3 heading spelled as its raw path, into every agent's always-loaded context. The prediction that makes is testable and holds — reference notes (path shown) average **30.3** plan citations, core notes (inlined, no path) **7.6**. That weakens B's `corpus-before-mechanism` clearance, but more usefully it *solves* B's own adoption risk: change one f-string and adoption is near-automatic. Hence a new Phase 0 ahead of everything else.

**2. A load-bearing claim in report B is false.** B rejects the Artifacts sub-tab partly because a Memory pane would inherit "prune, reclaim, restore from trash" and be defined by what it turns off. The closed `PaneCapability` set contains none of those — they're `sase artifact` *store* commands. Exactly one adapter uses suppressions today, for one capability. B's P4 argument is sound because it's about the store; the P3 version conflates the two.

**3. The real blocker for P3 is something neither found.** `compile_builtin_contract` asserts a compiled query profile exists, so a built-in pane *requires* a query schema (46–206 LOC) plus a full ~90-line adapter fact block. Report A's "thin wrapper on the Patch precedent" isn't permitted. B's conclusion survives; A's cost model doesn't.

**4. Rename base rate is one, not routine.** B cited beads `sase-te`/`sase-tf` as rename residue — both are about tier *vocabulary*, not note paths. Actual history: exactly one memory-note rename ever, `build_and_run.md → lint_and_test.md`, in today's HEAD — which has **17 plans and 5 research reports dangling right now**. Better evidence than the 625, and it points at a cheap Phase 1b (extend the existing `inventory_reachability` scan to the sidecars) that needs no Rust change.

Report A's startup hazard I downgraded: `MemoryPane` already accepts `activate_on_mount` and the Config hub already passes it — a checklist item, not an architecture problem.

## Recommendation

P0 renderer (~1 small) → P1 `memory:` ref kind (~4 medium) → P1b dangling detection (~1 small) → P2 read-channel narrowing (~2 medium) → Artifacts *reaches* memory via relations rails, no sub-tab → record the decision last, not first. Never move the bytes. §7 leaves five vocabulary decisions to you; the scope-in-ref one blocks P0.

I'll run the final declaration skill now.

Submission required for one repository. Building the manifest.

I dropped the `repo_id` key. Rebuilding the manifest programmatically.

Declaration accepted.

Published a fresh context for this turn and submitted the one required `commit` payload for `sdd:research` (`repo-e029ea166d96`). No deferrals — the evidence brief shows all five dirty paths are new since run start, with the consolidated report written directly by this run and the rest produced by this run's directory restructuring and link-index repointing. The commit message records the merge of the two researcher reports plus the lead pass, the three corrections it made, and why the topic stem is `memory_as_source_artifacts` rather than `memory_as_artifacts`.
