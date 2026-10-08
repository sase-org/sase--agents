# Session: sase-1hi.10.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [sase-1hi](../users/bbugyi200/machines/apollo/hoods/sase-1hi/README.md) / sase-1hi.10.5

Owner: `bbugyi200.apollo` · Hood: `sase-1hi` · Members: 3 · Bead: [sase-1hi.10.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1hi/sase-1hi.10.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1hi.10.5--plan [completed]"]
  n1["sase-1hi.10.5--1 [completed]"]
  n0 --> n1
  n2["sase-1hi.10.5--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-1hi.10.5--plan | completed | muse-spark-1.3-contributor / muse | 2026-10-08T15:06:07.103595+00:00 → 2026-10-08T15:28:30.377726+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1hi.10.5--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1hi.10.5--plan/chat.md) |
| <a id="member-1"></a>1 | sase-1hi.10.5--1 | completed | muse-spark-1.3-contributor / muse | 2026-10-08T15:30:03.473549+00:00 → 2026-10-08T15:48:08.737939+00:00 | [1](../agents/bbugyi200.apollo.sase-1hi.10.5--1/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.sase-1hi.10.5--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1hi.10.5--1/chat.md) |
| <a id="member-mon"></a>mon | sase-1hi.10.5--mon | failed | muse-spark-1.3-contributor / muse | 2026-10-08T15:27:52.897497+00:00 → 2026-10-08T15:30:03.522015+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-1hi.10.5--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`3346966`](https://github.com/sase-org/sase/commit/334696620dac94a10ed241f4a89c51ae76c57d30) | feat(ace): add Plan Decisions PNG goldens and refresh compact-Verdict group (sase-1hi.10.5) | 2026-10-08 11:44:03 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1hi.10.1](bbugyi200.apollo.sase-1hi.10.1.md) (session · 5) | sase-1hi.10 hood | completed 3, failed 2 |
| [sase-1hi.10.2](bbugyi200.apollo.sase-1hi.10.2.md) (session · 11) | sase-1hi.10 hood | completed 6, failed 5 |
| [sase-1hi.10.3](bbugyi200.apollo.sase-1hi.10.3.md) (session · 3) | sase-1hi.10 hood | completed 2, failed 1 |
| [sase-1hi.10.4](bbugyi200.apollo.sase-1hi.10.4.md) (session · 5) | sase-1hi.10 hood | completed 3, failed 2 |
| [sase-1hi.10.6](bbugyi200.apollo.sase-1hi.10.6.md) (session · 7) | sase-1hi.10 hood | completed 4, failed 3 |
| [sase-1hi.10.7.1](bbugyi200.apollo.sase-1hi.10.7.1.md) (session · 11) | sase-1hi.10 hood | active 1, completed 5, failed 5 |
| [sase-1hi.10.7.2](../agents/bbugyi200.apollo.sase-1hi.10.7.2/README.md) | sase-1hi.10 hood | waiting |
| [sase-1hi.10.7.3](bbugyi200.apollo.sase-1hi.10.7.3.md) (session · 9) | sase-1hi.10 hood | active 1, completed 4, failed 4 |
| [sase-1hi.10.7.4](../agents/bbugyi200.apollo.sase-1hi.10.7.4/README.md) | sase-1hi.10 hood | waiting |
| [sase-1hi.10.7.5](../agents/bbugyi200.apollo.sase-1hi.10.7.5/README.md) | sase-1hi.10 hood | waiting |
| [sase-1hi.10.7.land](../agents/bbugyi200.apollo.sase-1hi.10.7.land/README.md) | sase-1hi.10 hood | waiting |
| [sase-1hi.10.land](bbugyi200.apollo.sase-1hi.10.land.md) (session · 3) | sase-1hi.10 hood | failed 3 |
| [sase-1hi.1](bbugyi200.apollo.sase-1hi.1.md) (session · 3) | sase-1hi hood | failed 3 |
| [sase-1hi.1.1.1](../agents/bbugyi200.apollo.sase-1hi.1.1.1/README.md) | sase-1hi hood | completed |
| [sase-1hi.1.1.2](../agents/bbugyi200.apollo.sase-1hi.1.1.2/README.md) | sase-1hi hood | completed |
| [sase-1hi.1.1.3](../agents/bbugyi200.apollo.sase-1hi.1.1.3/README.md) | sase-1hi hood | completed |
| [sase-1hi.1.1.4](../agents/bbugyi200.apollo.sase-1hi.1.1.4/README.md) | sase-1hi hood | completed |
| [sase-1hi.1.1.land](bbugyi200.apollo.sase-1hi.1.1.land.md) (session · 3) | sase-1hi hood | completed 2, failed 1 |
| [sase-1hi.2](../agents/bbugyi200.apollo.sase-1hi.2/README.md) | sase-1hi hood | completed |
| [sase-1hi.3](bbugyi200.apollo.sase-1hi.3.md) (session · 7) | sase-1hi hood | completed 4, failed 3 |
| [sase-1hi.4](../agents/bbugyi200.apollo.sase-1hi.4/README.md) | sase-1hi hood | completed |
| [sase-1hi.5](../agents/bbugyi200.apollo.sase-1hi.5/README.md) | sase-1hi hood | completed |
| [sase-1hi.6](bbugyi200.apollo.sase-1hi.6.md) (session · 7) | sase-1hi hood | completed 4, failed 3 |
| [sase-1hi.7](bbugyi200.apollo.sase-1hi.7.md) (session · 5) | sase-1hi hood | completed 3, failed 2 |
| [sase-1hi.8](bbugyi200.apollo.sase-1hi.8.md) (session · 3) | sase-1hi hood | completed 2, failed 1 |
| [sase-1hi.9](../agents/bbugyi200.apollo.sase-1hi.9/README.md) | sase-1hi hood | completed |
| [sase-1hi.land](bbugyi200.apollo.sase-1hi.land.md) (session · 3) | sase-1hi hood | failed 3 |
