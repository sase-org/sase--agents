# Session: toobig-50.artifact\_ref\_models.0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [toobig-50](../users/bbugyi200/machines/athena/hoods/toobig-50/README.md) / toobig-50.artifact\_ref\_models.0

Owner: `bbugyi200.athena` · Hood: `toobig-50` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["toobig-50.artifact_ref_models.0--plan [dismissed]"]
  n1["toobig-50.artifact_ref_models.0--1 [dismissed]"]
  n0 --> n1
  n2["toobig-50.artifact_ref_models.0--mon [dismissed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | toobig-50.artifact\_ref\_models.0--plan | dismissed | gpt-5.5 / codex | 2026-09-08T19:31:25.575709 → 2026-09-08T20:11:41.944103 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--plan/chat.md) |
| <a id="member-1"></a>1 | toobig-50.artifact\_ref\_models.0--1 | dismissed | gpt-5.5 / codex | 2026-09-08T20:44:48.948378 → 2026-09-08T20:50:44.599339 | [1](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--1/chat.md) |
| <a id="member-mon"></a>mon | toobig-50.artifact\_ref\_models.0--mon | dismissed | gpt-5.5 / codex | 2026-09-08T20:11:28.428385 → 2026-09-08T20:43:14.926055 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-50.artifact_ref_models.0--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | — | `7678e4f` | refactor(artifact-ref): split artifact reference models | 2026-09-08 20:48:33 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [toobig-50.processing.0](../agents/bbugyi200.athena.toobig-50.processing.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.resolve.0](../agents/bbugyi200.athena.toobig-50.resolve.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.store.0](../agents/bbugyi200.athena.toobig-50.store.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.test\_app.0](../agents/bbugyi200.athena.toobig-50.test_app.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.test\_command\_availability\_agents.0](../agents/bbugyi200.athena.toobig-50.test_command_availability_agents.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.test\_notify\_handler.0](../agents/bbugyi200.athena.toobig-50.test_notify_handler.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.test\_resolve.0](../agents/bbugyi200.athena.toobig-50.test_resolve.0/README.md) | toobig-50 hood | dismissed |
| [toobig-50.test\_view\_files\_pager.0](../agents/bbugyi200.athena.toobig-50.test_view_files_pager.0/README.md) | toobig-50 hood | dismissed |
