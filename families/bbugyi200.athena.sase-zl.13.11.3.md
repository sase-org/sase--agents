# Family: sase-zl.13.11.3

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-zl](../users/bbugyi200/machines/athena/hoods/sase-zl/README.md) / sase-zl.13.11.3

Owner: `bbugyi200.athena` · Hood: `sase-zl` · Members: 5 · Bead: [sase-zl.13.11.3](https://github.com/sase-org/sase--beads/blob/main/pages/sase-zl/sase-zl.13.11.3.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-zl.13.11.3--2 [active]"]
  n1["sase-zl.13.11.3--mon [active]"]
  n0 --> n1
  n2["sase-zl.13.11.3--mon-0 [active]"]
  n0 --> n2
  n3["sase-zl.13.11.3--plan [active]"]
  n0 --> n3
  n4["sase-zl.13.11.3--1 [active]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-zl.13.11.3--2 | active | sonnet / claude | 2026-09-13T13:30:57.017069+00:00 | [1](../agents/bbugyi200.athena.sase-zl.13.11.3--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-zl.13.11.3--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-zl.13.11.3--2/chat.md) |
| <a id="member-mon"></a>mon | sase-zl.13.11.3--mon | active | grok-4.6 / grok | 2026-09-13T12:59:36.688180+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-zl.13.11.3--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-zl.13.11.3--mon-0 | active | grok-4.6 / grok | 2026-09-13T13:25:51.224290+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-zl.13.11.3--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-zl.13.11.3--plan | active | grok-4.6 / grok | 2026-09-13T12:04:40.258659+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-zl.13.11.3--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-zl.13.11.3--plan/chat.md) |
| <a id="member-1"></a>1 | sase-zl.13.11.3--1 | active | grok-4.6 / grok | 2026-09-13T13:05:08.501646+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-zl.13.11.3--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-zl.13.11.3--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`897147e`](https://github.com/sase-org/sase/commit/897147eac21d7a65d88b3270eda775e5057adcfc) | fix(monitor): fence manual resume against concurrent receiver adoption | 2026-09-13 09:41:46 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-zl.13.11.1](../agents/bbugyi200.athena.sase-zl.13.11.1/README.md) | sase-zl.13.11 hood | active |
| [sase-zl.13.11.2](../agents/bbugyi200.athena.sase-zl.13.11.2/README.md) | sase-zl.13.11 hood | active |
| [sase-zl.13.11.4](../agents/bbugyi200.athena.sase-zl.13.11.4/README.md) | sase-zl.13.11 hood | active |
| [sase-zl.13.11.5](bbugyi200.athena.sase-zl.13.11.5.md) (family · 9) | sase-zl.13.11 hood | active 9 |
| [sase-zl.13.11.6](../agents/bbugyi200.athena.sase-zl.13.11.6/README.md) | sase-zl.13.11 hood | active |
| [sase-zl.13.11.land](bbugyi200.athena.sase-zl.13.11.land.md) (family · 3) | sase-zl.13.11 hood | active 1, failed 2 |
| [sase-zl.13.1](../agents/bbugyi200.athena.sase-zl.13.1/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.10](bbugyi200.athena.sase-zl.13.10.md) (family · 3) | sase-zl.13 hood | active 3 |
| [sase-zl.13.2](../agents/bbugyi200.athena.sase-zl.13.2/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.3](../agents/bbugyi200.athena.sase-zl.13.3/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.4](../agents/bbugyi200.athena.sase-zl.13.4/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.5](bbugyi200.athena.sase-zl.13.5.md) (family · 7) | sase-zl.13 hood | active 7 |
| [sase-zl.13.6](../agents/bbugyi200.athena.sase-zl.13.6/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.7](../agents/bbugyi200.athena.sase-zl.13.7/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.8](../agents/bbugyi200.athena.sase-zl.13.8/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.9](../agents/bbugyi200.athena.sase-zl.13.9/README.md) | sase-zl.13 hood | active |
| [sase-zl.13.land](bbugyi200.athena.sase-zl.13.land.md) (family · 3) | sase-zl.13 hood | active 3 |
| [sase-zl.1](../agents/bbugyi200.athena.sase-zl.1/README.md) | sase-zl hood | active |
| [sase-zl.10](../agents/bbugyi200.athena.sase-zl.10/README.md) | sase-zl hood | active |
| [sase-zl.11](../agents/bbugyi200.athena.sase-zl.11/README.md) | sase-zl hood | active |
| [sase-zl.12](bbugyi200.athena.sase-zl.12.md) (family · 3) | sase-zl hood | active 3 |
| [sase-zl.2](../agents/bbugyi200.athena.sase-zl.2/README.md) | sase-zl hood | active |
| [sase-zl.3](../agents/bbugyi200.athena.sase-zl.3/README.md) | sase-zl hood | active |
| [sase-zl.4](../agents/bbugyi200.athena.sase-zl.4/README.md) | sase-zl hood | active |
| [sase-zl.5](../agents/bbugyi200.athena.sase-zl.5/README.md) | sase-zl hood | active |
| [sase-zl.6](../agents/bbugyi200.athena.sase-zl.6/README.md) | sase-zl hood | active |
| [sase-zl.7](../agents/bbugyi200.athena.sase-zl.7/README.md) | sase-zl hood | active |
| [sase-zl.8](../agents/bbugyi200.athena.sase-zl.8/README.md) | sase-zl hood | active |
| [sase-zl.9](../agents/bbugyi200.athena.sase-zl.9/README.md) | sase-zl hood | active |
| [sase-zl.land](bbugyi200.athena.sase-zl.land.md) (family · 3) | sase-zl hood | active 3 |
