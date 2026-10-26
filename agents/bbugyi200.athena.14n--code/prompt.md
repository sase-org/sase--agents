%model:@medium
#gh:gh_sase-org__sase @plan:202610/sase_core_runner_starvation_retry.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- scope = both (planner default: both). Implement the "scope = both" branch; ignore "scope = release". Context: "Should the automatic rerun also watch the CI workflow, not just Release-plz?".
- retries = one (planner default: one). Implement the "retries = one" branch; ignore "retries = two". Context: "Should a run get a second automatic rerun when the first rerun is also starved?".
Implement only the branches selected above.
