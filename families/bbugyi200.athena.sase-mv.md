# Family: sase-mv

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-mv](../users/bbugyi200/machines/athena/hoods/sase-mv/README.md) / sase-mv

Owner: `bbugyi200.athena` · Hood: `sase-mv` · Members: 6 · Bead: [sase-mv](https://github.com/sase-org/sase--beads/blob/main/pages/sase-mv/README.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-mv--code [completed]"]
  n1["sase-mv--1 [completed]"]
  n0 --> n1
  n2["sase-mv--mon [failed]"]
  n0 --> n2
  n3["sase-mv--plan [completed]"]
  n0 --> n3
  n4["sase-mv--2 [active]"]
  n0 --> n4
  n5["sase-mv--mon-0 [failed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-mv--code | completed | grok-4.6 / grok | 2026-08-17T13:13:17.143527+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mv--code/chat.md) |
| <a id="member-1"></a>1 | sase-mv--1 | completed | grok-4.6 / grok | 2026-08-17T14:06:55.544835+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mv--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-mv--1/chat.md) |
| <a id="member-mon"></a>mon | sase-mv--mon | failed | grok-4.6 / grok | 2026-08-17T13:43:54.432401+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mv--mon/chat.md) |
| <a id="member-plan"></a>plan | sase-mv--plan | completed | opus / claude | 2026-08-17T12:56:43.197113+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mv--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-mv--plan/chat.md) |
| <a id="member-2"></a>2 | sase-mv--2 | active | grok-4.6 / grok | 2026-08-17T15:11:24.848755+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mv--2/prompt.md) | — |
| <a id="member-mon-0"></a>mon-0 | sase-mv--mon-0 | failed | grok-4.6 / grok | 2026-08-17T14:43:42.598021+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mv--mon-0/chat.md) |
