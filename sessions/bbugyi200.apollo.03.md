# Session: 03

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [03](../users/bbugyi200/machines/apollo/hoods/03/README.md) / 03

Owner: `bbugyi200.apollo` · Hood: `03` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["03--plan [completed]"]
  n1["03--gate [failed]"]
  n0 --> n1
  n2["03--code [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 03--plan | completed | gpt-6-astra / codex | 2026-09-15T13:44:52.118290+00:00 → 2026-09-15T13:52:33.419431+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.03--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.03--plan/chat.md) |
| <a id="member-gate"></a>gate | 03--gate | failed | gpt-6-astra / codex | 2026-09-15T13:55:40.726881+00:00 → 2026-09-15T13:55:57.450635+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.03--gate/chat.md) |
| <a id="member-code"></a>code | 03--code | completed | gpt-5.5 / codex | 2026-09-15T13:56:02.005107+00:00 → 2026-09-15T15:20:13.202176+00:00 | [1](../agents/bbugyi200.apollo.03--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.03--code/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | — | `c8fedfa` | feat(demos): add ACE prompt history stash demo | 2026-07-06 23:34:42 EDT |
| code | — | `6122ebe` | test(usage): cover refresh admission after limit reset | 2026-09-15 11:17:33 EDT |
