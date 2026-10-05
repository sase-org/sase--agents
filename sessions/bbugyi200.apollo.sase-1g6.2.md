# Session: sase-1g6.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [sase-1g6](../users/bbugyi200/machines/apollo/hoods/sase-1g6/README.md) / sase-1g6.2

Owner: `bbugyi200.apollo` · Hood: `sase-1g6` · Members: 5 · Bead: [sase-1g6.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1g6/sase-1g6.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1g6.2--2 [completed]"]
  n1["sase-1g6.2--mon-0 [failed]"]
  n0 --> n1
  n2["sase-1g6.2--mon [failed]"]
  n0 --> n2
  n3["sase-1g6.2--plan [completed]"]
  n0 --> n3
  n4["sase-1g6.2--1 [completed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-1g6.2--2 | completed | gpt-6-luna / codex | 2026-10-04T23:30:27.981976+00:00 → 2026-10-04T23:35:44.958997+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1g6.2--2/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1g6.2--2/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-1g6.2--mon-0 | failed | gpt-6-luna / codex | 2026-10-04T23:28:57.281867+00:00 → 2026-10-04T23:30:28.243701+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-1g6.2--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-1g6.2--mon | failed | gpt-6-luna / codex | 2026-10-04T23:15:13.264972+00:00 → 2026-10-04T23:16:19.801404+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-1g6.2--mon/chat.md) |
| <a id="member-plan"></a>plan | sase-1g6.2--plan | completed | gpt-6-luna / codex | 2026-10-04T22:41:17.987866+00:00 → 2026-10-04T23:15:45.871725+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1g6.2--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1g6.2--plan/chat.md) |
| <a id="member-1"></a>1 | sase-1g6.2--1 | completed | gpt-6-luna / codex | 2026-10-04T23:16:19.585669+00:00 → 2026-10-04T23:29:31.301413+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1g6.2--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1g6.2--1/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1g6.1](../agents/bbugyi200.apollo.sase-1g6.1/README.md) | sase-1g6 hood | completed |
| [sase-1g6.3](../agents/bbugyi200.apollo.sase-1g6.3/README.md) | sase-1g6 hood | completed |
| [sase-1g6.4](../agents/bbugyi200.apollo.sase-1g6.4/README.md) | sase-1g6 hood | completed |
| [sase-1g6.land](bbugyi200.apollo.sase-1g6.land.md) (session · 3) | sase-1g6 hood | active 2, failed 1 |
