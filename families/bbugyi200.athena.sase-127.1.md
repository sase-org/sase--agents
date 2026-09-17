# Family: sase-127.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-127](../users/bbugyi200/machines/athena/hoods/sase-127/README.md) / sase-127.1

Owner: `bbugyi200.athena` · Hood: `sase-127` · Members: 3 · Bead: [sase-127.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-127/sase-127.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-127.1--plan [active]"]
  n1["sase-127.1--gate [failed]"]
  n0 --> n1
  n2["sase-127.1--code [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-127.1--plan | active | gpt-5.6-sol / codex | 2026-09-17T20:59:14.711103+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-127.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-127.1--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-127.1--gate | failed | gpt-5.6-sol / codex | 2026-09-17T21:06:48.139559+00:00 → 2026-09-17T21:07:28.504298+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-127.1--gate/chat.md) |
| <a id="member-code"></a>code | sase-127.1--code | active | gpt-5.5 / codex | 2026-09-17T21:07:55.943946+00:00 | 0 | — | — |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-127.2](../agents/bbugyi200.athena.sase-127.2/README.md) | sase-127 hood | active |
| [sase-127.3](../agents/bbugyi200.athena.sase-127.3/README.md) | sase-127 hood | active |
| [sase-127.4](../agents/bbugyi200.athena.sase-127.4/README.md) | sase-127 hood | waiting |
| [sase-127.land](../agents/bbugyi200.athena.sase-127.land/README.md) | sase-127 hood | waiting |
