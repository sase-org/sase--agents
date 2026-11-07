# Session: y

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [y](../users/bbugyi200/machines/apollo/hoods/y/README.md) / y

Owner: `bbugyi200.apollo` · Hood: `y` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["y--gate [failed]"]
  n1["y--code [completed]"]
  n0 --> n1
  n2["y--plan [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | y--gate | failed | opus / claude | 2026-09-14T13:01:10.472105+00:00 → 2026-09-14T13:01:43.511546+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.y--gate/chat.md) |
| <a id="member-code"></a>code | y--code | completed | sonnet / claude | 2026-09-14T13:01:46.446019+00:00 → 2026-09-14T13:48:36.054480+00:00 | [1](../agents/bbugyi200.apollo.y--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.y--code/prompt.md) | — |
| <a id="member-plan"></a>plan | y--plan | completed | opus / claude | 2026-09-14T12:52:40.424660+00:00 → 2026-09-14T13:01:12.678125+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.y--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.y--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | — | `4add66d` | chore: Add SDD prompt and plan for tui\_title\_version | 2026-07-03 14:43:19 EDT |
| — | — | `9deb012` | feat(ace): show sase version instead of PID in the TUI title | 2026-07-03 15:40:55 EDT |
| — | — | `8b64dd4` | chore: Add SDD prompt and plan for sase\_run\_skill\_prompt\_guidance | 2026-07-06 22:41:10 EDT |
| — | — | `2894fd2` | docs: clarify sase\_run prompt composition | 2026-07-06 22:48:00 EDT |
| code | — | `e2d9d64` | feat(pager): mute workspace root in trail chrome and titles | 2026-09-14 09:46:55 EDT |
