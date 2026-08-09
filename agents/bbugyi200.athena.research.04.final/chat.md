# Chat History - ace-run (research.04.final)

- **TIMESTAMP:** 2026-08-09 14:23:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.04.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260809_135346.md`

## Prompt

%id(final, clan=research.04) %wait(priority=20) %m:@research_lead
%wait:research.04.cdx %wait:research.04.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

Sase agents are constantly tasked with (e.g. via sase task beads that other agents created or via phase beads they are working) with raising the sase-core-rs dependency window in order to get whatever feature they are working on to work correctly. This wastes tokens on a task that seems pretty routine / automatable. Can you do some research with the goal of helping me figure out the best way to automate this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.04.cdx` -> `__a`, `research.04.cld` -> `__b`), then read both reports.
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

I'll start by reading both researcher transcripts to identify their reports.

Both reports are read. Report mapping: `research.04.cdx` → `automating_sase_core_rs_dependency_windows.md` (`__a`), `research.04.cld` → `core_floor_bump_automation.md` (`__b`). Now my own verification, focused on where they disagree.

This is the decisive test neither report ran — whether the binding-set oracle would actually reproduce the historical floors.

Research complete. Setting up the final layout.

The `sase` workspace is clean (no changes there, so no `just check` needed). Final layout is in place:

```
sase/repos/research/202608/core_dependency_window_ratchet/
├── core_dependency_window_ratchet__a.md   (research.04.cdx — release-boundary ratchet)
├── core_dependency_window_ratchet__b.md   (research.04.cld — computed floor ratchet)
└── core_dependency_window_ratchet.md      (consolidated)
```

## What the consolidation found

**The two reports weren't really competing.** `__a` diagnosed *when* the invariant should be enforced; `__b` diagnosed *what it costs and how fast the answer can be produced*. Their churn numbers (50 commits vs 67) are the same data over different windows — I reproduced both.

**My own pass added three things:**

1. **The decisive experiment neither ran.** `__b`'s central claim is that the required floor is "already fully computable" by bisecting published wheels against `check_sase_core_rs_bindings` + `validate_sase_core_rs`. I replayed the 12 most recent floor bumps against that oracle: **5 of 12 (42%) pass both probes against the pre-bump floor.** All five moved the floor for pure behavior changes (*"archive close metadata instead of destroying it on reopen"*, *"append a snooze note recording wake conditions"*) that a symbol-existence oracle cannot see. A bisect would have returned a floor that is **too low** — exactly the bug the strict gate exists to prevent. Corroborating: only 11 of 67 bump commits added a `require_rust_binding` call at all. This demotes `__b`'s oracle from floor-setter to free-but-incomplete early warning, and makes `__a`'s conservative "newest published at release time" the correct authority.

2. **`__b`'s top recommendation doesn't work as stated.** GitHub only offers auto-merge on PRs that *cannot merge immediately*. `sase-core` master is unprotected (verified 404 on branch protection), so release PRs are immediately mergeable — `gh pr merge --auto` would degrade to merging without waiting for CI. The report gives two working variants instead.

3. **Better cost metrics.** Both reports counted commits; the unit that matters is agent launches: **21 closed beads since 2026-07-23 have a floor bump as their entire titled purpose — 16 of them phase beads** — plus 4 live now. And touching `pyproject.toml` escalates `just check` to the **full 2482-file suite** (`tools/select_tests --explain`, verified), so the cheapest bump still pays the most expensive lane.

**Recommendation:** invert the `published-core-minimum-smoke` trigger — today it runs on every feature PR and master push but is *explicitly skipped* on the release-please branch, the one place its metadata matters. Move it there, ratchet the window on the existing `sync-lockfile` job (~8 core releases collapse into one edit), keep the cheap probes as a non-fatal `just check` warning so the feature agent learns which core release it needs before committing, delete the redundant golden literal, and merge `sase-core` release PRs from a workflow. R1 (the trigger inversion) is the smallest diff and the actual fix.

I left the files uncommitted — say the word and I'll commit them to the research sidecar. I also didn't file any beads for the follow-ups.

Layout confirmed — all three files present, renames staged, consolidated report untracked. Committing now.

Committed. Working tree is clean and `main` is in sync with `origin/main`.

**Commit:** `2b34a23 docs(research): consolidate sase-core-rs window ratchet research` — the two renames (`__a`, `__b`) recorded as pure renames, plus the 547-line consolidated report.

Final layout in the research sidecar:

```
202608/core_dependency_window_ratchet/
├── core_dependency_window_ratchet__a.md   (research.04.cdx — release-boundary ratchet)
├── core_dependency_window_ratchet__b.md   (research.04.cld — computed floor ratchet)
└── core_dependency_window_ratchet.md      (consolidated)
```

Two notes on the commit itself:

- My first `sase_git_commit` invocation failed because I passed the pre-rename paths as `-f` args; the renames were already staged, so those pathspecs no longer resolved. Re-running with only the post-rename paths succeeded.
- `sase commit` reported that prompt-archive publication was deferred (`agents sync lock is busy`) and that this project already has **2 quarantined agent-hood publication requests**. The primary commit and push are unaffected, but the archive link written into the commit may stay unavailable until someone runs `sase agent sync --retry-quarantined`. I did not run it, since another agent likely holds that lock right now.

The research conclusion is unchanged from the report: invert the `published-core-minimum-smoke` trigger so it runs on the release-please branch (where its metadata actually matters) instead of on every feature PR, ratchet the window on the existing `sync-lockfile` job, and keep the cheap binding probes as a non-fatal `just check` warning. The consolidated report's decisive addition is that the bisect-based "computed floor" cannot be the authority — 5 of the 12 most recent floor bumps pass both probes against the pre-bump floor, so a bisect would return a floor that is too low.
