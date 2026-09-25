# Family: sase-17m.5.1.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-17m](../users/bbugyi200/machines/athena/hoods/sase-17m/README.md) / sase-17m.5.1.4

Owner: `bbugyi200.athena` · Hood: `sase-17m` · Members: 5 · Bead: [sase-17m.5.1.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-17m/sase-17m.5.1.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-17m.5.1.4--1 [active]"]
  n1["sase-17m.5.1.4--plan [active]"]
  n0 --> n1
  n2["sase-17m.5.1.4--mon-0 [active]"]
  n0 --> n2
  n3["sase-17m.5.1.4--2 [active]"]
  n0 --> n3
  n4["sase-17m.5.1.4--mon [active]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-17m.5.1.4--1 | active | gpt-5.6-terra / codex | 2026-09-25T06:49:05.796408+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-17m.5.1.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17m.5.1.4--1/chat.md) |
| <a id="member-plan"></a>plan | sase-17m.5.1.4--plan | active | gpt-5.6-terra / codex | 2026-09-25T06:35:03.372754+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-17m.5.1.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17m.5.1.4--plan/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-17m.5.1.4--mon-0 | active | gpt-5.6-terra / codex | 2026-09-25T06:54:41.043944+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-17m.5.1.4--mon-0/chat.md) |
| <a id="member-2"></a>2 | sase-17m.5.1.4--2 | active | gpt-5.6-terra / codex | 2026-09-25T07:00:59.811304+00:00 | [1](../agents/bbugyi200.athena.sase-17m.5.1.4--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-17m.5.1.4--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17m.5.1.4--2/chat.md) |
| <a id="member-mon"></a>mon | sase-17m.5.1.4--mon | active | gpt-5.6-terra / codex | 2026-09-25T06:44:37.145031+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-17m.5.1.4--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`b79b9da`](https://github.com/sase-org/sase/commit/b79b9da246b434897fad03229097f76be34a7848) | feat(ace): rename family prompt panels to sessions | 2026-09-25 03:05:30 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-17m.5](bbugyi200.athena.sase-17m.5.md) (family · 3) | ancestor | failed 3 |
| [sase-17m.5.1.1](../agents/bbugyi200.athena.sase-17m.5.1.1/README.md) | sase-17m.5.1 hood | active |
| [sase-17m.5.1.2](../agents/bbugyi200.athena.sase-17m.5.1.2/README.md) | sase-17m.5.1 hood | active |
| [sase-17m.5.1.3](bbugyi200.athena.sase-17m.5.1.3.md) (family · 3) | sase-17m.5.1 hood | active 3 |
| [sase-17m.5.1.5](../agents/bbugyi200.athena.sase-17m.5.1.5/README.md) | sase-17m.5.1 hood | active |
| [sase-17m.5.1.6.1](bbugyi200.athena.sase-17m.5.1.6.1.md) (family · 5) | sase-17m.5.1 hood | completed 3, failed 2 |
| [sase-17m.5.1.6.2](../agents/bbugyi200.athena.sase-17m.5.1.6.2/README.md) | sase-17m.5.1 hood | completed |
| [sase-17m.5.1.6.3](../agents/bbugyi200.athena.sase-17m.5.1.6.3/README.md) | sase-17m.5.1 hood | completed |
| [sase-17m.5.1.6.4](../agents/bbugyi200.athena.sase-17m.5.1.6.4/README.md) | sase-17m.5.1 hood | completed |
| [sase-17m.5.1.6.5.1](bbugyi200.athena.sase-17m.5.1.6.5.1.md) (family · 3) | sase-17m.5.1 hood | completed 2, failed 1 |
| [sase-17m.5.1.6.5.land](../agents/bbugyi200.athena.sase-17m.5.1.6.5.land/README.md) | sase-17m.5.1 hood | active |
| [sase-17m.5.1.6.land](bbugyi200.athena.sase-17m.5.1.6.land.md) (family · 3) | sase-17m.5.1 hood | failed 3 |
| [sase-17m.5.1.land](bbugyi200.athena.sase-17m.5.1.land.md) (family · 3) | sase-17m.5.1 hood | active 3 |
| [sase-17m.1](../agents/bbugyi200.athena.sase-17m.1/README.md) | sase-17m hood | completed |
| [sase-17m.10](../agents/bbugyi200.athena.sase-17m.10/README.md) | sase-17m hood | waiting |
| [sase-17m.2](bbugyi200.athena.sase-17m.2.md) (family · 3) | sase-17m hood | failed 3 |
| [sase-17m.2.1.1](../agents/bbugyi200.athena.sase-17m.2.1.1/README.md) | sase-17m hood | active |
| [sase-17m.2.1.2](../agents/bbugyi200.athena.sase-17m.2.1.2/README.md) | sase-17m hood | active |
| [sase-17m.2.1.3](../agents/bbugyi200.athena.sase-17m.2.1.3/README.md) | sase-17m hood | active |
| [sase-17m.2.1.4](../agents/bbugyi200.athena.sase-17m.2.1.4/README.md) | sase-17m hood | active |
| [sase-17m.2.1.land](../agents/bbugyi200.athena.sase-17m.2.1.land/README.md) | sase-17m hood | active |
| [sase-17m.3](bbugyi200.athena.sase-17m.3.md) (family · 3) | sase-17m hood | failed 3 |
| [sase-17m.3.1.1](../agents/bbugyi200.athena.sase-17m.3.1.1/README.md) | sase-17m hood | active |
| [sase-17m.3.1.2](../agents/bbugyi200.athena.sase-17m.3.1.2/README.md) | sase-17m hood | active |
| [sase-17m.3.1.3](../agents/bbugyi200.athena.sase-17m.3.1.3/README.md) | sase-17m hood | active |
| [sase-17m.3.1.4](../agents/bbugyi200.athena.sase-17m.3.1.4/README.md) | sase-17m hood | active |
| [sase-17m.3.1.5](../agents/bbugyi200.athena.sase-17m.3.1.5/README.md) | sase-17m hood | active |
| [sase-17m.3.1.6](../agents/bbugyi200.athena.sase-17m.3.1.6/README.md) | sase-17m hood | active |
| [sase-17m.3.1.7](../agents/bbugyi200.athena.sase-17m.3.1.7/README.md) | sase-17m hood | active |
| [sase-17m.3.1.land](../agents/bbugyi200.athena.sase-17m.3.1.land/README.md) | sase-17m hood | active |
| [sase-17m.4](bbugyi200.athena.sase-17m.4.md) (family · 3) | sase-17m hood | failed 3 |
| [sase-17m.4.1.1](../agents/bbugyi200.athena.sase-17m.4.1.1/README.md) | sase-17m hood | active |
| [sase-17m.4.1.2](../agents/bbugyi200.athena.sase-17m.4.1.2/README.md) | sase-17m hood | active |
| [sase-17m.4.1.3](../agents/bbugyi200.athena.sase-17m.4.1.3/README.md) | sase-17m hood | active |
| [sase-17m.4.1.4](../agents/bbugyi200.athena.sase-17m.4.1.4/README.md) | sase-17m hood | active |
| [sase-17m.4.1.5](../agents/bbugyi200.athena.sase-17m.4.1.5/README.md) | sase-17m hood | active |
| [sase-17m.4.1.6](../agents/bbugyi200.athena.sase-17m.4.1.6/README.md) | sase-17m hood | active |
| [sase-17m.4.1.7](../agents/bbugyi200.athena.sase-17m.4.1.7/README.md) | sase-17m hood | active |
| [sase-17m.4.1.8](../agents/bbugyi200.athena.sase-17m.4.1.8/README.md) | sase-17m hood | active |
| [sase-17m.4.1.land](../agents/bbugyi200.athena.sase-17m.4.1.land/README.md) | sase-17m hood | active |
| [sase-17m.6](../agents/bbugyi200.athena.sase-17m.6/README.md) | sase-17m hood | completed |
| [sase-17m.7](bbugyi200.athena.sase-17m.7.md) (family · 3) | sase-17m hood | completed 2, failed 1 |
| [sase-17m.8](../agents/bbugyi200.athena.sase-17m.8/README.md) | sase-17m hood | waiting |
| [sase-17m.9](../agents/bbugyi200.athena.sase-17m.9/README.md) | sase-17m hood | waiting |
| [sase-17m.land](../agents/bbugyi200.athena.sase-17m.land/README.md) | sase-17m hood | waiting |
