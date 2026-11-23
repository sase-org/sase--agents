# Session: sase-ud.13.1.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ud](../users/bbugyi200/machines/athena/hoods/sase-ud/README.md) / sase-ud.13.1.4

Owner: `bbugyi200.athena` · Hood: `sase-ud` · Members: 11 · Bead: [sase-ud.13.1.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ud/sase-ud.13.1.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ud.13.1.4--4 [dismissed]"]
  n1["sase-ud.13.1.4--2 [dismissed]"]
  n0 --> n1
  n2["sase-ud.13.1.4--mon-1 [dismissed]"]
  n0 --> n2
  n3["sase-ud.13.1.4--mon-0 [dismissed]"]
  n0 --> n3
  n4["sase-ud.13.1.4--3 [active]"]
  n0 --> n4
  n5["sase-ud.13.1.4--mon-2 [active]"]
  n0 --> n5
  n6["sase-ud.13.1.4--5 [active]"]
  n0 --> n6
  n7["sase-ud.13.1.4--plan [active]"]
  n0 --> n7
  n8["sase-ud.13.1.4--1 [active]"]
  n0 --> n8
  n9["sase-ud.13.1.4--mon [active]"]
  n0 --> n9
  n10["sase-ud.13.1.4--mon-3 [active]"]
  n0 --> n10
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-4"></a>4 | sase-ud.13.1.4--4 | dismissed | grok-4.6 / grok | 2026-08-28T11:57:44 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--4/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.13.1.4--4/chat.md) |
| <a id="member-2"></a>2 | sase-ud.13.1.4--2 | dismissed | grok-4.6 / grok | 2026-08-28T10:43:05 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.13.1.4--2/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-ud.13.1.4--mon-1 | dismissed | grok-4.6 / grok | 2026-08-28T10:51:32 | 0 | — | — |
| <a id="member-mon-0"></a>mon-0 | sase-ud.13.1.4--mon-0 | dismissed | grok-4.6 / grok | 2026-08-28T10:21:03 | 0 | — | — |
| <a id="member-3"></a>3 | sase-ud.13.1.4--3 | active | grok-4.6 / grok | 2026-08-28T15:30:17.494026+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--3/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.13.1.4--3/chat.md) |
| <a id="member-mon-2"></a>mon-2 | sase-ud.13.1.4--mon-2 | active | grok-4.6 / grok | 2026-08-28T15:39:15.264648+00:00 | 0 | — | — |
| <a id="member-5"></a>5 | sase-ud.13.1.4--5 | active | grok-4.6 / grok | 2026-08-28T16:19:56.715654+00:00 | [1](../agents/bbugyi200.athena.sase-ud.13.1.4--5/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--5/prompt.md) | — |
| <a id="member-plan"></a>plan | sase-ud.13.1.4--plan | active | gpt-5.5 / codex | 2026-08-28T12:57:41.087731+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.13.1.4--plan/chat.md) |
| <a id="member-1"></a>1 | sase-ud.13.1.4--1 | active | grok-4.6 / grok | 2026-08-28T14:02:51.956461+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.13.1.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.13.1.4--1/chat.md) |
| <a id="member-mon"></a>mon | sase-ud.13.1.4--mon | active | gpt-5.5 / codex | 2026-08-28T13:39:59.963685+00:00 | 0 | — | — |
| <a id="member-mon-3"></a>mon-3 | sase-ud.13.1.4--mon-3 | active | grok-4.6 / grok | 2026-08-28T16:04:19.017304+00:00 | 0 | — | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 5 | — | `f24aed1` | feat(ace): collapse the agent-list status colour ladder | 2026-08-28 12:23:56 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ud.13](bbugyi200.athena.sase-ud.13.md) (session · 2) | ancestor | active 2 |
| [sase-ud.13.1.1](../agents/bbugyi200.athena.sase-ud.13.1.1/README.md) | sase-ud.13.1 hood | active |
| [sase-ud.13.1.2](bbugyi200.athena.sase-ud.13.1.2.md) (session · 8) | sase-ud.13.1 hood | active 3, completed 1, dismissed 3, failed 1 |
| [sase-ud.13.1.3](bbugyi200.athena.sase-ud.13.1.3.md) (session · 2) | sase-ud.13.1 hood | dismissed 2 |
| [sase-ud.13.1.3.1.1](bbugyi200.athena.sase-ud.13.1.3.1.1.md) (session · 5) | sase-ud.13.1 hood | active 4, dismissed 1 |
| [sase-ud.13.1.3.1.2](../agents/bbugyi200.athena.sase-ud.13.1.3.1.2/README.md) | sase-ud.13.1 hood | dismissed |
| [sase-ud.13.1.3.1.3](../agents/bbugyi200.athena.sase-ud.13.1.3.1.3/README.md) | sase-ud.13.1 hood | dismissed |
| [sase-ud.13.1.3.1.4](bbugyi200.athena.sase-ud.13.1.3.1.4.md) (session · 21) | sase-ud.13.1 hood | completed 8, dismissed 2, failed 11 |
| [sase-ud.13.1.3.1.4](../agents/bbugyi200.athena.sase-ud.13.1.3.1.4/README.md) | sase-ud.13.1 hood | active |
| [sase-ud.13.1.3.1.5.1](bbugyi200.athena.sase-ud.13.1.3.1.5.1.md) (session · 3) | sase-ud.13.1 hood | active 1, dismissed 2 |
| [sase-ud.13.1.3.1.5.land](../agents/bbugyi200.athena.sase-ud.13.1.3.1.5.land/README.md) | sase-ud.13.1 hood | active |
| [sase-ud.13.1.3.1.land](bbugyi200.athena.sase-ud.13.1.3.1.land.md) (session · 4) | sase-ud.13.1 hood | active 2, dismissed 1, failed 1 |
| [sase-ud.13.1.5](../agents/bbugyi200.athena.sase-ud.13.1.5/README.md) | sase-ud.13.1 hood | active |
| [sase-ud.13.1.land](bbugyi200.athena.sase-ud.13.1.land.md) (session · 3) | sase-ud.13.1 hood | active 1, dismissed 2 |
| [sase-ud.1](../agents/bbugyi200.athena.sase-ud.1/README.md) | sase-ud hood | dismissed |
| [sase-ud.10](bbugyi200.athena.sase-ud.10.md) (session · 2) | sase-ud hood | active 1, completed 1 |
| [sase-ud.11](bbugyi200.athena.sase-ud.11.md) (session · 2) | sase-ud hood | active 1, completed 1 |
| [sase-ud.12](bbugyi200.athena.sase-ud.12.md) (session · 2) | sase-ud hood | active 1, completed 1 |
| [sase-ud.14](../agents/bbugyi200.athena.sase-ud.14/README.md) | sase-ud hood | dismissed |
| [sase-ud.2](bbugyi200.athena.sase-ud.2.md) (session · 6) | sase-ud hood | active 2, completed 1, dismissed 2, failed 1 |
| [sase-ud.3](bbugyi200.athena.sase-ud.3.md) (session · 2) | sase-ud hood | active 1, completed 1 |
| [sase-ud.4](../agents/bbugyi200.athena.sase-ud.4/README.md) | sase-ud hood | active |
| [sase-ud.5](../agents/bbugyi200.athena.sase-ud.5/README.md) | sase-ud hood | active |
| [sase-ud.6](bbugyi200.athena.sase-ud.6.md) (session · 2) | sase-ud hood | active 1, completed 1 |
| [sase-ud.7](bbugyi200.athena.sase-ud.7.md) (session · 4) | sase-ud hood | active 1, completed 1, dismissed 1, failed 1 |
| [sase-ud.8](../agents/bbugyi200.athena.sase-ud.8/README.md) | sase-ud hood | active |
| [sase-ud.9](../agents/bbugyi200.athena.sase-ud.9/README.md) | sase-ud hood | dismissed |
| [sase-ud.land](bbugyi200.athena.sase-ud.land.md) (session · 3) | sase-ud hood | active 1, dismissed 2 |
