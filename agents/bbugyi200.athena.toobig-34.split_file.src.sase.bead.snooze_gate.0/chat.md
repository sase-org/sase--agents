# Chat History - ace-run (toobig-34.split_file.src.sase.bead.snooze_gate.0)

- **TIMESTAMP:** 2026-08-18 17:44:12 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-34.split_file.src.sase.bead.snooze_gate.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_172323.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.bead.snooze_gate.0, clan=toobig-34)
%wait:toobig-34.split_file.src.sase.agent.restart.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/bead/snooze_gate.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file and understanding its structure.

Now I'll create the split modules, following the established `_<gate>_gate_{spec,preview,response,actions}` pattern used by the sibling gates.

Now update the tests that referenced the moved private symbols.

Now let me run the checks.

All gates pass except a pre-existing `toobig` violation unrelated to my change. Let me file that as a task bead.

Exact duplicate found — `sase-q7` already tracks this. Recording independent corroboration rather than filing a new task.

Done. `src/sase/bead/snooze_gate.py` (728 lines) is now a facade plus four focused siblings, matching the layout the repo's other gates already use (`task_gate`, `flag_gate`, `stale_cleanup_gate`, `epic_resume_gate`):

| File | Lines | Holds |
|---|---|---|
| `snooze_gate.py` | 137 | front door: `create_bead_snooze_gate`, re-exports, `__all__` |
| `_snooze_gate_spec.py` | 333 | constants, `build_bead_snooze_gate_spec`, option specs, command wrapper + entrypoint |
| `_snooze_gate_response.py` | 151 | `BeadSnoozeResponse`, `translate_bead_snooze_response`, payload parsing |
| `_snooze_gate_actions.py` | 136 | `close_`/`ready_`/`resnooze_bead_snooze` and their store mutations |
| `_snooze_gate_preview.py` | 109 | Markdown preview, snooze block, notification note, close reason |

Three symbols had to become public because they now cross a module boundary (Symvision forbids cross-file private imports); the sibling gates use the same names:

- `_BeadSnoozeResponse` → `BeadSnoozeResponse`
- `_build_bead_snooze_gate_spec` → `build_bead_snooze_gate_spec`
- `_bead_snooze_presentation_note` → `bead_snooze_presentation_note`, `_bead_snooze_close_reason` → `bead_snooze_close_reason` (both in the preview module)

Nothing was removed from the facade's `__all__`, every previously importable name still resolves through `sase.bead.snooze_gate`, and `bead_snooze_gate_command_script` emits byte-identical text for all three options — so gates already persisted on disk still revalidate. Three test files were updated for the renames and for the `_resolve_bead_snooze_project_cwd` patch target moving to `sase.bead._snooze_gate_actions`.

Verification: every lint gate passes (ruff, mypy, symvision, keep-sorted, changelog, SASE validation, committed plans), `just test-scoped` is green (1535 passed, 3 skipped), and the 119 snooze-gate tests pass explicitly.

One thing to flag: `just check` aborts at `lint (toobig)` on a **pre-existing** failure — `tests/_suite_gate.py` is 1197 lines against the 1000 limit, unrelated to this change and present on master HEAD. That's already tracked as ready task `sase-q7`; I added independent corroboration (+1) rather than filing a duplicate, and ran the scoped test lane by hand since the gate blocks it.

These are my changes from this session. Committing them now.

Committed and pushed as `530c574d2`. Working tree is clean and `master` is in sync with `origin/master`.

**What the commit contains** — `src/sase/bead/snooze_gate.py` (728 lines) split into a facade plus four focused siblings, matching the layout the repo's other gates already use:

| File | Lines | Holds |
|---|---|---|
| `snooze_gate.py` | 137 | front door: `create_bead_snooze_gate`, re-exports, `__all__` |
| `_snooze_gate_spec.py` | 333 | constants, gate spec, option specs, command wrapper + entrypoint |
| `_snooze_gate_response.py` | 151 | `BeadSnoozeResponse`, translation, payload parsing |
| `_snooze_gate_actions.py` | 136 | close/ready/resnooze actions + store mutations |
| `_snooze_gate_preview.py` | 109 | Markdown preview, snooze block, notification note, close reason |

Three symbols became public because they now cross a module boundary (Symvision forbids cross-file private imports): `BeadSnoozeResponse`, `build_bead_snooze_gate_spec`, and `bead_snooze_presentation_note` / `bead_snooze_close_reason`. Every name previously importable from `sase.bead.snooze_gate` still resolves there, and `bead_snooze_gate_command_script` emits byte-identical text, so gates already on disk still revalidate. Three test files were updated for the renames and for the `_resolve_bead_snooze_project_cwd` patch target moving to `sase.bead._snooze_gate_actions`.

Two things worth knowing:

- `just check` aborts at `lint (toobig)` on a **pre-existing** failure unrelated to this change (`tests/_suite_gate.py`, 1197 lines vs. a 1000 limit, present on master before this work). It's already tracked as ready task `sase-q7`; I added corroboration rather than filing a duplicate, and ran `just test-scoped` by hand instead — 1535 passed, 3 skipped, plus all 119 snooze-gate tests green. Every other lint gate passes.
- The commit's agent-hood publication link may be delayed: the project has 39 quarantined publication requests. Clearing them is `sase agent sync --retry-quarantined` — I didn't run it, since it touches state well beyond this commit.
