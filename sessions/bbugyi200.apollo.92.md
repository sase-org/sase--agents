# Session: 92

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [92](../users/bbugyi200/machines/apollo/hoods/92/README.md) / 92

Owner: `bbugyi200.apollo` · Hood: `92` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["92--code [active]"]
  n1["92--gate [failed]"]
  n0 --> n1
  n2["92--plan [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | 92--code | active | grok-4.6 / grok | 2026-10-18T20:25:21.819138+00:00 | 0 | — | — |
| <a id="member-gate"></a>gate | 92--gate | failed | opus / claude | 2026-10-18T20:24:15.361406+00:00 → 2026-10-18T20:24:32.667646+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.92--gate/chat.md) |
| <a id="member-plan"></a>plan | 92--plan | active | opus / claude | 2026-10-18T20:18:46.629837+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.92--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.92--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`49c9470`](https://github.com/sase-org/sase/commit/49c9470431d6ce6a192ee3b5db2b84ec59eef036) | chore: Add SDD prompt and plan for agents\_list\_command | 2026-06-17 07:11:45 EDT |
| — | sase | [`00dc569`](https://github.com/sase-org/sase/commit/00dc569bba2ce6e1850ebab0bd7de17cda0d664e) | feat(cli)!: rename \`agents status\` to \`agents list\` | 2026-06-17 07:43:09 EDT |
| — | sase | [`fc3fc55`](https://github.com/sase-org/sase/commit/fc3fc552c09b3b78c30fdb0765eaf02ea70af32d) | fix: normalize GitHub sidecar origins to SSH | 2026-07-15 10:28:06 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [92.f1](../agents/bbugyi200.apollo.92.f1/README.md) | descendant | completed |
