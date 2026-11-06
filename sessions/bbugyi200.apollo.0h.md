# Session: 0h

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [0h](../users/bbugyi200/machines/apollo/hoods/0h/README.md) / 0h

Owner: `bbugyi200.apollo` · Hood: `0h` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0h--code [completed]"]
  n1["0h--plan [completed]"]
  n0 --> n1
  n2["0h--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | 0h--code | completed | gpt-5.5 / codex | 2026-09-18T10:58:34.030443+00:00 → 2026-09-18T12:20:46.395172+00:00 | [1](../agents/bbugyi200.apollo.0h--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.0h--code/prompt.md) | — |
| <a id="member-plan"></a>plan | 0h--plan | completed | opus / claude | 2026-09-18T10:39:43.373612+00:00 → 2026-09-18T10:57:49.579143+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.0h--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.0h--plan/chat.md) |
| <a id="member-gate"></a>gate | 0h--gate | failed | opus / claude | 2026-09-18T10:58:13.620504+00:00 → 2026-09-18T10:58:29.175575+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.0h--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | — | `5ed257f` | chore: Add SDD prompt and plan for double\_dash\_agent\_family\_separator | 2026-06-02 21:03:09 EDT |
| — | — | `d71af00` | feat: canonicalize plan-family suffixes with double dash | 2026-06-02 21:26:07 EDT |
| code | — | `7359446` | fix(tui): improve prompt search pill contrast | 2026-09-18 08:18:00 EDT |
