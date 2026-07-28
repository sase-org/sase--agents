# Chat History - ace-run (sase-ac.6.2)

- **TIMESTAMP:** 2026-07-28 09:30:47 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ac.6.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-ac.6, bead=sase-ac.6.2)
%model:@small_phase_worker
%auto
Can you complete the work for bead sase-ac.6.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Closing an assigned phase bead is unaffected by the parent-close
descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me make the fix.

Now the test.

Now append the test at the end of the file.

Both fail with the change reverted. Now `just check`.

Done — bead `sase-ac.6.2` is closed.

**Change** — `src/sase/ace/tui/actions/agent_workflow/_prompt_bar_requests.py:353`

The `#@` selector's "extra prompts" seeding took the project name out of a leading VCS tag (user-facing spelling, e.g. `sase`) and looked it up in `get_known_project_workspaces()`, which is keyed by the ProjectSpec *directory key* (`gh_sase-org__sase`). The miss returned `None` inside a bare `except Exception: pass`, so under a `#gh:sase` tag the project's `sase.yml` xprompts were silently absent from the selector.

Now the tag's project is routed through `canonical_xprompt_project()` and looked up in `known_project_namespaces()` — same fix `sase-ac.4` applied to the sibling arg-assist path. Local-import style and the surrounding error handling are unchanged (TUI interaction path).

**Tests** — two cases in `tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py` over a `gh_org__proj` / `PROJECT_NAME: proj` fixture: the user-facing spelling puts `proj/thing` into the selector's extra prompts, and the directory-key spelling normalizes to the same canonical namespace (no `gh_org__proj/thing`). Both fail with the source change reverted (verified via stash).

**Verification** — `just install`, then lint clean (ruff/mypy/symvision). Two caveats, neither from this change:
- `just check` fails at `SASE validation` → `plan links validate` (`202607/prompts/xprompt_identity_landing.md` links to a missing `../xprompt_identity_landing.md`). Reproduced on a fully stashed clean tree, so pre-existing.
- Full `just test`: 22978 passed, one failure in `tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill`, which passes in isolation — a parallel-load flake.

Changes are left uncommitted, and the parent epic `sase-ac.6` is untouched. Note the workspace is one commit behind `origin/master` (a sibling phase landed during this run).

Bead is closed. Committing now.

Committed and pushed; working tree clean, branch level with `origin/master`.

**Commit** `a0a2e4007` — `fix(ace): canonicalize prompt-bar VCS-tag xprompt lookup (sase-ac.6.2)`, staging only the two files from this session.

**Bead** `sase-ac.6.2` was already CLOSED (resolution `done`) before the commit; the commit's own close step was idempotent. Parent epic `sase-ac.6` untouched.

One note from the commit tool: the project has 3 quarantined agent-hood publication requests, so the agent link written to this commit may not resolve until `sase agent sync --retry-quarantined` is run. That's pre-existing outbox state, not caused by this commit — I haven't run the retry since it touches shared publication state.
