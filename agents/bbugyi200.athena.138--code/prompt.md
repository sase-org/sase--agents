%model:@medium
#gh:gh_sase-org__sase @plan:202610/sudo_finalize_settle_lock_race.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- gate_cli_scope = sudo_and_gate_cli (planner default: sudo_and_gate_cli). Implement the "gate_cli_scope = sudo_and_gate_cli" branch; ignore "gate_cli_scope = sudo_only". Context: "Should `sase gate answer` (fresh and --resume) also wait out follow-up lock contention?".
Implement only the branches selected above.
