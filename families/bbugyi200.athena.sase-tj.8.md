# Family: sase-tj.8

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-tj](../users/bbugyi200/machines/athena/hoods/sase-tj/README.md) / sase-tj.8

Owner: `bbugyi200.athena` · Hood: `sase-tj` · Members: 4 · Bead: [sase-tj.8](https://github.com/sase-org/sase--beads/blob/main/pages/sase-tj/sase-tj.8.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-tj.8--mon [failed]"]
  n1["sase-tj.8--2 [dismissed]"]
  n0 --> n1
  n2["sase-tj.8--1 [active]"]
  n0 --> n2
  n3["sase-tj.8--plan [completed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | sase-tj.8--mon | failed | sonnet / claude | 2026-08-25T14:14:16.681745+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-tj.8--mon/chat.md) |
| <a id="member-2"></a>2 | sase-tj.8--2 | dismissed | — | 2026-08-25T10:31:01 | 0 | — | — |
| <a id="member-1"></a>1 | sase-tj.8--1 | active | sonnet / claude | 2026-08-25T14:16:05.600213+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-tj.8--1/prompt.md) | — |
| <a id="member-plan"></a>plan | sase-tj.8--plan | completed | sonnet / claude | 2026-08-25T13:56:20.843975+00:00 → 2026-08-25T14:14:51.178176+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-tj.8--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-tj.8--plan/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-tj.1](../agents/bbugyi200.athena.sase-tj.1/README.md) | sase-tj hood | completed |
| [sase-tj.10.1](../agents/bbugyi200.athena.sase-tj.10.1/README.md) | sase-tj hood | completed |
| [sase-tj.10.2](../agents/bbugyi200.athena.sase-tj.10.2/README.md) | sase-tj hood | active |
| [sase-tj.10.3](../agents/bbugyi200.athena.sase-tj.10.3/README.md) | sase-tj hood | waiting |
| [sase-tj.10.land](../agents/bbugyi200.athena.sase-tj.10.land/README.md) | sase-tj hood | waiting |
| [sase-tj.2](../agents/bbugyi200.athena.sase-tj.2/README.md) | sase-tj hood | dismissed |
| [sase-tj.3](../agents/bbugyi200.athena.sase-tj.3/README.md) | sase-tj hood | completed |
| [sase-tj.4](../agents/bbugyi200.athena.sase-tj.4/README.md) | sase-tj hood | dismissed |
| [sase-tj.5](bbugyi200.athena.sase-tj.5.md) (family · 3) | sase-tj hood | completed 2, failed 1 |
| [sase-tj.6](../agents/bbugyi200.athena.sase-tj.6/README.md) | sase-tj hood | completed |
| [sase-tj.7](bbugyi200.athena.sase-tj.7.md) (family · 3) | sase-tj hood | dismissed 1, failed 2 |
| [sase-tj.9](../agents/bbugyi200.athena.sase-tj.9/README.md) | sase-tj hood | completed |
| [sase-tj.land](bbugyi200.athena.sase-tj.land.md) (family · 2) | sase-tj hood | failed 2 |
| [sase-tj.land.w0](../agents/bbugyi200.athena.sase-tj.land.w0/README.md) | sase-tj hood | dismissed |
| [sase-tj.land.w1](../agents/bbugyi200.athena.sase-tj.land.w1/README.md) | sase-tj hood | dismissed |
| [sase-tj.land.w3](../agents/bbugyi200.athena.sase-tj.land.w3/README.md) | sase-tj hood | active |
