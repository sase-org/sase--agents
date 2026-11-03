%model:@medium
#gh:gh_sase-org__sase @plan:202611/flag_removal_close_gate_deadlock.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- gate_checkout = auto (planner default: auto). Implement the "gate_checkout = auto" branch; ignore "gate_checkout = message_only". Context: "Should a gate command's `sase bead close` automatically run its guards against the checkout its gate turn inherits?".
Implement only the branches selected above.
