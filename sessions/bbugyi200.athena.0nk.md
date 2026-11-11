# Session: 0nk

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0nk](../users/bbugyi200/machines/athena/hoods/0nk/README.md) / 0nk

Owner: `bbugyi200.athena` · Hood: `0nk` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0nk--code [completed]"]
  n1["0nk--gate [failed]"]
  n0 --> n1
  n2["0nk--plan [dismissed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | 0nk--code | completed | grok-4.6 / grok | 2026-09-19T02:11:20.922680+00:00 → 2026-09-19T02:58:32.827082+00:00 | [1](../agents/bbugyi200.athena.0nk--code/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0nk--code/prompt.md) | [Chat](../agents/bbugyi200.athena.0nk--code/chat.md) |
| <a id="member-gate"></a>gate | 0nk--gate | failed | gpt-5.6-sol / codex | 2026-09-19T02:07:40.845239+00:00 → 2026-09-19T02:08:43.680331+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0nk--gate/chat.md) |
| <a id="member-plan"></a>plan | 0nk--plan | dismissed | gpt-5.6-sol / codex | 2026-09-18T21:56:37.992026 → 2026-09-18T22:04:55.961001 | 0 | [Prompt](../agents/bbugyi200.athena.0nk--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0nk--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | — | `a733725` | feat(tui): bulk-select tmux workspaces from the Agents chooser | 2026-09-18 22:54:48 EDT |
