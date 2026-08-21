# Family: 001

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [001](../users/bbugyi200/machines/athena/hoods/001/README.md) / 001

Owner: `bbugyi200.athena` · Hood: `001` · Members: 8

## Lineage

```mermaid
flowchart TD
  n0["001--2 [completed]"]
  n1["001--mon-1 [failed]"]
  n0 --> n1
  n2["001--mon [failed]"]
  n0 --> n2
  n3["001--mon-0 [failed]"]
  n0 --> n3
  n4["001--1 [completed]"]
  n0 --> n4
  n5["001--3 [completed]"]
  n0 --> n5
  n6["001--plan [completed]"]
  n0 --> n6
  n7["001--code [completed]"]
  n0 --> n7
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | 001--2 | completed | sonnet / claude | 2026-08-13T22:02:21.279011+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.001--2/prompt.md) | [Chat](../agents/bbugyi200.athena.001--2/chat.md) |
| <a id="member-mon-1"></a>mon-1 | 001--mon-1 | failed | sonnet / claude | 2026-08-13T22:49:21.608551+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.001--mon-1/chat.md) |
| <a id="member-mon"></a>mon | 001--mon | failed | sonnet / claude | 2026-08-13T21:56:51.789394+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.001--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | 001--mon-0 | failed | sonnet / claude | 2026-08-13T21:58:57.627361+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.001--mon-0/chat.md) |
| <a id="member-1"></a>1 | 001--1 | completed | sonnet / claude | 2026-08-13T21:57:52.997525+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.001--1/prompt.md) | [Chat](../agents/bbugyi200.athena.001--1/chat.md) |
| <a id="member-3"></a>3 | 001--3 | completed | sonnet / claude | 2026-08-13T23:18:23.632525+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.001--3/prompt.md) | [Chat](../agents/bbugyi200.athena.001--3/chat.md) |
| <a id="member-plan"></a>plan | 001--plan | completed | opus / claude | 2026-08-13T21:33:15.913825+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.001--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.001--plan/chat.md) |
| <a id="member-code"></a>code | 001--code | completed | sonnet / claude | 2026-08-13T21:49:36.650051+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.001--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`4375a97`](https://github.com/sase-org/sase/commit/4375a979133848a741f3bbecb5e64329eed5cad4) | chore: Add SDD prompt and plan for prompt\_insert\_ctrl\_g\_prefix | 2026-06-18 12:01:48 UTC |
| — | sase | [`d4dd47d`](https://github.com/sase-org/sase/commit/d4dd47dd5272dc047f2adb3e64dca5030f90b38a) | feat(tui)!: add prompt Ctrl+G insert prefix | 2026-06-18 12:24:42 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [001.f1](bbugyi200.athena.001.f1.md) (family · 2) | descendant | completed 2 |
