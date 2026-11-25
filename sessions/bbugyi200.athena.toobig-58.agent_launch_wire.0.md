# Session: toobig-58.agent\_launch\_wire.0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [toobig-58](../users/bbugyi200/machines/athena/hoods/toobig-58/README.md) / toobig-58.agent\_launch\_wire.0

Owner: `bbugyi200.athena` · Hood: `toobig-58` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["toobig-58.agent_launch_wire.0--1 [dismissed]"]
  n1["toobig-58.agent_launch_wire.0--mon [dismissed]"]
  n0 --> n1
  n2["toobig-58.agent_launch_wire.0--plan [dismissed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | toobig-58.agent\_launch\_wire.0--1 | dismissed | grok-4.6 / grok | 2026-09-11T20:09:15.385228 → 2026-09-11T20:19:58.171858 | [1](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--1/chat.md) |
| <a id="member-mon"></a>mon | toobig-58.agent\_launch\_wire.0--mon | dismissed | grok-4.6 / grok | 2026-09-11T19:46:57.067443 → 2026-09-11T20:07:41.837396 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--mon/chat.md) |
| <a id="member-plan"></a>plan | toobig-58.agent\_launch\_wire.0--plan | dismissed | grok-4.6 / grok | 2026-09-11T19:30:22.090077 → 2026-09-11T19:47:09.588794 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-58.agent_launch_wire.0--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | — | `a694708` | refactor(core): split agent\_launch\_wire into sibling modules | 2026-09-11 20:17:36 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [toobig-58.continuation.0](bbugyi200.athena.toobig-58.continuation.0.md) (session · 3) | toobig-58 hood | dismissed 3 |
| [toobig-58.continuation\_capture.0](../agents/bbugyi200.athena.toobig-58.continuation_capture.0/README.md) | toobig-58 hood | dismissed |
| [toobig-58.runner\_workspace.0](bbugyi200.athena.toobig-58.runner_workspace.0.md) (session · 3) | toobig-58 hood | dismissed 3 |
| [toobig-58.test\_llm\_provider\_invoke.0](bbugyi200.athena.toobig-58.test_llm_provider_invoke.0.md) (session · 3) | toobig-58 hood | dismissed 3 |
| [toobig-58.test\_repo\_handler\_open.0](../agents/bbugyi200.athena.toobig-58.test_repo_handler_open.0/README.md) | toobig-58 hood | dismissed |
