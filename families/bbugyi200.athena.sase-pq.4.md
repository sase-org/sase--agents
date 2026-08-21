# Family: sase-pq.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-pq](../users/bbugyi200/machines/athena/hoods/sase-pq/README.md) / sase-pq.4

Owner: `bbugyi200.athena` · Hood: `sase-pq` · Members: 3 · Bead: [sase-pq.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-pq/sase-pq.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-pq.4--plan [completed]"]
  n1["sase-pq.4--mon [failed]"]
  n0 --> n1
  n2["sase-pq.4--1 [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-pq.4--plan | completed | grok-4.6 / grok | 2026-08-18T14:16:40.665873+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pq.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pq.4--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-pq.4--mon | failed | grok-4.6 / grok | 2026-08-18T14:54:53.448863+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pq.4--mon/chat.md) |
| <a id="member-1"></a>1 | sase-pq.4--1 | completed | grok-4.6 / grok | 2026-08-18T15:19:20.078612+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pq.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pq.4--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`8786a35`](https://github.com/sase-org/sase/commit/8786a35717f7e9b67641e6234bf495418885b2d9) | feat(tui): show declared gate chips on pane and review modal | 2026-08-18 11:30:05 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-pq.1](../agents/bbugyi200.athena.sase-pq.1/README.md) | sase-pq hood | completed |
| [sase-pq.2](../agents/bbugyi200.athena.sase-pq.2/README.md) | sase-pq hood | completed |
| [sase-pq.3](../agents/bbugyi200.athena.sase-pq.3/README.md) | sase-pq hood | completed |
| [sase-pq.5](../agents/bbugyi200.athena.sase-pq.5/README.md) | sase-pq hood | completed |
| [sase-pq.6](../agents/bbugyi200.athena.sase-pq.6/README.md) | sase-pq hood | completed |
| [sase-pq.7](bbugyi200.athena.sase-pq.7.md) (family · 3) | sase-pq hood | completed 2, failed 1 |
| [sase-pq.land](bbugyi200.athena.sase-pq.land.md) (family · 9) | sase-pq hood | completed 5, failed 4 |
