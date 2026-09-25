#gh:gh_sase-org__sase Can you help me fix this command (see the command output below for context)? I'm not sure how this `--epic-symbol "sase-n4(get_usage_limit_config)"` option got added, so make sure you track down the root cause and think hard about the appropriate fix to apply. #plan 
```
❯ just symvision

┌───────────────────────────────────────────────────────┐
│                RUNNING: just symvision                │
└───────────────────────────────────────────────────────┘
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github from /home/bryan/projects/github/sase-org/sase-github.
[setup] Installing required plugin sase-research-artifacts from /home/bryan/projects/github/sase-org/sase-research-artifacts.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-n4(get_usage_limit_config)" --epic-symbol "sase-xe(FollowStoreMutationOutcome)" --epic-symbol "sase-xe(follow_store_path)" --epic-symbol "sase-xe(is_followed)" --epic-symbol "sase-xe(reconcile_follow_store)"
Error: --epic-symbol 'sase-n4(get_usage_limit_config)': bead 'sase-n4' not found. Remove this --epic-symbol entry.
error: recipe `_lint-symvision` failed on line 343 with exit code 1
error: recipe `symvision` failed on line 806 with exit code 1
```