# Family: sase-s0.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-s0](../users/bbugyi200/machines/athena/hoods/sase-s0/README.md) / sase-s0.land

Owner: `bbugyi200.athena` · Hood: `sase-s0` · Members: 8 · Bead: [sase-s0](https://github.com/sase-org/sase--beads/blob/main/pages/sase-s0/README.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-s0.land--mon-1 [failed]"]
  n1["sase-s0.land--plan [completed]"]
  n0 --> n1
  n2["sase-s0.land--3 [completed]"]
  n0 --> n2
  n3["sase-s0.land--mon-0 [failed]"]
  n0 --> n3
  n4["sase-s0.land--1 [completed]"]
  n0 --> n4
  n5["sase-s0.land--2 [completed]"]
  n0 --> n5
  n6["sase-s0.land--code [completed]"]
  n0 --> n6
  n7["sase-s0.land--mon [failed]"]
  n0 --> n7
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-1"></a>mon-1 | sase-s0.land--mon-1 | failed | grok-4.6 / grok | 2026-08-21T23:18:45.651700+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-s0.land--mon-1/chat.md) |
| <a id="member-plan"></a>plan | sase-s0.land--plan | completed | gpt-5.6-sol / codex | 2026-08-21T22:15:57.459802+00:00 → 2026-08-21T23:03:11.515502+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s0.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s0.land--plan/chat.md) |
| <a id="member-3"></a>3 | sase-s0.land--3 | completed | grok-4.6 / grok | 2026-08-21T23:22:20.286477+00:00 → 2026-08-21T23:40:04.146957+00:00 | [1](../agents/bbugyi200.athena.sase-s0.land--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-s0.land--3/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s0.land--3/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-s0.land--mon-0 | failed | grok-4.6 / grok | 2026-08-21T23:10:03.445807+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-s0.land--mon-0/chat.md) |
| <a id="member-1"></a>1 | sase-s0.land--1 | completed | grok-4.6 / grok | 2026-08-21T23:03:46.227117+00:00 → 2026-08-21T23:10:09.701840+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s0.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s0.land--1/chat.md) |
| <a id="member-2"></a>2 | sase-s0.land--2 | completed | grok-4.6 / grok | 2026-08-21T23:16:06.943297+00:00 → 2026-08-21T23:18:57.716336+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s0.land--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s0.land--2/chat.md) |
| <a id="member-code"></a>code | sase-s0.land--code | completed | grok-4.6 / grok | 2026-08-21T22:26:55.234738+00:00 → 2026-08-21T23:03:11.515502+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-s0.land--code/chat.md) |
| <a id="member-mon"></a>mon | sase-s0.land--mon | failed | grok-4.6 / grok | 2026-08-21T23:02:55.343974+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-s0.land--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`6ee4e1d`](https://github.com/sase-org/sase/commit/6ee4e1d3d26c35d3641de2e267f9297d94b236e1) | test(completion): cover ACE and LSP %final completion parity | 2026-08-21 23:36:51 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-s0.1](../agents/bbugyi200.athena.sase-s0.1/README.md) | sase-s0 hood | completed |
| [sase-s0.2](../agents/bbugyi200.athena.sase-s0.2/README.md) | sase-s0 hood | completed |
| [sase-s0.3](../agents/bbugyi200.athena.sase-s0.3/README.md) | sase-s0 hood | completed |
