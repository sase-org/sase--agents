# Session: bj

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [bj](../users/bbugyi200/machines/apollo/hoods/bj/README.md) / bj

Owner: `bbugyi200.apollo` · Hood: `bj` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["bj--gate [completed]"]
  n1["bj--plan [active]"]
  n0 --> n1
  n2["bj--code [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | bj--gate | completed | opus / claude | 2026-10-30T22:56:55.352603+00:00 → 2026-10-30T22:57:25.510578+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.bj--gate/chat.md) |
| <a id="member-plan"></a>plan | bj--plan | active | opus / claude | 2026-10-30T22:48:02.856453+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.bj--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.bj--plan/chat.md) |
| <a id="member-code"></a>code | bj--code | completed | gpt-6-luna / codex | 2026-10-30T22:57:44.653693+00:00 → 2026-10-30T23:06:42.601002+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.bj--code/prompt.md) | [Chat](../agents/bbugyi200.apollo.bj--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`cb733da`](https://github.com/sase-org/sase/commit/cb733dacf3baa2d631ed706c7a1fb07c9b39a560) | feat(tui): compact Plans rows and state indicators | 2026-07-17 08:06:08 EDT |
