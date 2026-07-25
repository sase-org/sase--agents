# Chat History - ace-run (sase-96.8.2)

- **TIMESTAMP:** 2026-07-25 15:17:29 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-96.8.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-96.8, bead=sase-96.8.2)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-96.8.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead details.

Now let me check the linked repos for any external consumers before deciding to delete the helper.

Now the two call sites:

Now update the tests that monkeypatch the removed helper:

Now I'll update the chop-agents test patches with a shared helper:

Now update the assertion on the prompt file's parent directory:

Lint and symvision are clean. Now the full check:

Bead **sase-96.8.2** is done and closed (epic sase-96.8 untouched).

## What changed

**`src/sase/agent/launch_spawn.py:248`** — `sase_tmpdir=get_sase_managed_tmpdir("launch-prompts")` instead of the bare `$SASE_TMPDIR` root. No Rust edit was needed: I confirmed in `sase-core` that `write_prompt_temp_file()` (`crates/sase_core/src/agent_launch/mod.rs:1791`) already `tempfile_in`s an explicit directory and only falls back to the system temp dir when the argument is empty/`None`.

**`src/sase/main/ace_handler.py:34`** — `ace_profile_<ts>.txt` now lands under `get_sase_managed_tmpdir("ace-profiles")`. The explicit `--profile <path>` override path is unchanged.

**`get_sase_tmpdir()` deleted** (from `paths.py` and the `sase.core` re-exports). I checked for consumers in this repo plus `sase-core`, `sase-github`, `sase-telegram`, and `chezmoi` (all opened via `/sase_repo`) — none remained. `get_sase_managed_tmpdir()`'s docstring now says callers must always pass a subdirectory part and that there is deliberately no bare-root helper, so nothing reintroduces the leak.

**Tests** — `tests/test_axe_chop_agents.py` gets a `_redirect_managed_tmpdir` helper replacing its five `get_sase_tmpdir` monkeypatches, and asserts the prompt file lands in `<root>/launch-prompts/` with the `sase_ace_prompt_` prefix; `tests/main/test_ace_handler.py` asserts the `ace-profiles/` subdirectory.

## Verification

- Exercised `prepare_agent_launch` against a scratch `SASE_TMPDIR`: prompt file landed at `<root>/launch-prompts/sase_ace_prompt_7kGArY.md`, and **0 files were added directly to the root** (only the `launch-prompts/` and `out/` directories) — the delta the plan asks for.
- `tests/test_core_agent_launch_wire.py` still passes unchanged, so the wire shape and prefix are intact.
- ACE artifact readers (`artifact_files.py`, `_revive_artifacts.py`, `_workflow_loaders.py`) have no temp-root assumptions, so nothing reads the old location.
- `just lint` (incl. symvision) clean. `just check`: **22,109 passed, 1 failed** — the failure is `tests/ace/tui/widgets/file_panel/test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes`, which the plan lists under Non-goals as pre-existing intra-file pollution; it passes in isolation, which I re-confirmed.

The changes are in the working tree, uncommitted — say the word and I'll commit them.

Bead is already closed. Committing now.

Done. Working tree is clean, `master` is level with `origin/master`, and the commit is pushed as `63b9d8814`.

**Bead sase-96.8.2 — closed** (parent epic sase-96.8 untouched, no new beads).

**What shipped:**
- `src/sase/agent/launch_spawn.py:248` — prompt file now goes to `get_sase_managed_tmpdir("launch-prompts")` instead of the bare `$SASE_TMPDIR` root. No Rust change needed; `write_prompt_temp_file()` already honors an explicit directory.
- `src/sase/main/ace_handler.py:34` — `ace_profile_<ts>.txt` lands under `get_sase_managed_tmpdir("ace-profiles")`; the explicit `--profile <path>` override is unchanged.
- `get_sase_tmpdir()` deleted from `paths.py` and the `sase.core` re-exports — no consumers remained in this repo, `sase-core`, `sase-github`, `sase-telegram`, or `chezmoi`. The surviving helper's docstring now states there is deliberately no bare-root variant.
- Tests updated in `tests/test_axe_chop_agents.py` (shared `_redirect_managed_tmpdir` helper replacing five monkeypatches) and `tests/main/test_ace_handler.py`.

**Verification:** a scratch-root run of `prepare_agent_launch` put the prompt at `<root>/launch-prompts/sase_ace_prompt_*.md` with zero files added directly to the root. `just check`: 22,109 passed, 1 failed — `test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes`, the pre-existing intra-file pollution failure the plan lists under Non-goals; it passes in isolation.

One warning from the commit: agent-hood publication for hood `ku` deferred (`ku.f1` absent from project inventory). It retries automatically and did not affect the commit or push.
