%model:@medium
#gh:gh_sase-org__sase @plan:202611/artifact_link_backfill_timeouts.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- outbox_retention = keep (planner default: keep). Implement the "outbox_retention = keep" branch; ignore "outbox_retention = days14". Context: "Should a terminal agent's never-publishable outbox rows leave the live queue 14 days after it finishes, instead of 90?".
Implement only the branches selected above.
%macros_enabled:true
