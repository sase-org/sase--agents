# Family: sase-m6.7.1.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-m6](../users/bbugyi200/machines/athena/hoods/sase-m6/README.md) / sase-m6.7.1.2

Owner: `bbugyi200.athena` · Hood: `sase-m6` · Members: 4 · Bead: [sase-m6.7.1.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-m6/sase-m6.7.1.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-m6.7.1.2--plan [dismissed]"]
  n1["sase-m6.7.1.2--1 [completed]"]
  n0 --> n1
  n2["sase-m6.7.1.2--mon [failed]"]
  n0 --> n2
  n3["sase-m6.7.1.2--code [completed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-m6.7.1.2--plan | dismissed | — | 2026-08-16T02:55:49 | 0 | — | — |
| <a id="member-1"></a>1 | sase-m6.7.1.2--1 | completed | grok-4.6 / grok | 2026-08-16T08:18:37.659078+00:00 | [1](../agents/bbugyi200.athena.sase-m6.7.1.2--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-m6.7.1.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m6.7.1.2--1/chat.md) |
| <a id="member-mon"></a>mon | sase-m6.7.1.2--mon | failed | grok-4.6 / grok | 2026-08-16T08:05:31.134885+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.7.1.2--mon/chat.md) |
| <a id="member-code"></a>code | sase-m6.7.1.2--code | completed | grok-4.6 / grok | 2026-08-16T07:35:13.557025+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.7.1.2--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`708c254`](https://github.com/sase-org/sase/commit/708c254523118a65c7d5f85eec42fa152c02ec97) | feat(artifacts): add host-owned RelationIndex for Artifacts panes | 2026-08-16 04:32:00 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-m6.7](bbugyi200.athena.sase-m6.7.md) (family · 2) | ancestor | failed 2 |
| [sase-m6.7.1.1](../agents/bbugyi200.athena.sase-m6.7.1.1/README.md) | sase-m6.7.1 hood | dismissed |
| [sase-m6.7.1.3](bbugyi200.athena.sase-m6.7.1.3.md) (family · 8) | sase-m6.7.1 hood | completed 4, dismissed 1, failed 3 |
| [sase-m6.7.1.4](bbugyi200.athena.sase-m6.7.1.4.md) (family · 3) | sase-m6.7.1 hood | completed 1, dismissed 1, failed 1 |
| [sase-m6.7.1.5](bbugyi200.athena.sase-m6.7.1.5.md) (family · 2) | sase-m6.7.1 hood | completed 1, dismissed 1 |
| [sase-m6.7.1.6](bbugyi200.athena.sase-m6.7.1.6.md) (family · 3) | sase-m6.7.1 hood | dismissed 2, failed 1 |
| [sase-m6.7.1.land](../agents/bbugyi200.athena.sase-m6.7.1.land/README.md) | sase-m6.7.1 hood | dismissed |
| [sase-m6.1](../agents/bbugyi200.athena.sase-m6.1/README.md) | sase-m6 hood | completed |
| [sase-m6.10](../agents/bbugyi200.athena.sase-m6.10/README.md) | sase-m6 hood | waiting |
| [sase-m6.2](../agents/bbugyi200.athena.sase-m6.2/README.md) | sase-m6 hood | completed |
| [sase-m6.3](bbugyi200.athena.sase-m6.3.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.4](bbugyi200.athena.sase-m6.4.md) (family · 4) | sase-m6 hood | completed 3, failed 1 |
| [sase-m6.5](bbugyi200.athena.sase-m6.5.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.6](bbugyi200.athena.sase-m6.6.md) (family · 2) | sase-m6 hood | failed 2 |
| [sase-m6.6](../agents/bbugyi200.athena.sase-m6.6/README.md) | sase-m6 hood | failed |
| [sase-m6.6.1.1](bbugyi200.athena.sase-m6.6.1.1.md) (family · 5) | sase-m6 hood | completed 3, failed 2 |
| [sase-m6.6.1.2](bbugyi200.athena.sase-m6.6.1.2.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.6.1.3](../agents/bbugyi200.athena.sase-m6.6.1.3/README.md) | sase-m6 hood | completed |
| [sase-m6.6.1.4](../agents/bbugyi200.athena.sase-m6.6.1.4/README.md) | sase-m6 hood | completed |
| [sase-m6.6.1.5](bbugyi200.athena.sase-m6.6.1.5.md) (family · 4) | sase-m6 hood | completed 1, dismissed 2, failed 1 |
| [sase-m6.6.1.6](bbugyi200.athena.sase-m6.6.1.6.md) (family · 2) | sase-m6 hood | completed 1, dismissed 1 |
| [sase-m6.6.1.7](../agents/bbugyi200.athena.sase-m6.6.1.7/README.md) | sase-m6 hood | dismissed |
| [sase-m6.6.1.land](bbugyi200.athena.sase-m6.6.1.land.md) (family · 2) | sase-m6 hood | completed 1, dismissed 1 |
| [sase-m6.8](bbugyi200.athena.sase-m6.8.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.8](../agents/bbugyi200.athena.sase-m6.8/README.md) | sase-m6 hood | waiting |
| [sase-m6.9](../agents/bbugyi200.athena.sase-m6.9/README.md) | sase-m6 hood | active |
| [sase-m6.land](../agents/bbugyi200.athena.sase-m6.land/README.md) | sase-m6 hood | waiting |
