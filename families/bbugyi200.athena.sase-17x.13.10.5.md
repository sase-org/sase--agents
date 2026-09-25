# Family: sase-17x.13.10.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-17x](../users/bbugyi200/machines/athena/hoods/sase-17x/README.md) / sase-17x.13.10.5

Owner: `bbugyi200.athena` · Hood: `sase-17x` · Members: 3 · Bead: [sase-17x.13.10.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-17x/sase-17x.13.10.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-17x.13.10.5--1 [completed]"]
  n1["sase-17x.13.10.5--mon [failed]"]
  n0 --> n1
  n2["sase-17x.13.10.5--plan [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-17x.13.10.5--1 | completed | muse-spark-1.3-contributor / muse | 2026-09-25T15:35:11.580001+00:00 → 2026-09-25T15:52:18.107623+00:00 | [1](../agents/bbugyi200.athena.sase-17x.13.10.5--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-17x.13.10.5--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17x.13.10.5--1/chat.md) |
| <a id="member-mon"></a>mon | sase-17x.13.10.5--mon | failed | muse-spark-1.3-contributor / muse | 2026-09-25T14:44:56.479189+00:00 → 2026-09-25T15:25:16.056600+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-17x.13.10.5--mon/chat.md) |
| <a id="member-plan"></a>plan | sase-17x.13.10.5--plan | completed | muse-spark-1.3-contributor / muse | 2026-09-25T14:28:56.844413+00:00 → 2026-09-25T14:45:20.137679+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-17x.13.10.5--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17x.13.10.5--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`ea25ee2`](https://github.com/sase-org/sase/commit/ea25ee2bf78796f9850c8164b71ff863b4162d8c) | fix(command-line): move tip marker write off loop, append restored blocks on UI thread (sase-17x.13.10.5) | 2026-09-25 11:47:03 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-17x.13.10.1](bbugyi200.athena.sase-17x.13.10.1.md) (family · 3) | sase-17x.13.10 hood | completed 2, failed 1 |
| [sase-17x.13.10.2](bbugyi200.athena.sase-17x.13.10.2.md) (family · 3) | sase-17x.13.10 hood | completed 2, failed 1 |
| [sase-17x.13.10.3](../agents/bbugyi200.athena.sase-17x.13.10.3/README.md) | sase-17x.13.10 hood | completed |
| [sase-17x.13.10.4](../agents/bbugyi200.athena.sase-17x.13.10.4/README.md) | sase-17x.13.10 hood | active |
| [sase-17x.13.10.6](../agents/bbugyi200.athena.sase-17x.13.10.6/README.md) | sase-17x.13.10 hood | waiting |
| [sase-17x.13.10.land](../agents/bbugyi200.athena.sase-17x.13.10.land/README.md) | sase-17x.13.10 hood | waiting |
| [sase-17x.13.1](../agents/bbugyi200.athena.sase-17x.13.1/README.md) | sase-17x.13 hood | active |
| [sase-17x.13.2](../agents/bbugyi200.athena.sase-17x.13.2/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.3](bbugyi200.athena.sase-17x.13.3.md) (family · 5) | sase-17x.13 hood | completed 3, failed 2 |
| [sase-17x.13.4](../agents/bbugyi200.athena.sase-17x.13.4/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.5](../agents/bbugyi200.athena.sase-17x.13.5/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.6](bbugyi200.athena.sase-17x.13.6.md) (family · 5) | sase-17x.13 hood | completed 3, failed 2 |
| [sase-17x.13.7](../agents/bbugyi200.athena.sase-17x.13.7/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.8](../agents/bbugyi200.athena.sase-17x.13.8/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.9](bbugyi200.athena.sase-17x.13.9.md) (family · 15) | sase-17x.13 hood | completed 8, failed 7 |
| [sase-17x.13.land](bbugyi200.athena.sase-17x.13.land.md) (family · 3) | sase-17x.13 hood | failed 3 |
| [sase-17x.1](../agents/bbugyi200.athena.sase-17x.1/README.md) | sase-17x hood | active |
| [sase-17x.10](bbugyi200.athena.sase-17x.10.md) (family · 3) | sase-17x hood | active 3 |
| [sase-17x.11](../agents/bbugyi200.athena.sase-17x.11/README.md) | sase-17x hood | active |
| [sase-17x.12](../agents/bbugyi200.athena.sase-17x.12/README.md) | sase-17x hood | active |
| [sase-17x.2](../agents/bbugyi200.athena.sase-17x.2/README.md) | sase-17x hood | active |
| [sase-17x.3](../agents/bbugyi200.athena.sase-17x.3/README.md) | sase-17x hood | active |
| [sase-17x.4](../agents/bbugyi200.athena.sase-17x.4/README.md) | sase-17x hood | active |
| [sase-17x.5](bbugyi200.athena.sase-17x.5.md) (family · 3) | sase-17x hood | active 2, completed 1 |
| [sase-17x.6](../agents/bbugyi200.athena.sase-17x.6/README.md) | sase-17x hood | active |
| [sase-17x.7](../agents/bbugyi200.athena.sase-17x.7/README.md) | sase-17x hood | active |
| [sase-17x.8](../agents/bbugyi200.athena.sase-17x.8/README.md) | sase-17x hood | active |
| [sase-17x.9](../agents/bbugyi200.athena.sase-17x.9/README.md) | sase-17x hood | active |
| [sase-17x.land](bbugyi200.athena.sase-17x.land.md) (family · 3) | sase-17x hood | active 3 |
