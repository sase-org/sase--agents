# Chat History - ace-run (toobig-8w.prompt_artifact_staging.0)

- **TIMESTAMP:** 2026-10-30 18:59:48 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8w.prompt_artifact_staging.0

## Prompt

%auto
%id(prompt_artifact_staging.0, clan=toobig-8w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/core/prompt_artifact_staging.py` file into multiple files? Use your best
%wait:toobig-8w.publication_state_repair.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll start by reading the split target, its tests, and the lint/test notes so the module boundaries stay under 500 lines without breaking public imports.

The source is 718 lines. Next I’ll map its public API, private helpers, and test monkeypatch targets so the split keeps the original import path.

I’ll look at a recent split in this package and at the remaining consumers so the new modules follow the same layout.

The split will be a public facade plus pool, stage, capture, and a private shared module so every file stays under 500 lines.

I'll retarget the tests that imported private names or patched helpers that now live in the split modules.

Formatting is clean. Next I’ll run the three named lints on the split files.

Symvision and mypy passed. The toobig failure is in an unrelated file, so I’ll run the staging tests and then `sase tool run check`.

Targeted tests passed. I'll run `sase tool run check` inline next, as this repo's check is a short catalog tool.

Check failed on two tests. I’ll inspect the NEW failure to see whether the split caused it.

Split `src/sase/core/prompt_artifact_staging.py` (718 lines) into a public facade plus four implementation modules, each well under 500 lines. `from sase.core.prompt_artifact_staging import …` still works for the original public names.

The layout:

- `prompt_artifact_staging.py` — facade re-exporting `stage_prompt_artifact`, `capture_prompt_file_ref`, `PromptArtifactRecord`, and the public constants
- `prompt_artifact_staging_stage.py` — file/locator staging and VCS provenance
- `prompt_artifact_staging_capture.py` — `@file:<path>` capture
- `prompt_artifact_staging_pool.py` — pool storage, manifest append, and budget GC
- `_prompt_artifact_staging_shared.py` — shared types and helpers as public names in a private module

No `_`-prefixed names are imported across the new production modules. Tests that patched `collect_repo_inventory`, `capture_file_exceeds_size_limit`, and `get_artifact_capture_pool_max_bytes`, or imported `_prune_prompt_artifact_pool` / `_NON_FILE_REF_KINDS`, now target the modules that own those names.

Verification:

- `just _lint-symvision` passed
- `just _lint-mypy` passed
- `just _lint-toobig` failed on unrelated `src/sase/monitor/start_stage.py` (1084 lines); every file this split touched is under 300 lines
- Targeted staging tests: 56 passed
- `sase tool run check` (`0d467feeeaae777248cd489a1b8bbb23`): 59,197 passed; 1 FLAKY (`test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited`); 1 NEW that passed on isolation rerun (`test_cancel_saves_once_submit_path_quiet`). That NEW node is the existing flake bead `sase-1gg`; I recorded a +1 with this run’s evidence.
