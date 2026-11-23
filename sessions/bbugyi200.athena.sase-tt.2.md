# Session: sase-tt.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-tt](../users/bbugyi200/machines/athena/hoods/sase-tt/README.md) / sase-tt.2

Owner: `bbugyi200.athena` · Hood: `sase-tt` · Members: 5 · Bead: [sase-tt.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-tt/sase-tt.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-tt.2--1 [dismissed]"]
  n1["sase-tt.2--2 [dismissed]"]
  n0 --> n1
  n2["sase-tt.2--mon-0 [failed]"]
  n0 --> n2
  n3["sase-tt.2--plan [dismissed]"]
  n0 --> n3
  n4["sase-tt.2--mon [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-tt.2--1 | dismissed | sonnet / claude | 2026-08-25T16:14:03 | 0 | [Prompt](../agents/bbugyi200.athena.sase-tt.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-tt.2--1/chat.md) |
| <a id="member-2"></a>2 | sase-tt.2--2 | dismissed | gpt-5.5 / codex | 2026-08-25T16:21:32 | [1](../agents/bbugyi200.athena.sase-tt.2--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-tt.2--2/prompt.md) | — |
| <a id="member-mon-0"></a>mon-0 | sase-tt.2--mon-0 | failed | sonnet / claude | 2026-08-25T20:18:42.905172+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-tt.2--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-tt.2--plan | dismissed | sonnet / claude | 2026-08-25T15:00:31 | 0 | [Prompt](../agents/bbugyi200.athena.sase-tt.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-tt.2--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-tt.2--mon | failed | sonnet / claude | 2026-08-25T20:04:10.206421+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-tt.2--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | — | `fe66394` | perf(agent-names): memoize registry staleness checks | 2026-08-25 16:25:21 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-tt.1](../agents/bbugyi200.athena.sase-tt.1/README.md) | sase-tt hood | dismissed |
| [sase-tt.3](../agents/bbugyi200.athena.sase-tt.3/README.md) | sase-tt hood | dismissed |
| [sase-tt.4](../agents/bbugyi200.athena.sase-tt.4/README.md) | sase-tt hood | dismissed |
| [sase-tt.5](../agents/bbugyi200.athena.sase-tt.5/README.md) | sase-tt hood | dismissed |
| [sase-tt.6](../agents/bbugyi200.athena.sase-tt.6/README.md) | sase-tt hood | dismissed |
| [sase-tt.7](../agents/bbugyi200.athena.sase-tt.7/README.md) | sase-tt hood | dismissed |
| [sase-tt.8](../agents/bbugyi200.athena.sase-tt.8/README.md) | sase-tt hood | dismissed |
| [sase-tt.land](bbugyi200.athena.sase-tt.land.md) (session · 5) | sase-tt hood | dismissed 3, failed 2 |
