# Family: sase-14j.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-14j](../users/bbugyi200/machines/athena/hoods/sase-14j/README.md) / sase-14j.4

Owner: `bbugyi200.athena` · Hood: `sase-14j` · Members: 3 · Bead: [sase-14j.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-14j/sase-14j.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-14j.4--plan [active]"]
  n1["sase-14j.4--1 [active]"]
  n0 --> n1
  n2["sase-14j.4--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-14j.4--plan | active | muse-spark-1.3-contributor / muse | 2026-09-20T23:19:19.239458+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-14j.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-14j.4--plan/chat.md) |
| <a id="member-1"></a>1 | sase-14j.4--1 | active | muse-spark-1.3-contributor / muse | 2026-09-21T00:56:43.247071+00:00 | [1](../agents/bbugyi200.athena.sase-14j.4--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-14j.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-14j.4--1/chat.md) |
| <a id="member-mon"></a>mon | sase-14j.4--mon | failed | muse-spark-1.3-contributor / muse | 2026-09-21T00:13:49.531047+00:00 → 2026-09-21T00:56:02.423585+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-14j.4--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`e1ba485`](https://github.com/sase-org/sase/commit/e1ba4851c1011acc8a8825d5570159b14f7926d0) | feat(tui): resolve per-agent bead touches for the metadata panel | 2026-09-20 21:06:00 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-14j.1](../agents/bbugyi200.athena.sase-14j.1/README.md) | sase-14j hood | active |
| [sase-14j.2](../agents/bbugyi200.athena.sase-14j.2/README.md) | sase-14j hood | active |
| [sase-14j.3](bbugyi200.athena.sase-14j.3.md) (family · 3) | sase-14j hood | active 2, failed 1 |
| [sase-14j.5](../agents/bbugyi200.athena.sase-14j.5/README.md) | sase-14j hood | active |
| [sase-14j.6](../agents/bbugyi200.athena.sase-14j.6/README.md) | sase-14j hood | active |
| [sase-14j.land](bbugyi200.athena.sase-14j.land.md) (family · 3) | sase-14j hood | active 1, completed 1, failed 1 |
