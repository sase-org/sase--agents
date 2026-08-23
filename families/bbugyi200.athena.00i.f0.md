# Family: 00i.f0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [00i](../users/bbugyi200/machines/athena/hoods/00i/README.md) / 00i.f0

Owner: `bbugyi200.athena` · Hood: `00i` · Members: 10

## Lineage

```mermaid
flowchart TD
  n0["00i.f0--3 [completed]"]
  n1["00i.f0--code [completed]"]
  n0 --> n1
  n2["00i.f0--4 [active]"]
  n0 --> n2
  n3["00i.f0--1 [completed]"]
  n0 --> n3
  n4["00i.f0--mon-2 [failed]"]
  n0 --> n4
  n5["00i.f0--2 [completed]"]
  n0 --> n5
  n6["00i.f0--mon-0 [failed]"]
  n0 --> n6
  n7["00i.f0--plan [completed]"]
  n0 --> n7
  n8["00i.f0--mon-1 [failed]"]
  n0 --> n8
  n9["00i.f0--mon [failed]"]
  n0 --> n9
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-3"></a>3 | 00i.f0--3 | completed | sonnet / claude | 2026-08-14T12:01:55.155699+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.00i.f0--3/prompt.md) | [Chat](../agents/bbugyi200.athena.00i.f0--3/chat.md) |
| <a id="member-code"></a>code | 00i.f0--code | completed | sonnet / claude | 2026-08-14T11:29:27.396149+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.00i.f0--code/chat.md) |
| <a id="member-4"></a>4 | 00i.f0--4 | active | sonnet / claude | 2026-08-14T12:10:09.774374+00:00 | [1](../agents/bbugyi200.athena.00i.f0--4/README.md#commits) | [Prompt](../agents/bbugyi200.athena.00i.f0--4/prompt.md) | — |
| <a id="member-1"></a>1 | 00i.f0--1 | completed | sonnet / claude | 2026-08-14T11:53:59.197647+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.00i.f0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.00i.f0--1/chat.md) |
| <a id="member-mon-2"></a>mon-2 | 00i.f0--mon-2 | failed | sonnet / claude | 2026-08-14T12:04:22.165777+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.00i.f0--mon-2/chat.md) |
| <a id="member-2"></a>2 | 00i.f0--2 | completed | sonnet / claude | 2026-08-14T11:55:09.202688+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.00i.f0--2/prompt.md) | [Chat](../agents/bbugyi200.athena.00i.f0--2/chat.md) |
| <a id="member-mon-0"></a>mon-0 | 00i.f0--mon-0 | failed | sonnet / claude | 2026-08-14T11:54:43.579309+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.00i.f0--mon-0/chat.md) |
| <a id="member-plan"></a>plan | 00i.f0--plan | completed | opus / claude | 2026-08-14T11:18:19.662512+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.00i.f0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.00i.f0--plan/chat.md) |
| <a id="member-mon-1"></a>mon-1 | 00i.f0--mon-1 | failed | sonnet / claude | 2026-08-14T11:55:42.938817+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.00i.f0--mon-1/chat.md) |
| <a id="member-mon"></a>mon | 00i.f0--mon | failed | sonnet / claude | 2026-08-14T11:53:16.827871+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.00i.f0--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 4 | sase | [`9df15db`](https://github.com/sase-org/sase/commit/9df15dbe270bcd2e8fa2912e34b61d0d12db3bbf) | fix(llm\_provider): consume pooled model aliases once per real invocation | 2026-08-14 08:11:36 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [00i](../agents/bbugyi200.athena.00i/README.md) | ancestor | completed |
