# Family: sase-ns.6.6.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ns](../users/bbugyi200/machines/athena/hoods/sase-ns/README.md) / sase-ns.6.6.5

Owner: `bbugyi200.athena` · Hood: `sase-ns` · Members: 4 · Bead: [sase-ns.6.6.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ns/sase-ns.6.6.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ns.6.6.5--1 [dismissed]"]
  n1["sase-ns.6.6.5--plan [dismissed]"]
  n0 --> n1
  n2["sase-ns.6.6.5--mon [failed]"]
  n0 --> n2
  n3["sase-ns.6.6.5--code [completed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | sase-ns.6.6.5--1 | dismissed | — | 2026-08-17T05:09:40 | 0 | — | — |
| <a id="member-plan"></a>plan | sase-ns.6.6.5--plan | dismissed | — | 2026-08-17T04:03:50 | 0 | — | — |
| <a id="member-mon"></a>mon | sase-ns.6.6.5--mon | failed | sonnet / claude | 2026-08-17T08:56:18.514507+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.6.5--mon/chat.md) |
| <a id="member-code"></a>code | sase-ns.6.6.5--code | completed | sonnet / claude | 2026-08-17T08:39:28.336849+00:00 | [1](../agents/bbugyi200.athena.sase-ns.6.6.5--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.6.5--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`b6246f1`](https://github.com/sase-org/sase/commit/b6246f1cfb8b1d4d9c2d524efab7c4082ba2ee93) | test: deflake headless epic approval against an in-flight launch | 2026-08-17 04:54:01 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ns.6.6.1](../agents/bbugyi200.athena.sase-ns.6.6.1/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.2/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.3](../agents/bbugyi200.athena.sase-ns.6.6.3/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.4](bbugyi200.athena.sase-ns.6.6.4.md) (family · 4) | sase-ns.6.6 hood | completed 1, dismissed 2, failed 1 |
| [sase-ns.6.6.6.1](bbugyi200.athena.sase-ns.6.6.6.1.md) (family · 4) | sase-ns.6.6 hood | active 1, completed 2, failed 1 |
| [sase-ns.6.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.6.2/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.6.3](bbugyi200.athena.sase-ns.6.6.6.3.md) (family · 2) | sase-ns.6.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.6.6.4](../agents/bbugyi200.athena.sase-ns.6.6.6.4/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.6.5](../agents/bbugyi200.athena.sase-ns.6.6.6.5/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.6.land/README.md) | sase-ns.6.6 hood | active |
| [sase-ns.6.6.land](bbugyi200.athena.sase-ns.6.6.land.md) (family · 4) | sase-ns.6.6 hood | dismissed 2, failed 2 |
| [sase-ns.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.land/README.md) | sase-ns.6.6 hood | completed |
| [sase-ns.6.1](bbugyi200.athena.sase-ns.6.1.md) (family · 2) | sase-ns.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.2](bbugyi200.athena.sase-ns.6.2.md) (family · 2) | sase-ns.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.3](../agents/bbugyi200.athena.sase-ns.6.3/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.4](../agents/bbugyi200.athena.sase-ns.6.4/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.5](../agents/bbugyi200.athena.sase-ns.6.5/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.land](bbugyi200.athena.sase-ns.6.land.md) (family · 4) | sase-ns.6 hood | dismissed 2, failed 2 |
| [sase-ns.6.land](../agents/bbugyi200.athena.sase-ns.6.land/README.md) | sase-ns.6 hood | completed |
| [sase-ns.1](bbugyi200.athena.sase-ns.1.md) (family · 4) | sase-ns hood | completed 2, dismissed 1, failed 1 |
| [sase-ns.2](bbugyi200.athena.sase-ns.2.md) (family · 8) | sase-ns hood | completed 4, dismissed 1, failed 3 |
| [sase-ns.3](bbugyi200.athena.sase-ns.3.md) (family · 2) | sase-ns hood | completed 1, dismissed 1 |
| [sase-ns.4](../agents/bbugyi200.athena.sase-ns.4/README.md) | sase-ns hood | dismissed |
| [sase-ns.5](../agents/bbugyi200.athena.sase-ns.5/README.md) | sase-ns hood | dismissed |
| [sase-ns.land](bbugyi200.athena.sase-ns.land.md) (family · 4) | sase-ns hood | dismissed 1, failed 3 |
| [sase-ns.land](../agents/bbugyi200.athena.sase-ns.land/README.md) | sase-ns hood | completed |
