# Session: toobig-8w.test\_publication\_state\_repair.0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [toobig-8w](../users/bbugyi200/machines/athena/hoods/toobig-8w/README.md) / toobig-8w.test\_publication\_state\_repair.0

Owner: `bbugyi200.athena` · Hood: `toobig-8w` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["toobig-8w.test_publication_state_repair.0--1 [completed]"]
  n1["toobig-8w.test_publication_state_repair.0--plan [completed]"]
  n0 --> n1
  n2["toobig-8w.test_publication_state_repair.0--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | toobig-8w.test\_publication\_state\_repair.0--1 | completed | muse-spark-1.3-contributor / muse | 2026-10-31T05:02:48.004858+00:00 → 2026-10-31T05:10:01.767299+00:00 | [1](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--1/chat.md) |
| <a id="member-plan"></a>plan | toobig-8w.test\_publication\_state\_repair.0--plan | completed | muse-spark-1.3-contributor / muse | 2026-10-31T03:19:50.470985+00:00 → 2026-10-31T03:57:50.351346+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--plan/chat.md) |
| <a id="member-mon"></a>mon | toobig-8w.test\_publication\_state\_repair.0--mon | failed | muse-spark-1.3-contributor / muse | 2026-10-31T03:57:37.212213+00:00 → 2026-10-31T05:00:31.065728+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-8w.test_publication_state_repair.0--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`10f17a3`](https://github.com/sase-org/sase/commit/10f17a39c6a310ec533243c253cabab5da5e1ad6) | refactor(tests): split publication state repair tests into package | 2026-10-31 01:09:51 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [toobig-8w.prompt\_artifact\_staging.0](../agents/bbugyi200.athena.toobig-8w.prompt_artifact_staging.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.publication\_protection.0](../agents/bbugyi200.athena.toobig-8w.publication_protection.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.publication\_snapshot.0](bbugyi200.athena.toobig-8w.publication_snapshot.0.md) (session · 5) | toobig-8w hood | completed 3, failed 2 |
| [toobig-8w.publication\_state\_repair.0](../agents/bbugyi200.athena.toobig-8w.publication_state_repair.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.staged\_handoff.0](../agents/bbugyi200.athena.toobig-8w.staged_handoff.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.start\_stage.0](../agents/bbugyi200.athena.toobig-8w.start_stage.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.test\_agents\_tab\_graph\_isolation.0](../agents/bbugyi200.athena.toobig-8w.test_agents_tab_graph_isolation.0/README.md) | toobig-8w hood | waiting |
| [toobig-8w.test\_cli.0](bbugyi200.athena.toobig-8w.test_cli.0.md) (session · 3) | toobig-8w hood | completed 2, failed 1 |
| [toobig-8w.test\_commit\_publication\_queue.0](../agents/bbugyi200.athena.toobig-8w.test_commit_publication_queue.0/README.md) | toobig-8w hood | completed |
| [toobig-8w.test\_workflow\_completion.0](../agents/bbugyi200.athena.toobig-8w.test_workflow_completion.0/README.md) | toobig-8w hood | waiting |
