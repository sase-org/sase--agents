# Chat History - ace-run (sase-9q.5)

- **TIMESTAMP:** 2026-07-26 08:54:15 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-9q.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-9q, bead=sase-9q.5)
%model:@small_phase_worker
%auto
%w:sase-9q.4
%w(bead=sase-9q.4)
Can you complete the work for bead sase-9q.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead's details.

Now let me look at the current state of the relevant code.

Now let me make the config additions.

Now the launch path.

Now rewrite `_finish_agent_launch` and the collection helper.

Now let me check for other callers of the modal / existing tests.

Now let me write the submit tests.

Good — those whitelist entries are now redundant since the launch path uses both.

The skills drift is pre-existing (`sase_beads` skill, untouched by this change). Running the test stage directly:

Confirmed pre-existing. Now closing the bead.

Done — bead `sase-9q.5` (phase `submit`) is closed.

## What changed

**`src/sase/ace/tui/actions/agent_workflow/_launch_start.py`** — `_finish_agent_launch` now gates on `build_prompt_input_plan` instead of `parse_prompt_input_request`. When nothing needs collecting, the existing fast paths are untouched (including the optional-declared-inputs-only → substitute-defaults branch). Otherwise `_collect_prompt_inputs_then_launch(prompt, plan, keep_bar)` pushes `InputCollectionModal(plan, ...)`; on confirm it records the tags from the **pre-substitution** body (D7, frontmatter excluded per D11), then `apply_prompt_input_values`, then `_launch_resolved_prompt`. Cancel behavior is byte-for-byte today's: bar stays mounted, nothing launches. `agent_count` still derives from `parse_multi_prompt`.

**Config** — new `ace.prompt_inputs` section in `default_config.yml` and `sase.schema.json` with `collect_raw_placeholders` and `xprompt_placeholder_args`, both defaulting to `true`. `build_prompt_input_plan` reads the first through the cached `load_merged_config`, so the submit path adds no disk I/O and the disabled case produces no placeholder fields.

One deliberate deviation worth flagging: I added the `xprompt_placeholder_args` key as data only, without a reader. A public reader with no consumer until phase `xpromptargs` would need a `--epic-symbol` whitelist entry that the next phase then has to remove; letting `xpromptargs` add its own reader is cleaner. The key itself is in place as the plan specifies.

**`Justfile`** — dropped the `sase-9q(apply_prompt_input_values)` and `sase-9q(build_prompt_input_plan)` epic-symbol entries. Both symbols now have real non-test consumers, and symvision hard-errors on stale entries.

**Tests** — 8 new cases in `tests/ace/tui/test_prompt_input_collection_launch.py`, with an autouse fixture stubbing `record_prompt_placeholders` so nothing touches `~/.sase`.

## Verification

`just check` is green through fmt/lint/mypy/symvision/toobig. `just test`: 22333 passed. `just test-visual`: 355 passed.

Four failures are pre-existing, confirmed by re-running against a stashed tree: `sase validate`'s `init skills --check` reports chezmoi shim drift for the unrelated `sase_beads` skill, and `test_renamed_generic_family_root_png_snapshot` fails identically without my changes. The other two (`test_suite_gate_integration`, `test_diff_cache`) pass in isolation with my changes applied — parallel-load flakes.

Nothing is committed. Phase `docs` (sase-9q.7) still owns the user docs and the `?` help popup, including documenting both new config keys.

Bead is closed. Committing now.

Committed and pushed. Working tree is clean, `master` is level with `origin/master`.

**Commit** `2ce0f956d` — `feat(tui): collect prompt inputs on prompt-bar submit (sase-9q.5)`, covering all six files.

**Bead** `sase-9q.5` was already closed before the commit (verified via `sase bead show`); the commit workflow's own close step is idempotent and re-ran harmlessly. The parent epic `sase-9q` remains open, as does the downstream phase `sase-9q.7`.

One warning from the post-commit step: agent-hood publication for hood `lf` failed with "committing agent 'lf' is absent from project inventory." The primary commit and push both succeeded; sase retries that bookkeeping automatically.
