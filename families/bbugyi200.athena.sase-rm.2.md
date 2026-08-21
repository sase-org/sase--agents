# Family: sase-rm.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-rm](../users/bbugyi200/machines/athena/hoods/sase-rm/README.md) / sase-rm.2

Owner: `bbugyi200.athena` · Hood: `sase-rm` · Members: 4 · Bead: [sase-rm.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-rm/sase-rm.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-rm.2--code [completed]"]
  n1["sase-rm.2--1 [failed]"]
  n0 --> n1
  n2["sase-rm.2--mon [failed]"]
  n0 --> n2
  n3["sase-rm.2--plan [completed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-rm.2--code | completed | gpt-5.5 / codex | 2026-08-21T09:08:02.517474+00:00 | [1](../agents/bbugyi200.athena.sase-rm.2--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-rm.2--code/chat.md) |
| <a id="member-1"></a>1 | sase-rm.2--1 | failed | grok-4.6 / grok | 2026-08-20T20:47:04.347738+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rm.2--1/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-rm.2--mon | failed | grok-4.6 / grok | 2026-08-20T20:33:08.308664+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-rm.2--mon/chat.md) |
| <a id="member-plan"></a>plan | sase-rm.2--plan | completed | gpt-5.6-sol / codex | 2026-08-21T09:02:39.348094+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rm.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rm.2--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`4a3e691`](https://github.com/sase-org/sase/commit/4a3e691964b6715a8698cce29fd5a16d55d50acc) | feat(completion): add inventory and snippet candidate providers | 2026-08-21 09:48:40 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-rm.1](bbugyi200.athena.sase-rm.1.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.10](bbugyi200.athena.sase-rm.10.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.11](bbugyi200.athena.sase-rm.11.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.12](../agents/bbugyi200.athena.sase-rm.12/README.md) | sase-rm hood | completed |
| [sase-rm.13](bbugyi200.athena.sase-rm.13.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.3](bbugyi200.athena.sase-rm.3.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.4](bbugyi200.athena.sase-rm.4.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.5](bbugyi200.athena.sase-rm.5.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.6](bbugyi200.athena.sase-rm.6.md) (family · 8) | sase-rm hood | active 1, completed 4, failed 3 |
| [sase-rm.6](../agents/bbugyi200.athena.sase-rm.6/README.md) | sase-rm hood | completed |
| [sase-rm.7](../agents/bbugyi200.athena.sase-rm.7/README.md) | sase-rm hood | completed |
| [sase-rm.8](../agents/bbugyi200.athena.sase-rm.8/README.md) | sase-rm hood | completed |
| [sase-rm.9](bbugyi200.athena.sase-rm.9.md) (family · 3) | sase-rm hood | completed 2, failed 1 |
| [sase-rm.land](bbugyi200.athena.sase-rm.land.md) (family · 2) | sase-rm hood | completed 2 |
| [sase-rm.land](../agents/bbugyi200.athena.sase-rm.land/README.md) | sase-rm hood | completed |
