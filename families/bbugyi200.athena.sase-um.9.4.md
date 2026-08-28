# Family: sase-um.9.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-um](../users/bbugyi200/machines/athena/hoods/sase-um/README.md) / sase-um.9.4

Owner: `bbugyi200.athena` · Hood: `sase-um` · Members: 5 · Bead: [sase-um.9.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-um/sase-um.9.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-um.9.4--mon-0 [failed]"]
  n1["sase-um.9.4--2 [active]"]
  n0 --> n1
  n2["sase-um.9.4--plan [completed]"]
  n0 --> n2
  n3["sase-um.9.4--1 [completed]"]
  n0 --> n3
  n4["sase-um.9.4--mon [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-um.9.4--mon-0 | failed | grok-4.6 / grok | 2026-08-28T23:39:58.680632+00:00 → 2026-08-28T23:44:42.465438+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-um.9.4--mon-0/chat.md) |
| <a id="member-2"></a>2 | sase-um.9.4--2 | active | grok-4.6 / grok | 2026-08-28T23:45:16.373282+00:00 | [1](../agents/bbugyi200.athena.sase-um.9.4--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-um.9.4--2/prompt.md) | — |
| <a id="member-plan"></a>plan | sase-um.9.4--plan | completed | grok-4.6 / grok | 2026-08-28T21:22:14.837110+00:00 → 2026-08-28T21:46:01.337454+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-um.9.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.9.4--plan/chat.md) |
| <a id="member-1"></a>1 | sase-um.9.4--1 | completed | grok-4.6 / grok | 2026-08-28T23:09:45.894590+00:00 → 2026-08-28T23:40:34.725148+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-um.9.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.9.4--1/chat.md) |
| <a id="member-mon"></a>mon | sase-um.9.4--mon | failed | grok-4.6 / grok | 2026-08-28T21:45:53.315702+00:00 → 2026-08-28T23:09:14.173123+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-um.9.4--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`fa74163`](https://github.com/sase-org/sase/commit/fa74163b5a742fa1cd7e8bfcf98fdd5c0b579da3) | fix(ci): ratchet core pin and wait for models-panel snapshot refresh | 2026-08-28 19:52:06 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-um.9.1](bbugyi200.athena.sase-um.9.1.md) (family · 3) | sase-um.9 hood | completed 2, failed 1 |
| [sase-um.9.2](../agents/bbugyi200.athena.sase-um.9.2/README.md) | sase-um.9 hood | completed |
| [sase-um.9.3](../agents/bbugyi200.athena.sase-um.9.3/README.md) | sase-um.9 hood | completed |
| [sase-um.9.land](../agents/bbugyi200.athena.sase-um.9.land/README.md) | sase-um.9 hood | waiting |
| [sase-um.1](bbugyi200.athena.sase-um.1.md) (family · 2) | sase-um hood | completed 2 |
| [sase-um.2](bbugyi200.athena.sase-um.2.md) (family · 2) | sase-um hood | completed 2 |
| [sase-um.3](../agents/bbugyi200.athena.sase-um.3/README.md) | sase-um hood | completed |
| [sase-um.4](../agents/bbugyi200.athena.sase-um.4/README.md) | sase-um hood | completed |
| [sase-um.5](bbugyi200.athena.sase-um.5.md) (family · 2) | sase-um hood | failed 2 |
| [sase-um.5.1.1](../agents/bbugyi200.athena.sase-um.5.1.1/README.md) | sase-um hood | completed |
| [sase-um.5.1.2](../agents/bbugyi200.athena.sase-um.5.1.2/README.md) | sase-um hood | completed |
| [sase-um.5.1.3](bbugyi200.athena.sase-um.5.1.3.md) (family · 67) | sase-um hood | completed 34, failed 33 |
| [sase-um.5.1.3](../agents/bbugyi200.athena.sase-um.5.1.3/README.md) | sase-um hood | completed |
| [sase-um.5.1.land](bbugyi200.athena.sase-um.5.1.land.md) (family · 7) | sase-um hood | completed 3, failed 3, waiting 1 |
| [sase-um.6](../agents/bbugyi200.athena.sase-um.6/README.md) | sase-um hood | completed |
| [sase-um.7](../agents/bbugyi200.athena.sase-um.7/README.md) | sase-um hood | completed |
| [sase-um.8](../agents/bbugyi200.athena.sase-um.8/README.md) | sase-um hood | completed |
| [sase-um.land](bbugyi200.athena.sase-um.land.md) (family · 3) | sase-um hood | failed 3 |
