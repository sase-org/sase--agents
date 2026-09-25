# Family: sase-11y.10.1.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11y](../users/bbugyi200/machines/athena/hoods/sase-11y/README.md) / sase-11y.10.1.4

Owner: `bbugyi200.athena` · Hood: `sase-11y` · Members: 9 · Bead: [sase-11y.10.1.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11y/sase-11y.10.1.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11y.10.1.4--1 [active]"]
  n1["sase-11y.10.1.4--3 [active]"]
  n0 --> n1
  n2["sase-11y.10.1.4--plan [active]"]
  n0 --> n2
  n3["sase-11y.10.1.4--mon-1 [active]"]
  n0 --> n3
  n4["sase-11y.10.1.4--gate [active]"]
  n0 --> n4
  n5["sase-11y.10.1.4--mon-0 [active]"]
  n0 --> n5
  n6["sase-11y.10.1.4--mon [failed]"]
  n0 --> n6
  n7["sase-11y.10.1.4--code [completed]"]
  n0 --> n7
  n8["sase-11y.10.1.4--2 [active]"]
  n0 --> n8
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-11y.10.1.4--1 | active | muse-spark-1.3-contributor / muse | 2026-09-21T02:03:49.636328+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11y.10.1.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--1/chat.md) |
| <a id="member-3"></a>3 | sase-11y.10.1.4--3 | active | muse-spark-1.3-contributor / muse | 2026-09-21T03:25:17.863488+00:00 | [1](../agents/bbugyi200.athena.sase-11y.10.1.4--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-11y.10.1.4--3/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--3/chat.md) |
| <a id="member-plan"></a>plan | sase-11y.10.1.4--plan | active | opus / claude | 2026-09-21T00:57:59.322416+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11y.10.1.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--plan/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-11y.10.1.4--mon-1 | active | muse-spark-1.3-contributor / muse | 2026-09-21T02:34:37.254780+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--mon-1/chat.md) |
| <a id="member-gate"></a>gate | sase-11y.10.1.4--gate | active | opus / claude | 2026-09-21T01:07:47.670473+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--gate/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-11y.10.1.4--mon-0 | active | muse-spark-1.3-contributor / muse | 2026-09-21T02:11:08.215617+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-11y.10.1.4--mon | failed | muse-spark-1.3-contributor / muse | 2026-09-21T01:44:12.207855+00:00 → 2026-09-21T01:56:39.312393+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--mon/chat.md) |
| <a id="member-code"></a>code | sase-11y.10.1.4--code | completed | muse-spark-1.3-contributor / muse | 2026-09-21T01:11:38.883597+00:00 → 2026-09-21T01:49:00.430230+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--code/chat.md) |
| <a id="member-2"></a>2 | sase-11y.10.1.4--2 | active | muse-spark-1.3-contributor / muse | 2026-09-21T02:21:19.405092+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11y.10.1.4--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.10.1.4--2/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`b27b023`](https://github.com/sase-org/sase/commit/b27b02323719eb6dca1288403b77a700ef9f1a37) | feat(ace): canonicalize the Services tab id with axe as legacy alias | 2026-09-21 02:29:05 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11y.10](bbugyi200.athena.sase-11y.10.md) (family · 3) | ancestor | active 3 |
| [sase-11y.10.1.1](../agents/bbugyi200.athena.sase-11y.10.1.1/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.2](bbugyi200.athena.sase-11y.10.1.2.md) (family · 3) | sase-11y.10.1 hood | active 2, completed 1 |
| [sase-11y.10.1.3](bbugyi200.athena.sase-11y.10.1.3.md) (family · 3) | sase-11y.10.1 hood | active 3 |
| [sase-11y.10.1.3.1.1](../agents/bbugyi200.athena.sase-11y.10.1.3.1.1/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.3.1.2](bbugyi200.athena.sase-11y.10.1.3.1.2.md) (family · 3) | sase-11y.10.1 hood | active 3 |
| [sase-11y.10.1.3.1.3](../agents/bbugyi200.athena.sase-11y.10.1.3.1.3/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.3.1.4](../agents/bbugyi200.athena.sase-11y.10.1.3.1.4/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.3.1.5](../agents/bbugyi200.athena.sase-11y.10.1.3.1.5/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.3.1.land](../agents/bbugyi200.athena.sase-11y.10.1.3.1.land/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.5](../agents/bbugyi200.athena.sase-11y.10.1.5/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.6](../agents/bbugyi200.athena.sase-11y.10.1.6/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.1](../agents/bbugyi200.athena.sase-11y.10.1.7.1/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.2](../agents/bbugyi200.athena.sase-11y.10.1.7.2/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.3](../agents/bbugyi200.athena.sase-11y.10.1.7.3/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.4](../agents/bbugyi200.athena.sase-11y.10.1.7.4/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.5](../agents/bbugyi200.athena.sase-11y.10.1.7.5/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.6](../agents/bbugyi200.athena.sase-11y.10.1.7.6/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.7.land](../agents/bbugyi200.athena.sase-11y.10.1.7.land/README.md) | sase-11y.10.1 hood | active |
| [sase-11y.10.1.land](bbugyi200.athena.sase-11y.10.1.land.md) (family · 3) | sase-11y.10.1 hood | active 3 |
| [sase-11y.1](../agents/bbugyi200.athena.sase-11y.1/README.md) | sase-11y hood | active |
| [sase-11y.11.1](../agents/bbugyi200.athena.sase-11y.11.1/README.md) | sase-11y hood | active |
| [sase-11y.11.2](../agents/bbugyi200.athena.sase-11y.11.2/README.md) | sase-11y hood | active |
| [sase-11y.11.3](../agents/bbugyi200.athena.sase-11y.11.3/README.md) | sase-11y hood | active |
| [sase-11y.11.4](../agents/bbugyi200.athena.sase-11y.11.4/README.md) | sase-11y hood | active |
| [sase-11y.11.5](../agents/bbugyi200.athena.sase-11y.11.5/README.md) | sase-11y hood | active |
| [sase-11y.11.land](../agents/bbugyi200.athena.sase-11y.11.land/README.md) | sase-11y hood | active |
| [sase-11y.2](bbugyi200.athena.sase-11y.2.md) (family · 3) | sase-11y hood | active 3 |
| [sase-11y.2.1.1](../agents/bbugyi200.athena.sase-11y.2.1.1/README.md) | sase-11y hood | active |
| [sase-11y.2.1.2](bbugyi200.athena.sase-11y.2.1.2.md) (family · 5) | sase-11y hood | active 5 |
| [sase-11y.2.1.3](../agents/bbugyi200.athena.sase-11y.2.1.3/README.md) | sase-11y hood | active |
| [sase-11y.2.1.4](../agents/bbugyi200.athena.sase-11y.2.1.4/README.md) | sase-11y hood | active |
| [sase-11y.2.1.5.1](../agents/bbugyi200.athena.sase-11y.2.1.5.1/README.md) | sase-11y hood | active |
| [sase-11y.2.1.5.2](../agents/bbugyi200.athena.sase-11y.2.1.5.2/README.md) | sase-11y hood | active |
| [sase-11y.2.1.5.land](bbugyi200.athena.sase-11y.2.1.5.land.md) (family · 1) | sase-11y hood | active 1 |
| [sase-11y.2.1.land](bbugyi200.athena.sase-11y.2.1.land.md) (family · 3) | sase-11y hood | active 3 |
| [sase-11y.3](bbugyi200.athena.sase-11y.3.md) (family · 7) | sase-11y hood | active 7 |
| [sase-11y.4](bbugyi200.athena.sase-11y.4.md) (family · 3) | sase-11y hood | active 2, completed 1 |
| [sase-11y.5](bbugyi200.athena.sase-11y.5.md) (family · 7) | sase-11y hood | active 5, completed 1, failed 1 |
| [sase-11y.6](bbugyi200.athena.sase-11y.6.md) (family · 3) | sase-11y hood | active 2, completed 1 |
| [sase-11y.7](bbugyi200.athena.sase-11y.7.md) (family · 12) | sase-11y hood | active 3, completed 5, failed 4 |
| [sase-11y.7.f0](../agents/bbugyi200.athena.sase-11y.7.f0/README.md) | sase-11y hood | active |
| [sase-11y.7.f1](bbugyi200.athena.sase-11y.7.f1.md) (family · 2) | sase-11y hood | active 2 |
| [sase-11y.8](../agents/bbugyi200.athena.sase-11y.8/README.md) | sase-11y hood | active |
| [sase-11y.9](../agents/bbugyi200.athena.sase-11y.9/README.md) | sase-11y hood | active |
| [sase-11y.land](bbugyi200.athena.sase-11y.land.md) (family · 3) | sase-11y hood | active 3 |
