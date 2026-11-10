%model:@medium
#gh:gh_sase-org__sase @plan:202611/sudo_remote_snapshot_and_macos_tcc.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- unreachable_target = fail (planner default: fail). Implement the "unreachable_target = fail" branch; ignore "unreachable_target = unverified". Context: "Should `sase sudo request` fail when it cannot snapshot executables on the remote target?".
- tcc_surfaces = full (planner default: full). Implement the "tcc_surfaces = full" branch; ignore "tcc_surfaces = docs_only". Context: "Should sase show macOS Full Disk Access warnings and failure hints, not just document them?".
Implement only the branches selected above.
%macros_enabled:true
