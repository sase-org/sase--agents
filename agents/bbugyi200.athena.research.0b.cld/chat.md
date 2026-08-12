# Chat History - ace-run (research.0b.cld)

- **TIMESTAMP:** 2026-08-12 12:57:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0b.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_123932.md`

## Prompt

%id(cld, clan=research.0b) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I recently made some improvements to the "Artifacts" tab (see
the sase-js epic bead for context) and would like to continue improving these sub-tabs
by adding new functionality. Before doing that however, I think it's a good idea to try
to unify these sub-tabs as much as possible by providing a similar interface for each
for users and a practical contract for artifact ref type designers to follow to make
sure new sidecar repo tabs follow the same standard. Can you do some research with the
goal of helping me decide the best way to implement this? End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of the Artifacts tab and its sub-tabs.

Now I have a complete picture. Writing the report.

Written to `sase/repos/research/202608/unified_artifacts_subtab_contract.md` (41k). The sase repo tree is untouched — `sase/repos/` is gitignored — so no `just check` was needed.

## What the research found

**The epic shipped a dynamic tab *registry* but not a dynamic *pane*.** A configured provider gets a tab, accent, digit, and working list. It does not get its own label, status counters, hints, copy targets, or help section — and the `properties` / `detail` blocks it declares in its provider spec are read by nothing. `@research` today renders inside a pane that calls itself "Plans", counts "proposals · active · archived", offers `A`pprove/`X` reject, and copies an "owning bead id."

Four concrete defects, one of which you already reported:

- **Files renders at strip position 6 but carries digit `4`** → the strip reads `1 2 3 5 6 4`. `test_artifacts_scaffold.py:546` currently *asserts* the wrong order, so the fix must update it.
- **Provider digits are alphabetical from offset 5**, so installing a `design` sidecar renumbers Plans from 5→6 and Research 6→7 — the exact regression §9.1 of the prior report warned against.
- **Latent accent collision**: the first provider fallback accent is `#AF87FF`, the same value pinned for `ref:plan`.
- **Provider discovery fails silently.** I verified this live: in a workspace with a stale venv, `resolve_artifacts_subtabs()` returned only the four fixed tabs — Plans and Research vanished with no toast and no doctor finding, because two bare `except Exception` blocks swallow it.

Plus the structural cost: 13,413 lines in `widgets/artifacts/`, only 691 of them shared; the off-thread load-coalescing machine written three times near-identically; `ArtifactEntryNavigator` is a Protocol that Files and Stitches only 5/7 implement, papered over with `getattr` at every call site; 47 keymap entries where 20 are four copies of five verbs and `s`/`o`/`a`/`y` each mean different things on adjacent tabs; and the `ref:* → artifacts_plans` copy-group shim hard-coded in three separate files.

## The recommendation

An `ArtifactsPaneContract` with a closed `PaneCapability` vocabulary inside sase that all five pane families produce, with every downstream surface reading capabilities instead of comparing pane ids — plus a declarative `ref.pane` block at provider-spec `schema_version: 2` for the designer-facing half. `FilterBar` is already exactly this pattern done right, so the report argues for copying it upward rather than inventing something.

Five phases, sequenced so Phase 0 is a same-day defect fix and Phase 2 is where you actually feel the unification. The report closes with five open decisions for you — the sharpest being whether to land Phases 0–2 *before* adding new sub-tab functionality, since anything added before the verb keymap exists gets written four times and rewritten once.

Two things I deliberately did not do: I did not file task beads for the defects, since they're the subject of a decision you haven't made yet — say the word and I'll run them through `/sase_new_task`. And I recommend Patches stay **contract-exempt (legacy)**, with one cheap fix regardless: `@patch:` is a live ref kind with no way to copy it from the Patches pane.

The file is the research report I wrote this session. Committing it now.

Committed.

**`docs(research): design a unified artifacts sub-tab contract`** (`0587634`) — adds `202608/unified_artifacts_subtab_contract.md` (710 lines) to the `research` sidecar. `git status --short --branch` reports a clean tree on `main` in sync with `origin/main`, so the push landed.

Two notes:

- The wrapper warned that the project has **2 quarantined agent-hood publication requests** ("agents sync lock is busy"), so the `SASE_AGENT` backlink written into this commit may 404 until you run `sase agent sync --retry-quarantined`. The commit itself is fine.
- The commit immediately before mine (`a805b4f`) is a **different agent's** report on the same question — `bbugyi200.athena.research.0b.cdx` landed `202608/artifacts_subtab_contract.md` (635 lines), recommending a host-owned browser with declarative provider metadata. Different filename, no conflict, but you now have two independent answers to compare. Mine differs mainly in that it audits what the `sase-js` epic actually shipped against §9 of the prior contract report and surfaces four live defects from that gap — including provider discovery failing silently, which I reproduced in a workspace with a stale venv.
