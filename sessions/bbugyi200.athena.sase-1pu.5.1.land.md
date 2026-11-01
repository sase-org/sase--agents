# Session: sase-1pu.5.1.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-1pu](../users/bbugyi200/machines/athena/hoods/sase-1pu/README.md) / sase-1pu.5.1.land

Owner: `bbugyi200.athena` · Hood: `sase-1pu` · Members: 3 · Bead: [sase-1pu.5.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1pu/sase-1pu.5.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1pu.5.1.land--plan [failed]"]
  n1["sase-1pu.5.1.land--gate [failed]"]
  n0 --> n1
  n2["sase-1pu.5.1.land--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-1pu.5.1.land--plan | failed | gpt-6-astra / codex | 2026-11-01T15:02:50.611928+00:00 → 2026-11-01T15:17:41.173714+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-1pu.5.1.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-1pu.5.1.land--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-1pu.5.1.land--gate | failed | gpt-6-astra / codex | 2026-11-01T15:16:29.096409+00:00 → 2026-11-01T15:17:35.455881+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-1pu.5.1.land--gate/chat.md) |
| <a id="member-mon"></a>mon | sase-1pu.5.1.land--mon | failed | gpt-6-astra / codex | 2026-11-01T15:17:33.849850+00:00 → 2026-11-01T15:20:51.416659+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-1pu.5.1.land--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1pu.5](bbugyi200.athena.sase-1pu.5.md) (session · 3) | ancestor | failed 3 |
| [sase-1pu.5.1.1](bbugyi200.athena.sase-1pu.5.1.1.md) (session · 3) | sase-1pu.5.1 hood | completed 2, failed 1 |
| [sase-1pu.5.1.2](bbugyi200.athena.sase-1pu.5.1.2.md) (session · 5) | sase-1pu.5.1 hood | completed 3, failed 2 |
| [sase-1pu.5.1.3](bbugyi200.athena.sase-1pu.5.1.3.md) (session · 3) | sase-1pu.5.1 hood | completed 2, failed 1 |
| [sase-1pu.5.1.4](bbugyi200.athena.sase-1pu.5.1.4.md) (session · 3) | sase-1pu.5.1 hood | completed 2, failed 1 |
| [sase-1pu.5.1.5.1](../agents/bbugyi200.athena.sase-1pu.5.1.5.1/README.md) | sase-1pu.5.1 hood | completed |
| [sase-1pu.5.1.5.2](../agents/bbugyi200.athena.sase-1pu.5.1.5.2/README.md) | sase-1pu.5.1 hood | completed |
| [sase-1pu.5.1.5.land](../agents/bbugyi200.athena.sase-1pu.5.1.5.land/README.md) | sase-1pu.5.1 hood | waiting |
| [sase-1pu.1](../agents/bbugyi200.athena.sase-1pu.1/README.md) | sase-1pu hood | completed |
| [sase-1pu.2](bbugyi200.athena.sase-1pu.2.md) (session · 5) | sase-1pu hood | completed 3, failed 2 |
| [sase-1pu.3](bbugyi200.athena.sase-1pu.3.md) (session · 3) | sase-1pu hood | completed 2, failed 1 |
| [sase-1pu.4](bbugyi200.athena.sase-1pu.4.md) (session · 5) | sase-1pu hood | completed 3, failed 2 |
| [sase-1pu.land](../agents/bbugyi200.athena.sase-1pu.land/README.md) | sase-1pu hood | waiting |
