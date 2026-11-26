- **AGENTS:**
  - [bbugyi200.athena.1gt](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gt.md)
- **ARTIFACTS:**
  - [sase_core_release_cut_wait_budget.md](https://github.com/sase-org/sase--plans/blob/55a613b40912a735958bc0b37e491956f00d1b76/202611/sase_core_release_cut_wait_budget.md)

%model:@small #gh:gh_sase-org__sase
[@plan:202611/sase_core_release_cut_wait_budget.md][1]

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false Reviewer decisions for this plan (final · reviewer via ACE):

- dispatch_cut = defer (planner default: defer). Implement the "dispatch_cut = defer"
  branch; ignore "dispatch_cut = gate". Context: "After the fix lands, should the
  implementer propose an immediate release cut that ships sase-core-rs 0.45.0?".
  Implement only the branches selected above. %macros_enabled:true

[1]:
  https://github.com/sase-org/sase--plans/blob/55a613b40912a735958bc0b37e491956f00d1b76/202611/sase_core_release_cut_wait_budget.md
