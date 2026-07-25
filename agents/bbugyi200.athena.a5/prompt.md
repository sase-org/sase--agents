#gh:gh_sase-org__sase The `just symvision` command is failing (see the output below). Can you help me fix this?
```
❯ just symvision

┌───────────────────────────────────────────────────────┐
│                RUNNING: just symvision                │
└───────────────────────────────────────────────────────┘
BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _active_status_for_record in src/sase/agent/running_listing.py
  _clear_stale_git_index_lock in src/sase/axe/runner_workspace.py
  _ensure_materialized_store_initialized in src/sase/sdd/_store_materialization.py
  _external_repo_records in src/sase/_repo_inventory_workspaces.py
  _finalize_existing_store in src/sase/sdd/_store_materialization.py
  _inherited_sdd_record_owner_anchor in src/sase/sdd/_store_workspace.py
  _is_remote_backed_record in src/sase/sdd/_store_materialization.py
  _is_sidecar_record in src/sase/sdd/_store_materialization.py
  _legacy_adoption_needed in src/sase/sdd/_store_materialization.py
  _materialize_sdd_store in src/sase/sdd/_store_materialization.py
  _normalize_path in src/sase/_repo_inventory_workspaces.py
  _normalize_path in src/sase/llm_provider/commit_finalizer_git.py
  _positive_result in src/sase/sdd/_store_materialization.py
  _provider_materialization_result in src/sase/sdd/_store_materialization.py
  _provider_options in src/sase/sdd/_sidecar_init.py
  _provider_options in src/sase/sdd/_store_materialization.py
  _repo_clones in src/sase/_repo_inventory_workspaces.py
  _resolve_sdd_storage in src/sase/sdd/_store_resolution.py
  _sdd_creation_authorized in src/sase/sdd/_store_materialization.py
  _sdd_dir_for_storage in src/sase/sdd/_store_resolution.py
  _usable_primary_record in src/sase/sdd/_store_materialization.py
  _workspace_checkouts in src/sase/_repo_inventory_workspaces.py
error: recipe `_lint-symvision` failed on line 155 with exit code 1
error: recipe `symvision` failed on line 389 with exit code 1
```