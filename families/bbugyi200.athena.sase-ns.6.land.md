# Family: sase-ns.6.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ns](../users/bbugyi200/machines/athena/hoods/sase-ns/README.md) / sase-ns.6.land

Owner: `bbugyi200.athena` · Hood: `sase-ns` · Members: 4 · Bead: [sase-ns.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ns/sase-ns.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ns.6.land--1 [failed]"]
  n1["sase-ns.6.land--plan [completed]"]
  n0 --> n1
  n2["sase-ns.6.land--mon [failed]"]
  n0 --> n2
  n3["sase-ns.6.land--mon-0 [failed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-ns.6.land--1 | failed | opus / claude | 2026-08-17T02:20:34.956613+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ns.6.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ns.6.land--1/chat.md) |
| <a id="member-plan"></a>plan | sase-ns.6.land--plan | completed | opus / claude | 2026-08-17T01:49:18.813946+00:00 | [1](../agents/bbugyi200.athena.sase-ns.6.land--plan/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-ns.6.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ns.6.land--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-ns.6.land--mon | failed | opus / claude | 2026-08-17T02:20:06.319867+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.land--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-ns.6.land--mon-0 | failed | opus / claude | 2026-08-17T08:03:05.529981+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.land--mon-0/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| plan | sase | [`5feaabc`](https://github.com/sase-org/sase/commit/5feaabc7122423aff552188be0e662cf2d538684) | fix(selection-health): retire the fixed config-center node's evidence | 2026-08-16 22:11:36 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ns.6.1](bbugyi200.athena.sase-ns.6.1.md) (family · 2) | sase-ns.6 hood | completed 2 |
| [sase-ns.6.2](bbugyi200.athena.sase-ns.6.2.md) (family · 2) | sase-ns.6 hood | completed 2 |
| [sase-ns.6.3](../agents/bbugyi200.athena.sase-ns.6.3/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.4](../agents/bbugyi200.athena.sase-ns.6.4/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.5](../agents/bbugyi200.athena.sase-ns.6.5/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.6.1](../agents/bbugyi200.athena.sase-ns.6.6.1/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.2/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.6.3](../agents/bbugyi200.athena.sase-ns.6.6.3/README.md) | sase-ns.6 hood | completed |
| [sase-ns.6.6.4](bbugyi200.athena.sase-ns.6.6.4.md) (family · 4) | sase-ns.6 hood | completed 3, failed 1 |
| [sase-ns.6.6.5](bbugyi200.athena.sase-ns.6.6.5.md) (family · 4) | sase-ns.6 hood | completed 3, failed 1 |
| [sase-ns.6.6.6.1](bbugyi200.athena.sase-ns.6.6.6.1.md) (family · 4) | sase-ns.6 hood | active 3, failed 1 |
| [sase-ns.6.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.6.2/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.6.6.3](bbugyi200.athena.sase-ns.6.6.6.3.md) (family · 2) | sase-ns.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.6.6.4](../agents/bbugyi200.athena.sase-ns.6.6.6.4/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.6.6.5](../agents/bbugyi200.athena.sase-ns.6.6.6.5/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.6.land/README.md) | sase-ns.6 hood | waiting |
| [sase-ns.6.6.land](bbugyi200.athena.sase-ns.6.6.land.md) (family · 4) | sase-ns.6 hood | completed 1, failed 3 |
| [sase-ns.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.land/README.md) | sase-ns.6 hood | completed |
| [sase-ns.1](bbugyi200.athena.sase-ns.1.md) (family · 4) | sase-ns hood | completed 2, dismissed 1, failed 1 |
| [sase-ns.2](bbugyi200.athena.sase-ns.2.md) (family · 8) | sase-ns hood | completed 4, dismissed 1, failed 3 |
| [sase-ns.3](bbugyi200.athena.sase-ns.3.md) (family · 2) | sase-ns hood | completed 1, dismissed 1 |
| [sase-ns.4](../agents/bbugyi200.athena.sase-ns.4/README.md) | sase-ns hood | dismissed |
| [sase-ns.5](../agents/bbugyi200.athena.sase-ns.5/README.md) | sase-ns hood | dismissed |
| [sase-ns.land](bbugyi200.athena.sase-ns.land.md) (family · 4) | sase-ns hood | dismissed 1, failed 3 |
| [sase-ns.land](../agents/bbugyi200.athena.sase-ns.land/README.md) | sase-ns hood | completed |
