# Session: sase-1ou.2.1.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-1ou](../users/bbugyi200/machines/athena/hoods/sase-1ou/README.md) / sase-1ou.2.1.land

Owner: `bbugyi200.athena` · Hood: `sase-1ou` · Members: 3 · Bead: [sase-1ou.2.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ou/sase-1ou.2.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1ou.2.1.land--1 [active]"]
  n1["sase-1ou.2.1.land--plan [active]"]
  n0 --> n1
  n2["sase-1ou.2.1.land--mon [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-1ou.2.1.land--1 | active | gpt-6-astra / codex | 2026-10-27T22:01:54.073043+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-1ou.2.1.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-1ou.2.1.land--1/chat.md) |
| <a id="member-plan"></a>plan | sase-1ou.2.1.land--plan | active | gpt-6-astra / codex | 2026-10-27T21:44:54.103409+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-1ou.2.1.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-1ou.2.1.land--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-1ou.2.1.land--mon | active | gpt-6-astra / codex | 2026-10-27T21:54:53.983073+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-1ou.2.1.land--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1ou.2](bbugyi200.athena.sase-1ou.2.md) (session · 3) | ancestor | failed 3 |
| [sase-1ou.2.1.1](../agents/bbugyi200.athena.sase-1ou.2.1.1/README.md) | sase-1ou.2.1 hood | active |
| [sase-1ou.2.1.2](bbugyi200.athena.sase-1ou.2.1.2.md) (session · 7) | sase-1ou.2.1 hood | active 7 |
| [sase-1ou.1](../agents/bbugyi200.athena.sase-1ou.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.3](bbugyi200.athena.sase-1ou.3.md) (session · 7) | sase-1ou hood | completed 4, failed 3 |
| [sase-1ou.4](bbugyi200.athena.sase-1ou.4.md) (session · 5) | sase-1ou hood | completed 3, failed 2 |
| [sase-1ou.5](bbugyi200.athena.sase-1ou.5.md) (session · 3) | sase-1ou hood | failed 3 |
| [sase-1ou.5.1.1](../agents/bbugyi200.athena.sase-1ou.5.1.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.2](../agents/bbugyi200.athena.sase-1ou.5.1.2/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.3](bbugyi200.athena.sase-1ou.5.1.3.md) (session · 3) | sase-1ou hood | completed 2, failed 1 |
| [sase-1ou.5.1.4](bbugyi200.athena.sase-1ou.5.1.4.md) (session · 5) | sase-1ou hood | completed 3, failed 2 |
| [sase-1ou.5.1.land](../agents/bbugyi200.athena.sase-1ou.5.1.land/README.md) | sase-1ou hood | completed |
| [sase-1ou.6.1](../agents/bbugyi200.athena.sase-1ou.6.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.6.land](bbugyi200.athena.sase-1ou.6.land.md) (session · 7) | sase-1ou hood | active 1, completed 3, failed 3 |
| [sase-1ou.land](bbugyi200.athena.sase-1ou.land.md) (session · 3) | sase-1ou hood | failed 3 |
