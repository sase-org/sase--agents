# Session: sase-1m3.4.1.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [sase-1m3](../users/bbugyi200/machines/apollo/hoods/sase-1m3/README.md) / sase-1m3.4.1.1

Owner: `bbugyi200.apollo` · Hood: `sase-1m3` · Members: 3 · Bead: [sase-1m3.4.1.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1m3/sase-1m3.4.1.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1m3.4.1.1--plan [dismissed]"]
  n1["sase-1m3.4.1.1--1 [dismissed]"]
  n0 --> n1
  n2["sase-1m3.4.1.1--mon [dismissed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-1m3.4.1.1--plan | dismissed | gpt-6-luna / codex | 2026-10-16T22:54:09.650497 → 2026-10-16T23:19:15.102800 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1m3.4.1.1--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1m3.4.1.1--plan/chat.md) |
| <a id="member-1"></a>1 | sase-1m3.4.1.1--1 | dismissed | gpt-6-luna / codex | 2026-10-16T23:23:33.274603 → 2026-10-16T23:36:56.173699 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-1m3.4.1.1--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-1m3.4.1.1--1/chat.md) |
| <a id="member-mon"></a>mon | sase-1m3.4.1.1--mon | dismissed | gpt-6-luna / codex | 2026-10-16T23:18:12.598264 → 2026-10-16T23:22:20.299046 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-1m3.4.1.1--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1m3.4](bbugyi200.apollo.sase-1m3.4.md) (session · 3) | ancestor | failed 3 |
| [sase-1m3.4.1.2](../agents/bbugyi200.apollo.sase-1m3.4.1.2/README.md) | sase-1m3.4.1 hood | dismissed |
| [sase-1m3.4.1.3](../agents/bbugyi200.apollo.sase-1m3.4.1.3/README.md) | sase-1m3.4.1 hood | dismissed |
| [sase-1m3.4.1.4](../agents/bbugyi200.apollo.sase-1m3.4.1.4/README.md) | sase-1m3.4.1 hood | dismissed |
| [sase-1m3.4.1.land](bbugyi200.apollo.sase-1m3.4.1.land.md) (session · 3) | sase-1m3.4.1 hood | completed 1, dismissed 2 |
| [sase-1m3.1](../agents/bbugyi200.apollo.sase-1m3.1/README.md) | sase-1m3 hood | completed |
| [sase-1m3.10](../agents/bbugyi200.apollo.sase-1m3.10/README.md) | sase-1m3 hood | completed |
| [sase-1m3.11](bbugyi200.apollo.sase-1m3.11.md) (session · 15) | sase-1m3 hood | completed 8, failed 7 |
| [sase-1m3.12](bbugyi200.apollo.sase-1m3.12.md) (session · 3) | sase-1m3 hood | completed 2, failed 1 |
| [sase-1m3.2](../agents/bbugyi200.apollo.sase-1m3.2/README.md) | sase-1m3 hood | completed |
| [sase-1m3.3](../agents/bbugyi200.apollo.sase-1m3.3/README.md) | sase-1m3 hood | completed |
| [sase-1m3.5](../agents/bbugyi200.apollo.sase-1m3.5/README.md) | sase-1m3 hood | completed |
| [sase-1m3.6](../agents/bbugyi200.apollo.sase-1m3.6/README.md) | sase-1m3 hood | completed |
| [sase-1m3.7](bbugyi200.apollo.sase-1m3.7.md) (session · 3) | sase-1m3 hood | failed 3 |
| [sase-1m3.7.1.1](../agents/bbugyi200.apollo.sase-1m3.7.1.1/README.md) | sase-1m3 hood | dismissed |
| [sase-1m3.7.1.2](bbugyi200.apollo.sase-1m3.7.1.2.md) (session · 5) | sase-1m3 hood | active 1, completed 2, failed 2 |
| [sase-1m3.7.1.2](../agents/bbugyi200.apollo.sase-1m3.7.1.2/README.md) | sase-1m3 hood | dismissed |
| [sase-1m3.7.1.3](../agents/bbugyi200.apollo.sase-1m3.7.1.3/README.md) | sase-1m3 hood | dismissed |
| [sase-1m3.7.1.4](../agents/bbugyi200.apollo.sase-1m3.7.1.4/README.md) | sase-1m3 hood | dismissed |
| [sase-1m3.7.1.5](bbugyi200.apollo.sase-1m3.7.1.5.md) (session · 13) | sase-1m3 hood | dismissed 13 |
| [sase-1m3.7.1.5](../agents/bbugyi200.apollo.sase-1m3.7.1.5/README.md) | sase-1m3 hood | waiting |
| [sase-1m3.7.1.land](bbugyi200.apollo.sase-1m3.7.1.land.md) (session · 7) | sase-1m3 hood | completed 1, dismissed 5, failed 1 |
| [sase-1m3.8](bbugyi200.apollo.sase-1m3.8.md) (session · 2) | sase-1m3 hood | completed 1, failed 1 |
| [sase-1m3.8](../agents/bbugyi200.apollo.sase-1m3.8/README.md) | sase-1m3 hood | completed |
| [sase-1m3.9](bbugyi200.apollo.sase-1m3.9.md) (session · 3) | sase-1m3 hood | completed 2, failed 1 |
| [sase-1m3.land](bbugyi200.apollo.sase-1m3.land.md) (session · 5) | sase-1m3 hood | active 1, completed 2, failed 2 |
