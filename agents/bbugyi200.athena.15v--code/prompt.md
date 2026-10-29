%model:@medium
#gh:gh_sase-org__sase @plan:202610/agents_monitoring_status_group.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- machine_subgroups = include (planner default: include). Implement the "machine_subgroups = include" branch; ignore "machine_subgroups = status_only". Context: "Should BY_MACHINE status subgroups also split out a Monitoring subgroup?".
- clans = include (planner default: include). Implement the "clans = include" branch; ignore "clans = sessions_only". Context: "Should a clan row that mirrors its lone monitoring member also move into Monitoring?".
- position = after_running (planner default: after_running). Implement the "position = after_running" branch; ignore "position = after_waiting". Context: "Should Monitoring sit directly after Running in the BY_STATUS order?".
Implement only the branches selected above.
