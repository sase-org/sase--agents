# Chat History - ace-run (research.0j.cld)

- **TIMESTAMP:** 2026-08-14 15:55:40 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0j.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_153112.md`

## Prompt

%id(cld, clan=research.0j) %wait(priority=20) %m:@research_b  #gh:gh_sase-org__sase I want to unify the different Artifacts tabs with the goal of
using an API / contract of some sort to allow specific sidecar/artifact repos to specify
how their corresponding tabs behave. This will also make adding new functionality more
rewarding in the future (if we get the abstraction right), since all custom sidecar
repos (even ones that are configured for other users that we don't know about) get new
functionality for the cost of a single implementation.

- See the artifacts_pane_contract.md file in the research sidecar repo for related
  research / inspiration (keep in mind this file is a bit dated since some of the
  requirements this agent was given were not quite right/complete and I ran this agent a
  few days ago--related changes have been made since then).
- I do want the "Patch" sub-tab to be included in this unification, with the goal of
  migrating this tab over to the same look and feel as the other sub-tabs.
- Before we do this, however, I would like to figure out how to generalize some of the
  "Patch" tab's coolest features (powerful search syntax, saved queries,
  ancestors/children jumpers, etc...) so they can be included in the contract.

Can you do some reasearch to help me decide the best way to implement this based on the
requirements and notes listed above? Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by getting oriented — reading the prior research file and the current Artifacts/Patch tab implementations.

I have enough evidence. Writing the report now.

Research written to `sase/repos/research/202608/unified_artifacts_pane_contract.md`.

## What I found

**The prior report's framing was backwards, and that reframing is the whole answer.** It excluded Patch partly *because* it owns its own query language. But that language is exactly the asset you want generalized — so the reason to bring Patch in is to take the query language away from it. Once querying is a contract layer, what's left of Patch's uniqueness is mutation verbs, which the `MUTATE` capability already has to cover for Beads.

**There are three query languages, and one is a self-declared fork of another.** `ace/agent_query/tokenizer.py:1` says *"Adapted from `sase.ace.query.tokenizer`"* — and the fork already added the one thing a unified design needs: a **typed property-key registry** (substring/enum/bool/duration). Meanwhile `filter_tokens.py` + four `filter_query` modules drive every non-Patch Artifacts pane with a flat dialect that has no `OR`, no parens, no case-sensitive literals. Each of the three is best-in-class at something and worst at something else — the unified engine is a merge, not a levelling-down.

**Three things it turns out you already have:** `GroupFoldRegistry` is documented as *"shared by Agents and Patches"* and keyed on `tuple[str, ...]` — the same shape as `ArtifactEntryTarget`; `FilterBar`'s eight class vars are a field schema written as class attributes; and `ref.properties` already carries `type`/`values`/`source` and is already Rust-validated, so it becomes queryable the moment anything reads it.

**A hard constraint the prior report missed:** `provider_spec.rs:18-25` documents that the Rust wire version must *not* be bumped — CI runs the published floor `sase-core-rs` against the checkout. That makes a Python-side presentation digest mandatory, not merely prudent.

## Verified live at HEAD

Re-running the prior report's inventory: defects A, B, E are **fixed**. C and D are **live** — and C is now three defects (provider accents also *drift*: adding a `design` sidecar silently repaints Research `#5FAFFF`→`#5FD7AF`, and `design` collides with `plan` outright). D reproduces exactly, including the detail that the **built-in Plans tab vanishes too**, and the degraded result survives `reset_artifacts_subtabs_cache()`. The "five shim sites" claim is now 13.

## One new defect, filed

`o` is double-booked on the Patch pane: `mark_pr_origin` (binding index 27) shadows `cycle_grouping_mode` (index 154), so forward grouping-cycle is unreachable while `O` works — despite `docs/ace.md:614` and the info-panel badge both promising it. Confirmed by executing `build_app_bindings`. Filed as **sase-m5** (medium, ready).

## Open decisions I'd want your call on

The report lists six; the two that actually shape the plan are `s` (mutate-status on Patch/Beads vs cycle-facet elsewhere — genuine semantic conflict, not just a key clash) and `y` (refresh on Patch vs copy-reference everywhere else, an inversion that will feel jarring on your primary surface).

The sase repo tree is clean — no code changed, so no `just check` was needed. The report is uncommitted in the research sidecar.

I'll commit the research file I created.

This is the file I wrote this session. Committing it.

Committed and pushed.

**`568d64f` — `docs(research): design a unified Artifacts pane contract including Patch`** — adds `202608/unified_artifacts_pane_contract.md` (858 lines) to the research sidecar. Working tree clean, branch in sync with `origin/main`.

One thing worth knowing: the rebase pulled in `4aba9be`, an upstream commit from a **parallel agent run** (`bbugyi200.athena.research.0j.cdx`) that answered the same question independently — `202608/artifacts_pane_unification/artifacts_pane_unification.md`, 847 lines. So the repo now holds two concurrent reports on the unified Artifacts pane. I haven't read theirs; if you want, I can diff the two designs and tell you where they agree, where they diverge, and which one's layering holds up — that's a genuinely useful cross-check, since two independent passes converging on the same contract boundary is much stronger evidence than either alone.

For the record on my report's substance, unchanged from before: the core claim is that the prior 2026-08-12 report excluded Patch for the wrong reason — the query language is the asset to generalize, not the obstacle — and that `provider_spec.rs:18-25`'s no-wire-bump constraint makes a Python-side presentation digest mandatory rather than optional. Defects A/B/E are fixed at HEAD; C and D reproduce, with C now three distinct defects. The new Patch keybinding conflict (`o` double-booked, `mark_pr_origin` shadowing `cycle_grouping_mode`) is filed as **sase-m5**.
