- **AGENTS:**
  - [bbugyi200.athena.1hb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hb.md)
- **ARTIFACTS:**
  - [artifact_link_job_budgets.md](https://github.com/sase-org/sase--plans/blob/aacdccdbc939c37e044b0570923839c5ec98f9e7/202611/artifact_link_job_budgets.md)

%model:@medium #gh:gh_sase-org__sase [@plan:202611/artifact_link_job_budgets.md][1]

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false Reviewer decisions for this plan (final · reviewer via ACE):

- raise_backfill_timeout = keep (planner default: keep). Implement the
  "raise_backfill_timeout = keep" branch; ignore "raise_backfill_timeout = raise".
  Context: "Should the housekeeping `artifact_link_backfill` job's axe timeout also be
  raised from 5m to 10m as a backstop?". Implement only the branches selected above.
  %macros_enabled:true

[1]:
  https://github.com/sase-org/sase--plans/blob/aacdccdbc939c37e044b0570923839c5ec98f9e7/202611/artifact_link_job_budgets.md
