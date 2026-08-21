# Family: sase-pw.7

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-pw](../users/bbugyi200/machines/athena/hoods/sase-pw/README.md) / sase-pw.7

Owner: `bbugyi200.athena` · Hood: `sase-pw` · Members: 5 · Bead: [sase-pw.7](https://github.com/sase-org/sase--beads/blob/main/pages/sase-pw/sase-pw.7.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-pw.7--mon [failed]"]
  n1["sase-pw.7--2 [completed]"]
  n0 --> n1
  n2["sase-pw.7--1 [completed]"]
  n0 --> n2
  n3["sase-pw.7--mon-0 [failed]"]
  n0 --> n3
  n4["sase-pw.7--plan [completed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | sase-pw.7--mon | failed | grok-4.6 / grok | 2026-08-18T19:16:02.346916+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pw.7--mon/chat.md) |
| <a id="member-2"></a>2 | sase-pw.7--2 | completed | grok-4.6 / grok | 2026-08-18T19:51:09.856542+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.7--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pw.7--2/chat.md) |
| <a id="member-1"></a>1 | sase-pw.7--1 | completed | grok-4.6 / grok | 2026-08-18T19:19:38.821458+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.7--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pw.7--1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-pw.7--mon-0 | failed | grok-4.6 / grok | 2026-08-18T19:25:16.965238+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pw.7--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-pw.7--plan | completed | grok-4.6 / grok | 2026-08-18T18:22:16.130570+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.7--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pw.7--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`831fa6b`](https://github.com/sase-org/sase/commit/831fa6bcbf5bfad84ae88b41c8eddd885ad48490) | feat(ace): seed Agents-tab query from the current project | 2026-08-18 16:02:26 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-pw.1](../agents/bbugyi200.athena.sase-pw.1/README.md) | sase-pw hood | completed |
| [sase-pw.2](../agents/bbugyi200.athena.sase-pw.2/README.md) | sase-pw hood | completed |
| [sase-pw.3](../agents/bbugyi200.athena.sase-pw.3/README.md) | sase-pw hood | completed |
| [sase-pw.4](../agents/bbugyi200.athena.sase-pw.4/README.md) | sase-pw hood | completed |
| [sase-pw.5](bbugyi200.athena.sase-pw.5.md) (family · 7) | sase-pw hood | completed 4, failed 3 |
| [sase-pw.6](../agents/bbugyi200.athena.sase-pw.6/README.md) | sase-pw hood | completed |
| [sase-pw.8](bbugyi200.athena.sase-pw.8.md) (family · 5) | sase-pw hood | completed 3, failed 2 |
| [sase-pw.9](bbugyi200.athena.sase-pw.9.md) (family · 3) | sase-pw hood | completed 2, failed 1 |
| [sase-pw.land](../agents/bbugyi200.athena.sase-pw.land/README.md) | sase-pw hood | completed |
