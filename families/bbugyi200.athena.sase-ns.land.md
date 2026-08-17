# Family: sase-ns.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ns](../users/bbugyi200/machines/athena/hoods/sase-ns/README.md) / sase-ns.land

Owner: `bbugyi200.athena` · Hood: `sase-ns` · Members: 4 · Bead: [sase-ns](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ns/README.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ns.land--plan [completed]"]
  n1["sase-ns.land--1 [failed]"]
  n0 --> n1
  n2["sase-ns.land--mon-0 [failed]"]
  n0 --> n2
  n3["sase-ns.land--mon [failed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-ns.land--plan | completed | opus / claude | 2026-08-16T23:04:56.088676+00:00 | [2](../agents/bbugyi200.athena.sase-ns.land--plan/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-ns.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ns.land--plan/chat.md) |
| <a id="member-1"></a>1 | sase-ns.land--1 | failed | opus / claude | 2026-08-17T00:01:10.431205+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ns.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ns.land--1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-ns.land--mon-0 | failed | opus / claude | 2026-08-17T01:02:30.433125+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.land--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-ns.land--mon | failed | opus / claude | 2026-08-17T00:00:46.147934+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.land--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| plan | sase | [`644177a`](https://github.com/sase-org/sase/commit/644177a889ce763650ec822d82583ad0a117fa6f) | test(config): mark the config-cache drain sleeps with wait pragmas | 2026-08-16 19:37:10 EDT |
| plan | sase | [`f8b4ebb`](https://github.com/sase-org/sase/commit/f8b4ebb11eddf4ff1e8f09ac4f783cd8cf9707dc) | fix(tui): drop the stale history-word metadata re-export | 2026-08-16 19:47:06 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ns.1](bbugyi200.athena.sase-ns.1.md) (family · 4) | sase-ns hood | completed 3, failed 1 |
| [sase-ns.2](bbugyi200.athena.sase-ns.2.md) (family · 8) | sase-ns hood | completed 5, failed 3 |
| [sase-ns.3](bbugyi200.athena.sase-ns.3.md) (family · 2) | sase-ns hood | completed 2 |
| [sase-ns.4](../agents/bbugyi200.athena.sase-ns.4/README.md) | sase-ns hood | completed |
| [sase-ns.5](../agents/bbugyi200.athena.sase-ns.5/README.md) | sase-ns hood | completed |
| [sase-ns.6.1](bbugyi200.athena.sase-ns.6.1.md) (family · 2) | sase-ns hood | completed 2 |
| [sase-ns.6.2](bbugyi200.athena.sase-ns.6.2.md) (family · 2) | sase-ns hood | completed 2 |
| [sase-ns.6.3](../agents/bbugyi200.athena.sase-ns.6.3/README.md) | sase-ns hood | completed |
| [sase-ns.6.4](../agents/bbugyi200.athena.sase-ns.6.4/README.md) | sase-ns hood | completed |
| [sase-ns.6.5](../agents/bbugyi200.athena.sase-ns.6.5/README.md) | sase-ns hood | completed |
| [sase-ns.6.6.1](../agents/bbugyi200.athena.sase-ns.6.6.1/README.md) | sase-ns hood | completed |
| [sase-ns.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.2/README.md) | sase-ns hood | active |
| [sase-ns.6.6.3](../agents/bbugyi200.athena.sase-ns.6.6.3/README.md) | sase-ns hood | completed |
| [sase-ns.6.6.4](bbugyi200.athena.sase-ns.6.6.4.md) (family · 2) | sase-ns hood | active 2 |
| [sase-ns.6.6.5](../agents/bbugyi200.athena.sase-ns.6.6.5/README.md) | sase-ns hood | active |
| [sase-ns.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.land/README.md) | sase-ns hood | waiting |
| [sase-ns.6.land](bbugyi200.athena.sase-ns.6.land.md) (family · 4) | sase-ns hood | completed 1, failed 3 |
