# Family: sase-um.5.1.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-um](../users/bbugyi200/machines/athena/hoods/sase-um/README.md) / sase-um.5.1.land

Owner: `bbugyi200.athena` · Hood: `sase-um` · Members: 7 · Bead: [sase-um.5.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-um/sase-um.5.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-um.5.1.land--gate [failed]"]
  n1["sase-um.5.1.land--1 [completed]"]
  n0 --> n1
  n2["sase-um.5.1.land--2 [completed]"]
  n0 --> n2
  n3["sase-um.5.1.land--plan [waiting]"]
  n0 --> n3
  n4["sase-um.5.1.land--code [completed]"]
  n0 --> n4
  n5["sase-um.5.1.land--mon-0 [failed]"]
  n0 --> n5
  n6["sase-um.5.1.land--mon [failed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | sase-um.5.1.land--gate | failed | gpt-5.6-sol / codex | 2026-08-28T18:42:23.658809+00:00 → 2026-08-28T18:46:12.895401+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--gate/chat.md) |
| <a id="member-1"></a>1 | sase-um.5.1.land--1 | completed | gpt-5.6-sol / codex | 2026-08-28T18:28:29.448221+00:00 → 2026-08-28T18:33:58.326652+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-um.5.1.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--1/chat.md) |
| <a id="member-2"></a>2 | sase-um.5.1.land--2 | completed | gpt-5.6-sol / codex | 2026-08-28T18:38:37.123266+00:00 → 2026-08-28T18:42:31.403106+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-um.5.1.land--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--2/chat.md) |
| <a id="member-plan"></a>plan | sase-um.5.1.land--plan | waiting | gpt-5.6-sol / codex | 2026-08-28T07:18:18.730435+00:00 → 2026-08-28T07:30:57.687725+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-um.5.1.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--plan/chat.md) |
| <a id="member-code"></a>code | sase-um.5.1.land--code | completed | grok-4.6 / grok | 2026-08-28T18:46:19.273973+00:00 → 2026-08-28T19:02:44.941934+00:00 | [1](../agents/bbugyi200.athena.sase-um.5.1.land--code/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-um.5.1.land--code/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--code/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-um.5.1.land--mon-0 | failed | gpt-5.6-sol / codex | 2026-08-28T18:33:50.562895+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-um.5.1.land--mon | failed | gpt-5.6-sol / codex | 2026-08-28T07:30:50.143684+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-um.5.1.land--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`bcd6813`](https://github.com/sase-org/sase/commit/bcd6813d270aa0da6e48df79410fe7017f5441c9) | fix(history): restore helper-git-cwd chat name fallback | 2026-08-28 15:00:49 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-um.5](bbugyi200.athena.sase-um.5.md) (family · 2) | ancestor | failed 2 |
| [sase-um.5.1.1](../agents/bbugyi200.athena.sase-um.5.1.1/README.md) | sase-um.5.1 hood | completed |
| [sase-um.5.1.2](../agents/bbugyi200.athena.sase-um.5.1.2/README.md) | sase-um.5.1 hood | completed |
| [sase-um.5.1.3](bbugyi200.athena.sase-um.5.1.3.md) (family · 67) | sase-um.5.1 hood | completed 34, failed 33 |
| [sase-um.5.1.3](../agents/bbugyi200.athena.sase-um.5.1.3/README.md) | sase-um.5.1 hood | completed |
| [sase-um.1](bbugyi200.athena.sase-um.1.md) (family · 2) | sase-um hood | completed 2 |
| [sase-um.2](bbugyi200.athena.sase-um.2.md) (family · 2) | sase-um hood | completed 2 |
| [sase-um.3](../agents/bbugyi200.athena.sase-um.3/README.md) | sase-um hood | completed |
| [sase-um.4](../agents/bbugyi200.athena.sase-um.4/README.md) | sase-um hood | completed |
| [sase-um.6](../agents/bbugyi200.athena.sase-um.6/README.md) | sase-um hood | completed |
| [sase-um.7](../agents/bbugyi200.athena.sase-um.7/README.md) | sase-um hood | completed |
| [sase-um.8](../agents/bbugyi200.athena.sase-um.8/README.md) | sase-um hood | completed |
| [sase-um.9.1](bbugyi200.athena.sase-um.9.1.md) (family · 3) | sase-um hood | completed 2, failed 1 |
| [sase-um.9.2](../agents/bbugyi200.athena.sase-um.9.2/README.md) | sase-um hood | completed |
| [sase-um.9.3](../agents/bbugyi200.athena.sase-um.9.3/README.md) | sase-um hood | completed |
| [sase-um.9.4](bbugyi200.athena.sase-um.9.4.md) (family · 5) | sase-um hood | completed 3, failed 2 |
| [sase-um.9.5.1](../agents/bbugyi200.athena.sase-um.9.5.1/README.md) | sase-um hood | completed |
| [sase-um.9.5.2](../agents/bbugyi200.athena.sase-um.9.5.2/README.md) | sase-um hood | active |
| [sase-um.9.5.3](../agents/bbugyi200.athena.sase-um.9.5.3/README.md) | sase-um hood | waiting |
| [sase-um.9.5.4](../agents/bbugyi200.athena.sase-um.9.5.4/README.md) | sase-um hood | waiting |
| [sase-um.9.5.5](../agents/bbugyi200.athena.sase-um.9.5.5/README.md) | sase-um hood | waiting |
| [sase-um.9.5.land](../agents/bbugyi200.athena.sase-um.9.5.land/README.md) | sase-um hood | waiting |
| [sase-um.9.land](bbugyi200.athena.sase-um.9.land.md) (family · 3) | sase-um hood | failed 3 |
| [sase-um.land](bbugyi200.athena.sase-um.land.md) (family · 3) | sase-um hood | failed 3 |
