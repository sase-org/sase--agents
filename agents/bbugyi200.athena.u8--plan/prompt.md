#gh:gh_sase-org__sase The `just test` command is failing (see the command output below). Can you help me diagnose the root cause of this issue and fix it? #plan #m_opus 
```
============================================================================= short test summary info ==============================================================================
FAILED tests/test_artifact_file_e2e.py::test_reference_expansion_updates_unused_and_show_consumption - AssertionError: assert 1 == 0
FAILED tests/test_plan_search_cli.py::test_handler_rejects_negative_limit - sase.sdd._store_types.SddMaterializationError: could not resolve the owning SASE project key for the agents sidecar from /home/bryan/projects/github/sase-org/sase
FAILED tests/test_plan_search_cli.py::test_handler_rejects_invalid_date - sase.sdd._store_types.SddMaterializationError: could not resolve the owning SASE project key for the agents sidecar from /home/bryan/projects/github/sase-org/sase
FAILED tests/test_bead/test_claimed_status.py::test_show_explains_claim_owner - sase.sdd._store_types.SddMaterializationError: could not resolve the owning SASE project key for the agents sidecar from /home/bryan/projects/github/sase-org/sase
======================================================= 4 failed, 26020 passed, 7 skipped, 69 warnings in 185.13s (0:03:05) ========================================================
```