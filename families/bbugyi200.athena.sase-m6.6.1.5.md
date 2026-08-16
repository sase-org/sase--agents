# Family: sase-m6.6.1.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-m6](../users/bbugyi200/machines/athena/hoods/sase-m6/README.md) / sase-m6.6.1.5

Owner: `bbugyi200.athena` · Hood: `sase-m6` · Members: 4 · Bead: [sase-m6.6.1.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-m6/sase-m6.6.1.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-m6.6.1.5--1 [dismissed]"]
  n1["sase-m6.6.1.5--mon [failed]"]
  n0 --> n1
  n2["sase-m6.6.1.5--code [completed]"]
  n0 --> n2
  n3["sase-m6.6.1.5--plan [dismissed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-m6.6.1.5--1 | dismissed | grok-4.6 / grok | 2026-08-15T19:30:37.809450 → 2026-08-15T19:42:44.374682 | 0 | — | — |
| <a id="member-mon"></a>mon | sase-m6.6.1.5--mon | failed | grok-4.6 / grok | 2026-08-15T23:15:36.035769+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.5--mon/chat.md) |
| <a id="member-code"></a>code | sase-m6.6.1.5--code | completed | grok-4.6 / grok | 2026-08-15T22:46:39.304597+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.5--code/chat.md) |
| <a id="member-plan"></a>plan | sase-m6.6.1.5--plan | dismissed | gpt-5.6-sol / codex | 2026-08-15T18:42:16.981222 → 2026-08-15T19:15:45.482022 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.5--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`545cb8e`](https://github.com/sase-org/sase/commit/545cb8e7055c61a81773c424a94a73386aa131db) | feat(query): wire the compiled query profile into contracts, host facade, and FilterBar | 2026-08-15 09:08:39 EDT |
| — | sase | [`e4c6460`](https://github.com/sase-org/sase/commit/e4c64607f693552d3101bd1d130c3c76680f6e7f) | test(ace): align flat-pane visual fixtures with query profiles | 2026-08-15 19:38:20 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-m6.6](../agents/bbugyi200.athena.sase-m6.6/README.md) | ancestor | failed |
| [sase-m6.6.1.1](bbugyi200.athena.sase-m6.6.1.1.md) (family · 5) | sase-m6.6.1 hood | completed 3, failed 2 |
| [sase-m6.6.1.2](bbugyi200.athena.sase-m6.6.1.2.md) (family · 2) | sase-m6.6.1 hood | completed 2 |
| [sase-m6.6.1.3](../agents/bbugyi200.athena.sase-m6.6.1.3/README.md) | sase-m6.6.1 hood | completed |
| [sase-m6.6.1.4](../agents/bbugyi200.athena.sase-m6.6.1.4/README.md) | sase-m6.6.1 hood | completed |
| [sase-m6.6.1.6](bbugyi200.athena.sase-m6.6.1.6.md) (family · 2) | sase-m6.6.1 hood | completed 2 |
| [sase-m6.6.1.7](../agents/bbugyi200.athena.sase-m6.6.1.7/README.md) | sase-m6.6.1 hood | completed |
| [sase-m6.6.1.land](bbugyi200.athena.sase-m6.6.1.land.md) (family · 2) | sase-m6.6.1 hood | active 2 |
| [sase-m6.1](../agents/bbugyi200.athena.sase-m6.1/README.md) | sase-m6 hood | completed |
| [sase-m6.10](../agents/bbugyi200.athena.sase-m6.10/README.md) | sase-m6 hood | waiting |
| [sase-m6.2](../agents/bbugyi200.athena.sase-m6.2/README.md) | sase-m6 hood | completed |
| [sase-m6.3](bbugyi200.athena.sase-m6.3.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.4](bbugyi200.athena.sase-m6.4.md) (family · 4) | sase-m6 hood | completed 3, failed 1 |
| [sase-m6.5](bbugyi200.athena.sase-m6.5.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.7](../agents/bbugyi200.athena.sase-m6.7/README.md) | sase-m6 hood | active |
| [sase-m6.8](../agents/bbugyi200.athena.sase-m6.8/README.md) | sase-m6 hood | waiting |
| [sase-m6.9](../agents/bbugyi200.athena.sase-m6.9/README.md) | sase-m6 hood | waiting |
| [sase-m6.land](../agents/bbugyi200.athena.sase-m6.land/README.md) | sase-m6 hood | waiting |
