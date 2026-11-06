# Session: 0d

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [0d](../users/bbugyi200/machines/apollo/hoods/0d/README.md) / 0d

Owner: `bbugyi200.apollo` · Hood: `0d` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0d--plan [completed]"]
  n1["0d--code [completed]"]
  n0 --> n1
  n2["0d--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 0d--plan | completed | gpt-6-astra / codex | 2026-09-17T19:05:34.271742+00:00 → 2026-09-17T19:11:51.220510+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.0d--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.0d--plan/chat.md) |
| <a id="member-code"></a>code | 0d--code | completed | gpt-5.5 / codex | 2026-09-17T19:12:36.533413+00:00 → 2026-09-17T20:22:57.100801+00:00 | [1](../agents/bbugyi200.apollo.0d--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.0d--code/prompt.md) | — |
| <a id="member-gate"></a>gate | 0d--gate | failed | gpt-6-astra / codex | 2026-09-17T19:12:18.235296+00:00 → 2026-09-17T19:12:32.470846+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.0d--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | — | `26767ec` | chore: Add SDD prompt and plan for vim\_text\_area\_adoption | 2026-07-05 19:48:52 EDT |
| — | — | `085054e` | feat(tui): adopt vim text areas for modal inputs | 2026-07-05 20:49:46 EDT |
| — | — | `5785c09` | chore: Add SDD prompt and plan for telegram\_project\_display\_names\_1 | 2026-07-07 02:06:33 EDT |
| — | — | `0654041` | feat: humanize safe project filename stems | 2026-07-07 02:19:02 EDT |
| code | — | `d618a42` | test(sudo): cover cwd handoff and runner errors | 2026-09-17 16:19:47 EDT |
