# Chat History - ace-run (research.1g.cdx)

- **TIMESTAMP:** 2026-09-05 18:41:37 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.1g.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260905_182106.md`

## Prompt

%clan(research.1g, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).
- I already did some research on this (see the tailnet_agent_fleet.md file in the
  research sidecar repo), but have since decided to remove the `agent_sync` import leg
  (see the sase-ws epic bead and the sase_collaboration_architecture.md file in the
  research sidecar repo for context). Review the tailnet_agent_fleet.md file for context
  and inspiration before performing your own (much improved I would expect, since you
  have more up-to-date information and a better starting point) research.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable, robust, and beautiful.]]) %id:research.1g.cdx
%model:@research_a 
#gh:gh_sase-org__sase I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).
- I already did some research on this (see the tailnet_agent_fleet.md file in the
  research sidecar repo), but have since decided to remove the `agent_sync` import leg
  (see the sase-ws epic bead and the sase_collaboration_architecture.md file in the
  research sidecar repo for context). Review the tailnet_agent_fleet.md file for context
  and inspiration before performing your own (much improved I would expect, since you
  have more up-to-date information and a better starting point) research.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable, robust, and beautiful. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the SASE repository and audited-memory workflows because the requested inputs and output live in a research sidecar, and I’ll review the bead/artifact rules before inspecting the prior research. Then I’ll validate the current technical options against primary sources and write a decision-oriented report ending in one recommended architecture.

The prior collaboration report confirms the new boundary: live fleet control is a same-user process-plane feature, while `agent_sync` import/materialization is gone. I’m now extracting the original fleet proposal and the `sase-ws` cutover details, then I’ll stress-test the proposal’s transport, identity, recovery, and UX assumptions against the current SASE architecture.

A current-code audit sharpens the earlier proposal in two important ways: the mobile gateway already has pairing, audit logs, agent list/launch/kill/retry, and SSE replay scaffolding, but its agent reads still fork Python and its SSE connection only emits live heartbeats after initial replay. Also, `request_id` is carried on launch requests but does not yet make ordinary mobile launches exactly-once, so remote launch cannot be considered safe until host-side deduplication is durable.

The key design consequence is now clear: the remote fleet should be a live process-control plane, not another replication path. I’m turning that into a concrete v2 architecture, including the security fixes and failure semantics the existing gateway would need before it is safe to expose across the tailnet.

The draft now recommends a direct per-host control plane over Tailscale Serve, with snapshot reconciliation and durable operations. I’ve also made the non-obvious hazards explicit: remote pairing is currently self-authorizable, SSE does not yet broadcast live changes, and today’s launch `request_id` does not provide exactly-once behavior.

The report itself is complete and passes the repository’s whitespace checks. Artifact registration succeeded; the link indexer also created a local metadata commit and warned that this ephemeral checkout cannot publish it directly. I’m inspecting that bookkeeping now so the final handoff declares the exact repository state without pushing or bypassing SASE’s host-owned finalizer.

The report is finished at 3,708 words, ends with the requested recommendation, and is registered as `file:explicit:ae30a4f43ec627db27cec11d` with provenance links to both earlier reports and `sase-ws`. Validation found and removed two Markdown trailing-space issues; the final file now passes the check.

Completed the research report:

[tailnet_agent_fleet_v2.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202609/tailnet_agent_fleet_v2.md)

The recommendation is:

- Extend the existing Rust `sase_gateway` into a supervised per-host fleet daemon.
- Expose each host through its own [Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve) endpoint.
- Federate hosts directly in ACE using cache-first providers.
- Use HTTP snapshots plus SSE invalidations—not replicated agent state.
- Keep the `agent_sync` import leg permanently removed.
- Use immutable host/run identities and a durable operation journal for safe retries.
- Fix pairing, token scoping, and fingerprint pinning before enabling remote mutations.
- Avoid Tailscale Services because its interchangeable-host routing does not preserve process ownership ([documentation](https://tailscale.com/docs/features/tailscale-services)).

The report includes code-audit findings, live latency measurements, alternatives, rollout phases, security design, TUI behavior, and acceptance tests.

Registered artifact: `file:explicit:ae30a4f43ec627db27cec11d`.
