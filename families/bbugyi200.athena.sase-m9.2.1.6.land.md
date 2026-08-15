# Family: sase-m9.2.1.6.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-m9](../users/bbugyi200/machines/athena/hoods/sase-m9/README.md) / sase-m9.2.1.6.land

Owner: `bbugyi200.athena` · Hood: `sase-m9` · Members: 6 · Bead: [sase-m9.2.1.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-m9/sase-m9.2.1.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-m9.2.1.6.land--mon [failed]"]
  n1["sase-m9.2.1.6.land--2 [completed]"]
  n0 --> n1
  n2["sase-m9.2.1.6.land--mon-0 [failed]"]
  n0 --> n2
  n3["sase-m9.2.1.6.land--1 [completed]"]
  n0 --> n3
  n4["sase-m9.2.1.6.land--code [completed]"]
  n0 --> n4
  n5["sase-m9.2.1.6.land--plan [dismissed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | sase-m9.2.1.6.land--mon | failed | gpt-5.5 / codex | 2026-08-15T16:58:19.460919+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--mon/chat.md) |
| <a id="member-2"></a>2 | sase-m9.2.1.6.land--2 | completed | gpt-5.5 / codex | 2026-08-15T17:39:36.579633+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m9.2.1.6.land--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--2/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-m9.2.1.6.land--mon-0 | failed | gpt-5.5 / codex | 2026-08-15T17:25:41.950816+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--mon-0/chat.md) |
| <a id="member-1"></a>1 | sase-m9.2.1.6.land--1 | completed | gpt-5.5 / codex | 2026-08-15T17:12:47.735116+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m9.2.1.6.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--1/chat.md) |
| <a id="member-code"></a>code | sase-m9.2.1.6.land--code | completed | gpt-5.5 / codex | 2026-08-15T16:44:11.002679+00:00 | [1](../agents/bbugyi200.athena.sase-m9.2.1.6.land--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--code/chat.md) |
| <a id="member-plan"></a>plan | sase-m9.2.1.6.land--plan | dismissed | gpt-5.6-sol / codex | 2026-08-15T12:31:25.783706 → 2026-08-15T12:58:29.386434 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m9.2.1.6.land--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`4ba7ee8`](https://github.com/sase-org/sase/commit/4ba7ee812573024d48b201d223c7cc075903b3b0) | build(deps): require provider-disable core floor | 2026-08-15 12:56:20 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-m9.2](../agents/bbugyi200.athena.sase-m9.2/README.md) | ancestor | active |
| [sase-m9.2.1.6.1](../agents/bbugyi200.athena.sase-m9.2.1.6.1/README.md) | sase-m9.2.1.6 hood | dismissed |
| [sase-m9.2.1.6.2](../agents/bbugyi200.athena.sase-m9.2.1.6.2/README.md) | sase-m9.2.1.6 hood | dismissed |
| [sase-m9.2.1.6.3](bbugyi200.athena.sase-m9.2.1.6.3.md) (family · 3) | sase-m9.2.1.6 hood | completed 1, dismissed 1, failed 1 |
| [sase-m9.2.1.1](../agents/bbugyi200.athena.sase-m9.2.1.1/README.md) | sase-m9.2.1 hood | dismissed |
| [sase-m9.2.1.2](../agents/bbugyi200.athena.sase-m9.2.1.2/README.md) | sase-m9.2.1 hood | dismissed |
| [sase-m9.2.1.3](../agents/bbugyi200.athena.sase-m9.2.1.3/README.md) | sase-m9.2.1 hood | dismissed |
| [sase-m9.2.1.4](../agents/bbugyi200.athena.sase-m9.2.1.4/README.md) | sase-m9.2.1 hood | dismissed |
| [sase-m9.2.1.5](bbugyi200.athena.sase-m9.2.1.5.md) (family · 3) | sase-m9.2.1 hood | completed 1, dismissed 1, failed 1 |
| [sase-m9.2.1.land](bbugyi200.athena.sase-m9.2.1.land.md) (family · 2) | sase-m9.2.1 hood | dismissed 1, failed 1 |
| [sase-m9.1](bbugyi200.athena.sase-m9.1.md) (family · 2) | sase-m9 hood | failed 2 |
| [sase-m9.1.1.1](../agents/bbugyi200.athena.sase-m9.1.1.1/README.md) | sase-m9 hood | dismissed |
| [sase-m9.1.1.2](../agents/bbugyi200.athena.sase-m9.1.1.2/README.md) | sase-m9 hood | dismissed |
| [sase-m9.1.1.3](../agents/bbugyi200.athena.sase-m9.1.1.3/README.md) | sase-m9 hood | dismissed |
| [sase-m9.1.1.land](bbugyi200.athena.sase-m9.1.1.land.md) (family · 6) | sase-m9 hood | completed 3, dismissed 1, failed 2 |
| [sase-m9.3](bbugyi200.athena.sase-m9.3.md) (family · 2) | sase-m9 hood | failed 2 |
| [sase-m9.3.1.1](bbugyi200.athena.sase-m9.3.1.1.md) (family · 2) | sase-m9 hood | completed 2 |
| [sase-m9.3.1.2](bbugyi200.athena.sase-m9.3.1.2.md) (family · 2) | sase-m9 hood | active 1, dismissed 1 |
| [sase-m9.3.1.3](bbugyi200.athena.sase-m9.3.1.3.md) (family · 2) | sase-m9 hood | completed 2 |
| [sase-m9.3.1.3](../agents/bbugyi200.athena.sase-m9.3.1.3/README.md) | sase-m9 hood | waiting |
| [sase-m9.3.1.4](bbugyi200.athena.sase-m9.3.1.4.md) (family · 2) | sase-m9 hood | active 2 |
| [sase-m9.3.1.4](../agents/bbugyi200.athena.sase-m9.3.1.4/README.md) | sase-m9 hood | waiting |
| [sase-m9.3.1.5](../agents/bbugyi200.athena.sase-m9.3.1.5/README.md) | sase-m9 hood | waiting |
| [sase-m9.3.1.land](../agents/bbugyi200.athena.sase-m9.3.1.land/README.md) | sase-m9 hood | waiting |
| [sase-m9.land](../agents/bbugyi200.athena.sase-m9.land/README.md) | sase-m9 hood | waiting |
