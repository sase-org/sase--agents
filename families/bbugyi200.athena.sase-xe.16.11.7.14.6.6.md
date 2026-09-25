# Family: sase-xe.16.11.7.14.6.6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-xe](../users/bbugyi200/machines/athena/hoods/sase-xe/README.md) / sase-xe.16.11.7.14.6.6

Owner: `bbugyi200.athena` · Hood: `sase-xe` · Members: 7 · Bead: [sase-xe.16.11.7.14.6.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-xe/sase-xe.16.11.7.14.6.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-xe.16.11.7.14.6.6--mon-0 [active]"]
  n1["sase-xe.16.11.7.14.6.6--mon [active]"]
  n0 --> n1
  n2["sase-xe.16.11.7.14.6.6--gate [failed]"]
  n0 --> n2
  n3["sase-xe.16.11.7.14.6.6--1 [active]"]
  n0 --> n3
  n4["sase-xe.16.11.7.14.6.6--mon-1 [active]"]
  n0 --> n4
  n5["sase-xe.16.11.7.14.6.6--plan [active]"]
  n0 --> n5
  n6["sase-xe.16.11.7.14.6.6--2 [active]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-xe.16.11.7.14.6.6--mon-0 | active | grok-4.6 / grok | 2026-09-12T02:36:37.963764+00:00 | 0 | — | — |
| <a id="member-mon"></a>mon | sase-xe.16.11.7.14.6.6--mon | active | grok-4.6 / grok | 2026-09-11T18:53:23.340965+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--mon/chat.md) |
| <a id="member-gate"></a>gate | sase-xe.16.11.7.14.6.6--gate | failed | gpt-5.5 / codex | 2026-09-11T13:13:35.596868+00:00 → 2026-09-11T13:13:54.677119+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--gate/chat.md) |
| <a id="member-1"></a>1 | sase-xe.16.11.7.14.6.6--1 | active | grok-4.6 / grok | 2026-09-12T02:29:18.693405+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--1/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-xe.16.11.7.14.6.6--mon-1 | active | grok-4.6 / grok | 2026-09-12T02:37:48.974990+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--mon-1/chat.md) |
| <a id="member-plan"></a>plan | sase-xe.16.11.7.14.6.6--plan | active | grok-4.6 / grok | 2026-09-11T18:25:53.392267+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--plan/chat.md) |
| <a id="member-2"></a>2 | sase-xe.16.11.7.14.6.6--2 | active | grok-4.6 / grok | 2026-09-12T02:41:08.467408+00:00 | [1](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.6--2/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`ae7fde6`](https://github.com/sase-org/sase/commit/ae7fde656f3a39c61560e66f1418780564dee14b) | test(ace): align fleet PNG snapshots with the unified Agents list | 2026-09-11 23:04:16 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-xe.16.11.7.14.6.1](bbugyi200.athena.sase-xe.16.11.7.14.6.1.md) (family · 7) | sase-xe.16.11.7.14.6 hood | active 7 |
| [sase-xe.16.11.7.14.6.2](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.2/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.3](bbugyi200.athena.sase-xe.16.11.7.14.6.3.md) (family · 3) | sase-xe.16.11.7.14.6 hood | active 2, completed 1 |
| [sase-xe.16.11.7.14.6.4](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.4/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.4.f0](bbugyi200.athena.sase-xe.16.11.7.14.6.4.f0.md) (family · 9) | sase-xe.16.11.7.14.6 hood | active 1, completed 4, failed 4 |
| [sase-xe.16.11.7.14.6.5](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.5/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.7.1](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.1/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.7.2](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.2/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.7.3](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.3/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.7.4](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.4/README.md) | sase-xe.16.11.7.14.6 hood | active |
| [sase-xe.16.11.7.14.6.7.5](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.5/README.md) | sase-xe.16.11.7.14.6 hood | waiting |
| [sase-xe.16.11.7.14.6.7.6](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.6/README.md) | sase-xe.16.11.7.14.6 hood | waiting |
| [sase-xe.16.11.7.14.6.7.land](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.land/README.md) | sase-xe.16.11.7.14.6 hood | waiting |
| [sase-xe.16.11.7.14.6.land](../agents/bbugyi200.athena.sase-xe.16.11.7.14.6.land/README.md) | sase-xe.16.11.7.14.6 hood | waiting |
| [sase-xe.16.11.7.14.1](bbugyi200.athena.sase-xe.16.11.7.14.1.md) (family · 3) | sase-xe.16.11.7.14 hood | active 2, completed 1 |
| [sase-xe.16.11.7.14.2](../agents/bbugyi200.athena.sase-xe.16.11.7.14.2/README.md) | sase-xe.16.11.7.14 hood | active |
| [sase-xe.16.11.7.14.3](../agents/bbugyi200.athena.sase-xe.16.11.7.14.3/README.md) | sase-xe.16.11.7.14 hood | active |
| [sase-xe.16.11.7.14.4](../agents/bbugyi200.athena.sase-xe.16.11.7.14.4/README.md) | sase-xe.16.11.7.14 hood | active |
| [sase-xe.16.11.7.14.5](bbugyi200.athena.sase-xe.16.11.7.14.5.md) (family · 4) | sase-xe.16.11.7.14 hood | active 2, completed 1, dismissed 1 |
| [sase-xe.16.11.7.14.land](bbugyi200.athena.sase-xe.16.11.7.14.land.md) (family · 3) | sase-xe.16.11.7.14 hood | active 3 |
| [sase-xe.16.11.7.1](../agents/bbugyi200.athena.sase-xe.16.11.7.1/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.10](../agents/bbugyi200.athena.sase-xe.16.11.7.10/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.11](../agents/bbugyi200.athena.sase-xe.16.11.7.11/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.12](../agents/bbugyi200.athena.sase-xe.16.11.7.12/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.13](../agents/bbugyi200.athena.sase-xe.16.11.7.13/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.2](../agents/bbugyi200.athena.sase-xe.16.11.7.2/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.3](../agents/bbugyi200.athena.sase-xe.16.11.7.3/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.4](../agents/bbugyi200.athena.sase-xe.16.11.7.4/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.5](../agents/bbugyi200.athena.sase-xe.16.11.7.5/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.6](../agents/bbugyi200.athena.sase-xe.16.11.7.6/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.7](../agents/bbugyi200.athena.sase-xe.16.11.7.7/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.8](../agents/bbugyi200.athena.sase-xe.16.11.7.8/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.9](../agents/bbugyi200.athena.sase-xe.16.11.7.9/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.7.land](../agents/bbugyi200.athena.sase-xe.16.11.7.land/README.md) | sase-xe.16.11.7 hood | active |
| [sase-xe.16.11.1](../agents/bbugyi200.athena.sase-xe.16.11.1/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.2](../agents/bbugyi200.athena.sase-xe.16.11.2/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.3](bbugyi200.athena.sase-xe.16.11.3.md) (family · 7) | sase-xe.16.11 hood | active 7 |
| [sase-xe.16.11.4](../agents/bbugyi200.athena.sase-xe.16.11.4/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.5](../agents/bbugyi200.athena.sase-xe.16.11.5/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.6.1](../agents/bbugyi200.athena.sase-xe.16.11.6.1/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.6.2](../agents/bbugyi200.athena.sase-xe.16.11.6.2/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.6.3](../agents/bbugyi200.athena.sase-xe.16.11.6.3/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.6.4](../agents/bbugyi200.athena.sase-xe.16.11.6.4/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.6.5](../agents/bbugyi200.athena.sase-xe.16.11.6.5/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.6.6](../agents/bbugyi200.athena.sase-xe.16.11.6.6/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.6.land](../agents/bbugyi200.athena.sase-xe.16.11.6.land/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.11.land](bbugyi200.athena.sase-xe.16.11.land.md) (family · 3) | sase-xe.16.11 hood | active 3 |
| [sase-xe.16.11.land.w0](../agents/bbugyi200.athena.sase-xe.16.11.land.w0/README.md) | sase-xe.16.11 hood | waiting |
| [sase-xe.16.11.land.w1](../agents/bbugyi200.athena.sase-xe.16.11.land.w1/README.md) | sase-xe.16.11 hood | active |
| [sase-xe.16.1](bbugyi200.athena.sase-xe.16.1.md) (family · 3) | sase-xe.16 hood | active 2, completed 1 |
| [sase-xe.16.10](bbugyi200.athena.sase-xe.16.10.md) (family · 6) | sase-xe.16 hood | active 3, completed 1, dismissed 1, failed 1 |
| [sase-xe.16.2](../agents/bbugyi200.athena.sase-xe.16.2/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.3](../agents/bbugyi200.athena.sase-xe.16.3/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.4](../agents/bbugyi200.athena.sase-xe.16.4/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.5](../agents/bbugyi200.athena.sase-xe.16.5/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.6](bbugyi200.athena.sase-xe.16.6.md) (family · 3) | sase-xe.16 hood | active 2, completed 1 |
| [sase-xe.16.7](../agents/bbugyi200.athena.sase-xe.16.7/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.8](../agents/bbugyi200.athena.sase-xe.16.8/README.md) | sase-xe.16 hood | active |
| [sase-xe.16.8.f0](bbugyi200.athena.sase-xe.16.8.f0.md) (family · 11) | sase-xe.16 hood | active 1, completed 5, failed 5 |
| [sase-xe.16.9](bbugyi200.athena.sase-xe.16.9.md) (family · 3) | sase-xe.16 hood | active 2, completed 1 |
| [sase-xe.16.land](bbugyi200.athena.sase-xe.16.land.md) (family · 5) | sase-xe.16 hood | active 5 |
| [sase-xe.1](../agents/bbugyi200.athena.sase-xe.1/README.md) | sase-xe hood | active |
| [sase-xe.10](bbugyi200.athena.sase-xe.10.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.10](../agents/bbugyi200.athena.sase-xe.10/README.md) | sase-xe hood | waiting |
| [sase-xe.11](bbugyi200.athena.sase-xe.11.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.12](bbugyi200.athena.sase-xe.12.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.13](bbugyi200.athena.sase-xe.13.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.13](../agents/bbugyi200.athena.sase-xe.13/README.md) | sase-xe hood | waiting |
| [sase-xe.14](bbugyi200.athena.sase-xe.14.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.14.f0](bbugyi200.athena.sase-xe.14.f0.md) (family · 5) | sase-xe hood | active 1, completed 1, failed 3 |
| [sase-xe.15](bbugyi200.athena.sase-xe.15.md) (family · 6) | sase-xe hood | active 2, completed 2, failed 2 |
| [sase-xe.15](../agents/bbugyi200.athena.sase-xe.15/README.md) | sase-xe hood | waiting |
| [sase-xe.2](bbugyi200.athena.sase-xe.2.md) (family · 3) | sase-xe hood | active 2, failed 1 |
| [sase-xe.3](../agents/bbugyi200.athena.sase-xe.3/README.md) | sase-xe hood | active |
| [sase-xe.4](bbugyi200.athena.sase-xe.4.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.5](bbugyi200.athena.sase-xe.5.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.5](../agents/bbugyi200.athena.sase-xe.5/README.md) | sase-xe hood | waiting |
| [sase-xe.6](../agents/bbugyi200.athena.sase-xe.6/README.md) | sase-xe hood | active |
| [sase-xe.7](bbugyi200.athena.sase-xe.7.md) (family · 3) | sase-xe hood | active 2, failed 1 |
| [sase-xe.7.f0](../agents/bbugyi200.athena.sase-xe.7.f0/README.md) | sase-xe hood | active |
| [sase-xe.8](bbugyi200.athena.sase-xe.8.md) (family · 3) | sase-xe hood | active 2, completed 1 |
| [sase-xe.8](../agents/bbugyi200.athena.sase-xe.8/README.md) | sase-xe hood | waiting |
| [sase-xe.9](../agents/bbugyi200.athena.sase-xe.9/README.md) | sase-xe hood | active |
| [sase-xe.land](bbugyi200.athena.sase-xe.land.md) (family · 3) | sase-xe hood | active 3 |
| [sase-xe.land](../agents/bbugyi200.athena.sase-xe.land/README.md) | sase-xe hood | waiting |
