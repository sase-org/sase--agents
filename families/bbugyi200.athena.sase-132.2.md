# Family: sase-132.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-132](../users/bbugyi200/machines/athena/hoods/sase-132/README.md) / sase-132.2

Owner: `bbugyi200.athena` · Hood: `sase-132` · Members: 3 · Bead: [sase-132.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-132/sase-132.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-132.2--plan [active]"]
  n1["sase-132.2--gate [failed]"]
  n0 --> n1
  n2["sase-132.2--code [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-132.2--plan | active | gpt-5.6-sol / codex | 2026-09-18T20:35:56.751023+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-132.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-132.2--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-132.2--gate | failed | gpt-5.6-sol / codex | 2026-09-18T20:42:50.549800+00:00 → 2026-09-18T20:43:34.231707+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-132.2--gate/chat.md) |
| <a id="member-code"></a>code | sase-132.2--code | active | gpt-5.5 / codex | 2026-09-18T20:43:51.752160+00:00 | 0 | — | — |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-132.1](../agents/bbugyi200.athena.sase-132.1/README.md) | sase-132 hood | completed |
| [sase-132.3](bbugyi200.athena.sase-132.3.md) (family · 3) | sase-132 hood | active 2, failed 1 |
| [sase-132.4](../agents/bbugyi200.athena.sase-132.4/README.md) | sase-132 hood | completed |
| [sase-132.5](../agents/bbugyi200.athena.sase-132.5/README.md) | sase-132 hood | completed |
| [sase-132.6](../agents/bbugyi200.athena.sase-132.6/README.md) | sase-132 hood | completed |
| [sase-132.7](../agents/bbugyi200.athena.sase-132.7/README.md) | sase-132 hood | waiting |
| [sase-132.land](../agents/bbugyi200.athena.sase-132.land/README.md) | sase-132 hood | waiting |
