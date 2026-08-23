# Family: 0bv

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0bv](../users/bbugyi200/machines/athena/hoods/0bv/README.md) / 0bv

Owner: `bbugyi200.athena` · Hood: `0bv` · Members: 8

## Lineage

```mermaid
flowchart TD
  n0["0bv--plan [completed]"]
  n1["0bv--mon-1 [failed]"]
  n0 --> n1
  n2["0bv--mon-0 [failed]"]
  n0 --> n2
  n3["0bv--1 [completed]"]
  n0 --> n3
  n4["0bv--2 [completed]"]
  n0 --> n4
  n5["0bv--code [completed]"]
  n0 --> n5
  n6["0bv--3 [active]"]
  n0 --> n6
  n7["0bv--mon [failed]"]
  n0 --> n7
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 0bv--plan | completed | opus / claude | 2026-08-23T14:52:50.935263+00:00 → 2026-08-23T15:48:05.639943+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0bv--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0bv--plan/chat.md) |
| <a id="member-mon-1"></a>mon-1 | 0bv--mon-1 | failed | sonnet / claude | 2026-08-23T16:32:30.715078+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0bv--mon-1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | 0bv--mon-0 | failed | sonnet / claude | 2026-08-23T16:07:39.008359+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0bv--mon-0/chat.md) |
| <a id="member-1"></a>1 | 0bv--1 | completed | sonnet / claude | 2026-08-23T16:02:30.965184+00:00 → 2026-08-23T16:07:48.181158+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0bv--1/prompt.md) | [Chat](../agents/bbugyi200.athena.0bv--1/chat.md) |
| <a id="member-2"></a>2 | 0bv--2 | completed | sonnet / claude | 2026-08-23T16:23:25.751459+00:00 → 2026-08-23T16:32:44.322811+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0bv--2/prompt.md) | [Chat](../agents/bbugyi200.athena.0bv--2/chat.md) |
| <a id="member-code"></a>code | 0bv--code | completed | sonnet / claude | 2026-08-23T15:06:44.056780+00:00 → 2026-08-23T15:48:05.639943+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0bv--code/chat.md) |
| <a id="member-3"></a>3 | 0bv--3 | active | sonnet / claude | 2026-08-23T16:33:12.254542+00:00 | [1](../agents/bbugyi200.athena.0bv--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0bv--3/prompt.md) | — |
| <a id="member-mon"></a>mon | 0bv--mon | failed | sonnet / claude | 2026-08-23T15:47:55.408699+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0bv--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`22ece6b`](https://github.com/sase-org/sase/commit/22ece6b7c1bcc19301b01339e643d88ca647d3cb) | feat(test-cost): commit per-cause cpu\_limit budgets with provenance | 2026-08-23 12:34:31 EDT |
