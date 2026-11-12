# Chat History - ace-run (toobig-9s.loader_sources.0)

- **TIMESTAMP:** 2026-11-12 09:30:20 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9s.loader_sources.0

## Prompt

%auto
%id(loader_sources.0, clan=toobig-9s)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/macro/loader_sources.py` file into multiple files? Use your best
%wait:toobig-9s.core.0
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

Done. Split `src/sase/macro/loader_sources.py` (759 lines) into a facade plus five modules, all under 500 lines.

New layout (verified each file's line count, largest is 301):

- [loader_sources.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/loader_sources.py) (55 lines) — facade re-exporting the original 18 public names; the public import path is unchanged.
- [_loader_sources_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/_loader_sources_common.py) — the already-private module holding shared helpers under public names: `namespace_macro`, `load_macro_from_file`, `load_ordinary_macros_from_dir`, `parse_markdown_local_macros`.
- [loader_sources_files.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/loader_sources_files.py) — package dirs, search paths, file/internal/default loaders.
- [loader_sources_config.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/loader_sources_config.py) — `load_macros_from_config`.
- [loader_sources_plugins.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/loader_sources_plugins.py) — plugin loaders.
- [loader_sources_projects.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/macro/loader_sources_projects.py) — project, lifecycle, and local-config/workflow loaders; `_project_ref_candidates` stayed private there since only it uses it.

Behavior: all 21 function bodies are AST-identical to the committed version apart from the two intentional `_private` → public helper renames and one added docstring. No `_`-prefixed name is imported across the new modules. All other consumers (`loader.py`, `loader_skills.py`, `project_identity.py`, `workflow_loader_sources.py`, the TUI catalog) keep importing from the facade untouched.

Tests: retargeted every `loader_sources.<dep>` patch/seam to the module that now owns the lookup (`_plugins`, `_files`, `_config`, `_projects`), and added the two moved `"xprompts"` string pairs plus the per-file reason for `loader_sources_files.py` to the terminology guard.

Verification actually observed: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each exit 0; 219 + 17 targeted tests pass; `sase tool run check` (run `cd82b4e5`) ends with triage verdict pass, including the 1179-file scoped test lane.

Declaration submitted: `loader_sources` split committed via `commit` payload.
