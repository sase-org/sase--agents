# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 18:08:31 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.f.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_175250.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I would like to add support for running multiple agent children in the same family in parallel so I can support a few different use cases:
1. Running all phase agents and the agent that lands the epic in the same agent family
2. Doing the same thing for the research_swarm_kiss that lives in my chezmoi repo.

This will have several benefits, including saving space on the agents tab and allowing the user to see all of the agent metadata for all of the agents related to a particular Epic on a single panel. The root agent entry that contains all of the Epic agents should consolidate the metadata from all of them.

Can you do some research to help me understand how feasible this is and what other design decisions need to be made before we can start implementing this? End your analysis with a recommended solution Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to trace the current agent-family lifecycle, metadata aggregation, and workflow launch model, then compare it with the epic and `research_swarm_kiss` workflows. I’m using the SASE memory-read skill for the xprompt/TUI rules and the repo skill for the research sidecar and chezmoi checkout, as required by this project.

The research crosses two guarded areas: xprompt launch semantics and Agents-tab responsiveness. I’m loading both design notes before inspecting code, plus the generated-skill note because the chezmoi workflow may be deployed from a SASE template.

The two external checkouts are now opened through SASE. I’ll first map the existing family/parent invariants and identify where “one child at a time” is enforced—launch parsing, persistence, process orchestration, or only the UI—because feasibility depends on which layer owns that constraint.

The documented model already permits sibling children to become runnable together once a common parent succeeds. The important limitation is attachment semantics: every `%n(parent, suffix)` currently creates an implicit dependency on that exact parent, and the family base is also used as the dependency identity. I’m checking whether that coupling can be relaxed cleanly or whether epic launches need a first-class family declaration.

A key architectural split is now clear: family membership, parent/child lineage, workspace inheritance, and execution dependency are currently bundled into one `%n(parent, suffix)` operation. That works for serial plan chains, but both requested use cases need membership without an implicit dependency and without inheriting one shared workspace. I’m tracing the epic wave planner next to see how much of that can be preserved.

The epic planner itself is cleanly separated: Rust computes the DAG waves and deterministic names; Python renders one segment per phase plus the land segment and supplies per-segment metadata. I’m opening the sibling core through SASE now to confirm whether adding family identity belongs in the wire model or can remain launch-layer presentation metadata.

The current details panel is only partly family-aware. Replies, tool calls, SASE context events, output variables, and some status/timestamp fields aggregate; commits, deltas, artifacts, top-level model/workspace fields, and arbitrary child timestamps do not consistently aggregate. The design therefore needs one shared “family members” projection and explicit attribution rules, not more one-off copies onto the root.

There is already July research on agent-family unification and dynamic-family design in the research sidecar. I’m incorporating it as prior art and checking its conclusions against the current code, so the new report can focus on what is still undecided rather than repeating stale assumptions.

Two non-obvious correctness hazards rule out a UI-only change: children linked through `parent_timestamp` are treated as follow-ups in several lifecycle paths, and running-parent attachment defers them into the parent’s workspace. Reusing either mechanism for peer workers would distort runner-cap accounting and could serialize or co-locate work that is parallel today. I’m validating those admission and failure paths before drafting.

I’ve finished the feasibility pass. The narrow feature is achievable without inventing a new scheduler: both use cases already have static dependency graphs and independent launch slots. The durable fix is to add a static family/run-group manifest that is orthogonal to `%wait` and workspace allocation, then make ACE render and aggregate from that manifest. I’m drafting the report with the concrete epic and research-swarm mappings plus the decisions that must be locked first.

Research is complete: [parallel_agent_family_children_feasibility.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202607/parallel_agent_family_children_feasibility.md).

Main recommendation: introduce a persisted static run-group manifest, keeping family membership independent from waits, workspaces, and runner admission. The epic lander and research lead become the displayed roots, with metadata aggregated through one Rust-backed family projection.

No source code was changed. I also noted that the current chezmoi revision contains `research_swarm.md`, but no literal `research_swarm_kiss`; the report documents that assumption.

The research file is my change, so I’m handling the required finalizer now. I’m using the SASE git-commit skill to commit only that markdown file in the research sidecar, then I’ll verify the checkout is clean.

The sidecar contains only the new report, and the diff matches the completed research. I’m committing it as a documentation-only change with an explicit file scope, so no unrelated files can be staged.

Committed the research report as `a7418cf` (`docs: research parallel agent family design`).

Report: [parallel_agent_family_children_feasibility.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202607/parallel_agent_family_children_feasibility.md)

The research sidecar is clean and synchronized with `origin/main`.
