# Family: sase-m9.1.1.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-m9](../users/bbugyi200/machines/athena/hoods/sase-m9/README.md) / sase-m9.1.1.land

Owner: `bbugyi200.athena` · Hood: `sase-m9` · Members: 6 · Bead: [sase-m9.1.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-m9/sase-m9.1.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-m9.1.1.land--mon-0 [failed]"]
  n1["sase-m9.1.1.land--code [completed]"]
  n0 --> n1
  n2["sase-m9.1.1.land--plan [completed]"]
  n0 --> n2
  n3["sase-m9.1.1.land--mon [failed]"]
  n0 --> n3
  n4["sase-m9.1.1.land--2 [completed]"]
  n0 --> n4
  n5["sase-m9.1.1.land--1 [completed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-m9.1.1.land--mon-0 | failed | gpt-5.5 / codex | 2026-08-15T01:48:34.609994+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--mon-0/chat.md) |
| <a id="member-code"></a>code | sase-m9.1.1.land--code | completed | gpt-5.5 / codex | 2026-08-15T01:15:30.170625+00:00 | [1](../agents/bbugyi200.athena.sase-m9.1.1.land--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--code/chat.md) |
| <a id="member-plan"></a>plan | sase-m9.1.1.land--plan | completed | gpt-5.6-sol / codex | 2026-08-15T01:03:31.551326+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m9.1.1.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-m9.1.1.land--mon | failed | gpt-5.5 / codex | 2026-08-15T01:34:58.286216+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--mon/chat.md) |
| <a id="member-2"></a>2 | sase-m9.1.1.land--2 | completed | gpt-5.5 / codex | 2026-08-15T01:59:58.299211+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m9.1.1.land--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--2/chat.md) |
| <a id="member-1"></a>1 | sase-m9.1.1.land--1 | completed | gpt-5.5 / codex | 2026-08-15T01:45:42.466818+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m9.1.1.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m9.1.1.land--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`76356cf`](https://github.com/sase-org/sase/commit/76356cf57d71e7574350f003f15caea0f50d9c0d) | docs: align shell taxonomy wording | 2026-08-14 21:36:53 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-m9.1](bbugyi200.athena.sase-m9.1.md) (family · 2) | ancestor | failed 2 |
| [sase-m9.1.1.1](../agents/bbugyi200.athena.sase-m9.1.1.1/README.md) | sase-m9.1.1 hood | completed |
| [sase-m9.1.1.2](../agents/bbugyi200.athena.sase-m9.1.1.2/README.md) | sase-m9.1.1 hood | completed |
| [sase-m9.1.1.3](../agents/bbugyi200.athena.sase-m9.1.1.3/README.md) | sase-m9.1.1 hood | completed |
| [sase-m9.2](bbugyi200.athena.sase-m9.2.md) (family · 2) | sase-m9 hood | failed 2 |
| [sase-m9.2](../agents/bbugyi200.athena.sase-m9.2/README.md) | sase-m9 hood | active |
| [sase-m9.2.1.1](../agents/bbugyi200.athena.sase-m9.2.1.1/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.2](../agents/bbugyi200.athena.sase-m9.2.1.2/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.3](../agents/bbugyi200.athena.sase-m9.2.1.3/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.4](../agents/bbugyi200.athena.sase-m9.2.1.4/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.5](bbugyi200.athena.sase-m9.2.1.5.md) (family · 3) | sase-m9 hood | completed 2, failed 1 |
| [sase-m9.2.1.6.1](../agents/bbugyi200.athena.sase-m9.2.1.6.1/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.6.2](../agents/bbugyi200.athena.sase-m9.2.1.6.2/README.md) | sase-m9 hood | completed |
| [sase-m9.2.1.6.3](bbugyi200.athena.sase-m9.2.1.6.3.md) (family · 3) | sase-m9 hood | completed 2, failed 1 |
| [sase-m9.2.1.6.land](bbugyi200.athena.sase-m9.2.1.6.land.md) (family · 4) | sase-m9 hood | active 1, completed 2, failed 1 |
| [sase-m9.2.1.land](bbugyi200.athena.sase-m9.2.1.land.md) (family · 2) | sase-m9 hood | failed 2 |
| [sase-m9.3](../agents/bbugyi200.athena.sase-m9.3/README.md) | sase-m9 hood | waiting |
| [sase-m9.land](../agents/bbugyi200.athena.sase-m9.land/README.md) | sase-m9 hood | waiting |
