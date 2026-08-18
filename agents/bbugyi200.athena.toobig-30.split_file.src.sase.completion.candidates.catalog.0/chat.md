# Chat History - ace-run (toobig-30.split_file.src.sase.completion.candidates.catalog.0)

- **TIMESTAMP:** 2026-08-17 21:11:12 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-30.split_file.src.sase.completion.candidates.catalog.0

## Prompt

#gh:sase-org/sase
%id:toobig-30.split_file.src.sase.completion.candidates.catalog.0
%clan(toobig-30, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 729  src/sase/completion/candidates/catalog.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/completion/candidates/catalog.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the split modules.

Now the aggregator:

The split is in place and verified; the scoped test lane is still running in the background. Here's where things stand:

**New layout** (`src/sase/completion/candidates/`), grouped by where the values come from:

| File | Lines | Contents |
|---|---|---|
| `catalog.py` | 93 | Just the `ValueKind → (fetch, source_path)` table plus the import-set contract docstring |
| `catalog_support.py` | 53 | `dedupe`, `project_records_and_snapshot` — the only genuinely shared helpers |
| `catalog_projects.py` | 169 | repo, workspace, patch (+ registry/state-root parsing) |
| `catalog_sdd.py` | 118 | bead, plan (+ bead-store resolution) |
| `catalog_prompts.py` | 145 | xprompt, skill, tag (+ package-root walking) |
| `catalog_content.py` | 136 | glossary, memory (+ project config path resolution) |
| `catalog_agents.py` | 187 | agent, monitor, proc, artifact (+ shared agent-index query) |
| `catalog_build.py` | 80 | flag, plugin, model — properties of the build, not a project |

Notes on the mechanics:

- Fetchers that cross a module boundary became public (`repo_candidates`, etc.) because Symvision forbids importing `_private` names across files; helpers used by only one module stayed private in that module (`_resolve_beads_dir`, `_query_agent_index`, `_package_dir`, `_project_config_path`, …).
- `providers.py` is untouched — it still does `from ...catalog import PROVIDERS`, so the public surface is unchanged.
- I AST-compared every function against the old file: 43 of 45 bodies are identical modulo the renames; the two that differ are `_resolve_beads_dir`/`plan_candidates`, where the duplicated `(".git", ".hg", ".jj")` literal became a `_REPO_MARKERS` constant now that they share a file.

**Verification:** `just check` passes fmt, keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, and terminology. The completion suites pass in full — 233 passed, 1 skipped across `tests/completion`, the handler/fast-path/parser tests, and `test_completion_candidates_contract.py` (which enforces the no-`ace`/`parser`/`rich`/`textual` import set and the per-kind latency budget).

`just check` does fail at the Symvision gate, but on a pre-existing problem unrelated to this diff: six `--epic-symbol "sase-p2.2(...)"` entries in the Justfile went stale when that phase bead closed two hours ago, while its consuming phase `sase-p2.3` is still in progress. Re-running Symvision with only those six entries dropped reports nothing about the new modules. I recorded it as a `DISCOVERED ISSUE:` note on the in-progress epic `sase-p2` (the fix there is to retarget the entries, not delete the symbols) and added a `+1` to `sase-o7`, the task tracking the systemic version — this instance shows the whitelist can also go stale at a *phase* close, not just at epic landing.

I'll report the scoped test result when it finishes.

Changes are mine from this session. Let me re-verify within this turn before committing.

I was using the wrong interpreter — the workspace has its own venv.

Symvision fails only on the stale `sase-p2.2` entries. Let me confirm nothing in my diff is flagged:

Nothing from my diff is flagged. Now the scoped test lane:

All 755 scoped tests pass, lint gates pass, and the only Symvision findings are pre-existing stale whitelist entries. Committing now.

Committed and pushed; working tree clean and in sync with `origin/master`. Let me verify the Symvision follow-up was actually recorded (the earlier pass claimed it, but that pass terminated):

Both follow-ups were recorded. Done — here's the final state.

**Commit:** `cd13a0f92 refactor(completion): split the candidate catalog by value source` — committed and pushed, working tree clean and level with `origin/master`.

**The split** — `catalog.py` went from 774 lines to 93, grouped by where the values come from:

| File | Lines | Contents |
|---|---|---|
| `catalog.py` | 93 | `ValueKind → (fetch, source_path)` table + import-set contract docstring |
| `catalog_support.py` | 53 | `dedupe`, `project_records_and_snapshot` — the only cross-group helpers |
| `catalog_projects.py` | 169 | repo, workspace, patch |
| `catalog_sdd.py` | 118 | bead, plan |
| `catalog_prompts.py` | 145 | xprompt, skill, tag |
| `catalog_content.py` | 136 | glossary, memory |
| `catalog_agents.py` | 187 | agent, monitor, proc, artifact |
| `catalog_build.py` | 80 | flag, plugin, model |

`PROVIDERS` kept its name and location, so `providers.py` and every other caller are untouched. Fetchers crossing a module boundary became public (Symvision forbids importing `_private` names across files); single-consumer helpers stayed private where they're used.

**Verification, all run in this turn:**
- `just check` — passes fmt (python + markdown), keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, and patch/stitch terminology.
- `just test-scoped` — 755 passed.
- `tests/completion` + `tests/main/test_completion_candidates_contract.py` — 192 passed, 1 skipped, including the no-`ace`/`parser`/`rich`/`textual` import-set check and the per-kind fast-path latency budget.

**One gate is red, pre-existing and unrelated:** `lint (symvision)` fails on six stale `--epic-symbol "sase-p2.2(...)"` entries in the Justfile — that phase bead closed at 00:45Z while its consuming phase `sase-p2.3` is still in progress, so the entries need retargeting, not deletion. Re-running Symvision with just those six dropped reports nothing about the new modules. That was already recorded as a `DISCOVERED ISSUE:` on epic `sase-p2` and as a `+1` on `sase-o7`, which tracks the systemic version.

One note from the commit itself: prompt-archive publication was deferred because the agents sync lock was busy, and this project has 27 quarantined agent-hood publication requests. The commit landed fine, but the archive link on it may stay unavailable until someone runs `sase agent sync --retry-quarantined`.
