# Family: sase-rs.6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-rs](../users/bbugyi200/machines/athena/hoods/sase-rs/README.md) / sase-rs.6

Owner: `bbugyi200.athena` · Hood: `sase-rs` · Members: 7 · Bead: [sase-rs.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-rs/sase-rs.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-rs.6--2 [completed]"]
  n1["sase-rs.6--3 [active]"]
  n0 --> n1
  n2["sase-rs.6--mon [failed]"]
  n0 --> n2
  n3["sase-rs.6--mon-0 [failed]"]
  n0 --> n3
  n4["sase-rs.6--plan [completed]"]
  n0 --> n4
  n5["sase-rs.6--1 [completed]"]
  n0 --> n5
  n6["sase-rs.6--mon-1 [failed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-rs.6--2 | completed | grok-4.6 / grok | 2026-08-21T19:02:04.778180+00:00 → 2026-08-21T19:09:06.382126+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rs.6--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rs.6--2/chat.md) |
| <a id="member-3"></a>3 | sase-rs.6--3 | active | grok-4.6 / grok | 2026-08-21T19:12:08.200800+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rs.6--3/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-rs.6--mon | failed | grok-4.6 / grok | 2026-08-21T18:39:12.035122+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-rs.6--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-rs.6--mon-0 | failed | grok-4.6 / grok | 2026-08-21T18:46:06.175605+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-rs.6--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-rs.6--plan | completed | grok-4.6 / grok | 2026-08-21T17:59:30.074532+00:00 → 2026-08-21T18:40:11.268962+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rs.6--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rs.6--plan/chat.md) |
| <a id="member-1"></a>1 | sase-rs.6--1 | completed | grok-4.6 / grok | 2026-08-21T18:41:25.094080+00:00 → 2026-08-21T18:46:41.484117+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rs.6--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rs.6--1/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-rs.6--mon-1 | failed | grok-4.6 / grok | 2026-08-21T19:08:35.868255+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-rs.6--mon-1/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-rs.1](../agents/bbugyi200.athena.sase-rs.1/README.md) | sase-rs hood | completed |
| [sase-rs.2](bbugyi200.athena.sase-rs.2.md) (family · 3) | sase-rs hood | completed 2, failed 1 |
| [sase-rs.3](../agents/bbugyi200.athena.sase-rs.3/README.md) | sase-rs hood | completed |
| [sase-rs.4](../agents/bbugyi200.athena.sase-rs.4/README.md) | sase-rs hood | completed |
| [sase-rs.5](../agents/bbugyi200.athena.sase-rs.5/README.md) | sase-rs hood | completed |
| [sase-rs.land](../agents/bbugyi200.athena.sase-rs.land/README.md) | sase-rs hood | waiting |
