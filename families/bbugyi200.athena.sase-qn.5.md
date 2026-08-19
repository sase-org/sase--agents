# Family: sase-qn.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-qn](../users/bbugyi200/machines/athena/hoods/sase-qn/README.md) / sase-qn.5

Owner: `bbugyi200.athena` · Hood: `sase-qn` · Members: 3 · Bead: [sase-qn.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-qn/sase-qn.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-qn.5--plan [completed]"]
  n1["sase-qn.5--mon [failed]"]
  n0 --> n1
  n2["sase-qn.5--1 [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-qn.5--plan | completed | grok-4.6 / grok | 2026-08-19T01:55:17.353969+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-qn.5--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-qn.5--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-qn.5--mon | failed | grok-4.6 / grok | 2026-08-19T02:32:54.891854+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-qn.5--mon/chat.md) |
| <a id="member-1"></a>1 | sase-qn.5--1 | active | grok-4.6 / grok | 2026-08-19T02:49:08.569714+00:00 | [2](../agents/bbugyi200.athena.sase-qn.5--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-qn.5--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`ce5ddf1`](https://github.com/sase-org/sase/commit/ce5ddf13cd8030b385c430da1a5909b07849a3c1) | perf(plugins): enforce catalog-scale budgets and keep lazy latest | 2026-08-18 23:02:02 EDT |
| 1 | sase | [`0e36971`](https://github.com/sase-org/sase/commit/0e36971e0ba2b75ffa9cc09d33ff2a00c6bcce65) | chore(perf): ignore plugin catalog scale floor-check report | 2026-08-18 23:06:15 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-qn.1](../agents/bbugyi200.athena.sase-qn.1/README.md) | sase-qn hood | completed |
| [sase-qn.2](../agents/bbugyi200.athena.sase-qn.2/README.md) | sase-qn hood | completed |
| [sase-qn.3](../agents/bbugyi200.athena.sase-qn.3/README.md) | sase-qn hood | completed |
| [sase-qn.4](../agents/bbugyi200.athena.sase-qn.4/README.md) | sase-qn hood | completed |
| [sase-qn.land](../agents/bbugyi200.athena.sase-qn.land/README.md) | sase-qn hood | waiting |
