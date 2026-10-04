# Session: 51

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [51](../users/bbugyi200/machines/apollo/hoods/51/README.md) / 51

Owner: `bbugyi200.apollo` · Hood: `51` · Members: 9

## Lineage

```mermaid
flowchart TD
  n0["51--code [completed]"]
  n1["51--3 [active]"]
  n0 --> n1
  n2["51--mon-1 [failed]"]
  n0 --> n2
  n3["51--mon [failed]"]
  n0 --> n3
  n4["51--mon-0 [failed]"]
  n0 --> n4
  n5["51--plan [completed]"]
  n0 --> n5
  n6["51--1 [completed]"]
  n0 --> n6
  n7["51--2 [completed]"]
  n0 --> n7
  n8["51--gate [failed]"]
  n0 --> n8
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | 51--code | completed | gpt-6-luna / codex | 2026-10-04T14:01:01.817644+00:00 → 2026-10-04T14:56:42.908870+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.51--code/chat.md) |
| <a id="member-3"></a>3 | 51--3 | active | gpt-6-luna / codex | 2026-10-04T16:25:11.450261+00:00 | [1](../agents/bbugyi200.apollo.51--3/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.51--3/prompt.md) | — |
| <a id="member-mon-1"></a>mon-1 | 51--mon-1 | failed | gpt-6-luna / codex | 2026-10-04T16:18:03.356241+00:00 → 2026-10-04T16:25:11.938897+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.51--mon-1/chat.md) |
| <a id="member-mon"></a>mon | 51--mon | failed | gpt-6-luna / codex | 2026-10-04T14:55:30.082831+00:00 → 2026-10-04T15:21:28.219675+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.51--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | 51--mon-0 | failed | gpt-6-luna / codex | 2026-10-04T15:57:06.518390+00:00 → 2026-10-04T16:04:55.474565+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.51--mon-0/chat.md) |
| <a id="member-plan"></a>plan | 51--plan | completed | opus / claude | 2026-10-04T13:49:26.702974+00:00 → 2026-10-04T14:56:42.908870+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.51--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.51--plan/chat.md) |
| <a id="member-1"></a>1 | 51--1 | completed | gpt-6-luna / codex | 2026-10-04T15:21:28.053385+00:00 → 2026-10-04T15:58:03.929809+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.51--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.51--1/chat.md) |
| <a id="member-2"></a>2 | 51--2 | completed | gpt-6-luna / codex | 2026-10-04T16:04:55.330542+00:00 → 2026-10-04T16:18:44.105136+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.51--2/prompt.md) | [Chat](../agents/bbugyi200.apollo.51--2/chat.md) |
| <a id="member-gate"></a>gate | 51--gate | failed | opus / claude | 2026-10-04T14:00:17.450797+00:00 → 2026-10-04T14:00:33.601841+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.51--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`86e9ef0`](https://github.com/sase-org/sase/commit/86e9ef0e706125afdcf0674701e76c70ba124847) | chore: Add SDD prompt and plan for tui\_perf\_memory\_migration | 2026-06-10 09:04:22 EDT |
| — | sase | [`20d1294`](https://github.com/sase-org/sase/commit/20d129453f68a9b6070d1f6464817cfbf9313df9) | chore: migrate tui\_jk\_baseline memory to tui\_perf | 2026-06-10 09:11:41 EDT |
| 3 | sase | [`3d318f2`](https://github.com/sase-org/sase/commit/3d318f2d3923ab8716b5dddafbd3e926a1a034c1) | feat(ace): continue macro argument lists with parenthesis | 2026-10-04 13:07:29 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [51.f1](../agents/bbugyi200.apollo.51.f1/README.md) | descendant | completed |
