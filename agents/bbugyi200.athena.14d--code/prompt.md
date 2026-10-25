%model:@small
#gh:gh_sase-org__sase @plan:202610/gate_command_exec_header.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- unstartable_recovery = narrow (planner default: narrow). Implement the "unstartable_recovery = narrow" branch; ignore "unstartable_recovery = keep". Context: "Should a gate command that can never start (ENOEXEC) get its own failure code whose recovery offers only cancel?".
Implement only the branches selected above.
