%model:@small
#gh:gh_sase-org__sase @plan:202610/host_completion_reasons_wait_wedge.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- apollo_unblock = gate (planner default: gate). Implement the "apollo_unblock = gate" branch; ignore "apollo_unblock = manual". Context: "Should the implementing agent unblock apollo's parked waiters through a /sase_gate after the fix is verified?".
- stale_a013_followup = kill (planner default: kill). Implement the "stale_a013_followup = kill" branch; ignore "stale_a013_followup = release". Context: "Should bob-cli-a0.13--1 be stopped before apollo is unblocked?".
Implement only the branches selected above.
