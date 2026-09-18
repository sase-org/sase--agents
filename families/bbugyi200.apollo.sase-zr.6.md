# Family: sase-zr.6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [sase-zr](../users/bbugyi200/machines/apollo/hoods/sase-zr/README.md) / sase-zr.6

Owner: `bbugyi200.apollo` · Hood: `sase-zr` · Members: 6 · Bead: [sase-zr.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-zr/sase-zr.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-zr.6--plan [active]"]
  n1["sase-zr.6--gate [active]"]
  n0 --> n1
  n2["sase-zr.6--mon-0 [active]"]
  n0 --> n2
  n3["sase-zr.6--mon [active]"]
  n0 --> n3
  n4["sase-zr.6--1 [active]"]
  n0 --> n4
  n5["sase-zr.6--2 [active]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-zr.6--plan | active | gpt-5.5 / codex | 2026-09-14T18:19:42.947671+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-zr.6--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-zr.6--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-zr.6--gate | active | gpt-5.5 / codex | 2026-09-14T18:48:27.437736+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-zr.6--gate/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-zr.6--mon-0 | active | sonnet / claude | 2026-09-14T21:36:56.712086+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-zr.6--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-zr.6--mon | active | gpt-5.5 / codex | 2026-09-14T19:35:26.239902+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.sase-zr.6--mon/chat.md) |
| <a id="member-1"></a>1 | sase-zr.6--1 | active | sonnet / claude | 2026-09-14T21:35:45.615247+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.sase-zr.6--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-zr.6--1/chat.md) |
| <a id="member-2"></a>2 | sase-zr.6--2 | active | sonnet / claude | 2026-09-14T23:23:12.737243+00:00 | [1](../agents/bbugyi200.apollo.sase-zr.6--2/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.sase-zr.6--2/prompt.md) | [Chat](../agents/bbugyi200.apollo.sase-zr.6--2/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`7f7700d`](https://github.com/sase-org/sase/commit/7f7700d030c3806b56e326db9567cfa9345cc2f5) | docs(notifications): document gate decision receipts, rollout order, and latency probes | 2026-09-14 19:28:12 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-zr.1](bbugyi200.apollo.sase-zr.1.md) (family · 5) | sase-zr hood | active 5 |
| [sase-zr.1](../agents/bbugyi200.apollo.sase-zr.1/README.md) | sase-zr hood | completed |
| [sase-zr.2](bbugyi200.apollo.sase-zr.2.md) (family · 3) | sase-zr hood | active 3 |
| [sase-zr.2](../agents/bbugyi200.apollo.sase-zr.2/README.md) | sase-zr hood | completed |
| [sase-zr.3](../agents/bbugyi200.apollo.sase-zr.3/README.md) | sase-zr hood | active |
| [sase-zr.4](../agents/bbugyi200.apollo.sase-zr.4/README.md) | sase-zr hood | active |
| [sase-zr.5](bbugyi200.apollo.sase-zr.5.md) (family · 3) | sase-zr hood | active 1, failed 2 |
| [sase-zr.7.1](bbugyi200.apollo.sase-zr.7.1.md) (family · 4) | sase-zr hood | active 1, failed 3 |
| [sase-zr.7.1.1.1](../agents/bbugyi200.apollo.sase-zr.7.1.1.1/README.md) | sase-zr hood | completed |
| [sase-zr.7.1.1.2](../agents/bbugyi200.apollo.sase-zr.7.1.1.2/README.md) | sase-zr hood | completed |
| [sase-zr.7.1.1.3](../agents/bbugyi200.apollo.sase-zr.7.1.1.3/README.md) | sase-zr hood | completed |
| [sase-zr.7.1.1.4](../agents/bbugyi200.apollo.sase-zr.7.1.1.4/README.md) | sase-zr hood | completed |
| [sase-zr.7.1.1.5.1](../agents/bbugyi200.apollo.sase-zr.7.1.1.5.1/README.md) | sase-zr hood | active |
| [sase-zr.7.1.1.5.2](../agents/bbugyi200.apollo.sase-zr.7.1.1.5.2/README.md) | sase-zr hood | waiting |
| [sase-zr.7.1.1.5.3](../agents/bbugyi200.apollo.sase-zr.7.1.1.5.3/README.md) | sase-zr hood | waiting |
| [sase-zr.7.1.1.5.land](../agents/bbugyi200.apollo.sase-zr.7.1.1.5.land/README.md) | sase-zr hood | waiting |
| [sase-zr.7.1.1.land](bbugyi200.apollo.sase-zr.7.1.1.land.md) (family · 3) | sase-zr hood | failed 3 |
| [sase-zr.7.2](../agents/bbugyi200.apollo.sase-zr.7.2/README.md) | sase-zr hood | waiting |
| [sase-zr.7.3](../agents/bbugyi200.apollo.sase-zr.7.3/README.md) | sase-zr hood | waiting |
| [sase-zr.7.4](../agents/bbugyi200.apollo.sase-zr.7.4/README.md) | sase-zr hood | completed |
| [sase-zr.7.5](../agents/bbugyi200.apollo.sase-zr.7.5/README.md) | sase-zr hood | waiting |
| [sase-zr.7.land](../agents/bbugyi200.apollo.sase-zr.7.land/README.md) | sase-zr hood | waiting |
| [sase-zr.land](../agents/bbugyi200.apollo.sase-zr.land/README.md) | sase-zr hood | waiting |
