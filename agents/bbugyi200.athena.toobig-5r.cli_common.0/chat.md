# Chat History - ace-run (toobig-5r.cli_common.0)

- **TIMESTAMP:** 2026-09-21 15:56:59 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.cli_common.0

## Prompt

%id(cli_common.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/bead/cli_common.py` file up into multiple files? Use your best
%wait:toobig-5r.loader_refresh.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Verification is still running — I'll report once it completes.

Done. Split the 711-line `cli_common.py` into 5 files, all ≤500 lines, with `just check` passing.

New layout (all under `src/sase/bead/`):

| File | Lines | Contents |
|---|---|---|
| [cli_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/bead/cli_common.py) | 422 | Facade + store access (`init_beads`, `get_project`, `get_read_view`) + mutation lane (`auto_commit_bead_store`, `bead_store_mutation` and its private helpers); re-exports everything with `__all__` |
| [cli_common_publication.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/bead/cli_common_publication.py) | 113 | `BeadPublicationError`, routed-publication checks, `ensure_bead_mutation_published` |
| [cli_common_routing.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/bead/cli_common_routing.py) | 50 | `resolve_bead_operation_context` |
| [cli_common_paths.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/bead/cli_common_paths.py) | 186 | `normalize_workspace_path`, `storage_plan_path` and helpers |
| [cli_common_presentation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/bead/cli_common_presentation.py) | 26 | `status_icon`, `created_cell` |

Compatibility notes:

- The full `sase.bead.cli_common` import surface is preserved, including the `_BeadsLocation` alias and `_push_committed_bead_store` that tests patch.
- The mutation lane and its private helpers stay in the facade so existing `sase.bead.cli_common.*` test patches keep working; moved code was kept verbatim.
- One iteration was needed: the symvision gate forbids importing private names across files, so the three privates used by `bead_store_mutation` live in the facade rather than the publication module.

Verification: `just fmt` clean, `just check` exit 0 (all lint gates including ruff, mypy, symvision, plus the diff-scoped test lane).
