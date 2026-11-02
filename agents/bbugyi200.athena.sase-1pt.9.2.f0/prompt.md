%id(bead=sase-1pt.9.2)
%model:gpt-6-astra@xhigh
%auto
#gh:gh_sase-org__sase
#fork:sase-1pt.9.2--plan

The monitor 5zwebkfet1r3 (sase-1pt.9.2 installed proof) was SIGTERM'd by athena's restart at about 07:26 local on 2026-11-01, after 46h 59m 19s.
It never completed, and its follow-up never launched (workspace retention settlement failed: sase_core_rs is importable but does not expose binding 'decide_workspace_retention'; the installed wheel is stale or was built without the shipped bindings. Run `sase update` (or `just install-dev` from your sase checkout).).
Inspect the captured output with sase monitor show 5zwebkfet1r3.
The requested next action, verbatim:
%macros_enabled:false
Complete bead sase-1pt.9.2 using the frozen checkpoint and collection evidence. Read checkpoint artifact file:explicit:7016ae2d8528704b800b8bff and the result/candidates/telemetry under its evidence_directory. Independently verify cohort and exclusions, measure all plan latency/queue metrics, audit every sampled run end to end against sidecar remotes, check backlog conversion/idle cadence/pin conflicts/retention, and publish the report via sase artifact create --bead sase-1pt.9.2. Record missed-target causes as PROPOSED FOLLOW-UP notes on this phase. Run sase bead epic-symbols sase-1pt.9.2 and close only this phase after the complete audit; never its parents, no new beads and no memory edits. If collection has fewer than 30 verified runs, preserve the evidence and arrange the necessary continuation without claiming proof. The install prerequisites are already verified; do not repeat the failed old gate command. Use sase_final before a normal turn-ending response.
%macros_enabled:true
Re-check the awaited condition now; if it still does not hold, re-arm the same wait through /sase_monitor instead of ending idle.
Continue stranded phase sase-1pt.9.2 from last turn sase-1pt.9.2--plan. Re-read sase bead read sase-1pt.9.2, including notes, finish the phase, and close only that phase. If it must stay open, arrange a durable continuation before ending.