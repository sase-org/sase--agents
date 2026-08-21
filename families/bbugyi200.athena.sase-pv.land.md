# Family: sase-pv.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-pv](../users/bbugyi200/machines/athena/hoods/sase-pv/README.md) / sase-pv.land

Owner: `bbugyi200.athena` · Hood: `sase-pv` · Members: 7 · Bead: [sase-pv](https://github.com/sase-org/sase--beads/blob/main/pages/sase-pv/README.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-pv.land--3 [active]"]
  n1["sase-pv.land--1 [completed]"]
  n0 --> n1
  n2["sase-pv.land--mon-1 [failed]"]
  n0 --> n2
  n3["sase-pv.land--mon-0 [failed]"]
  n0 --> n3
  n4["sase-pv.land--2 [completed]"]
  n0 --> n4
  n5["sase-pv.land--plan [completed]"]
  n0 --> n5
  n6["sase-pv.land--mon [failed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-3"></a>3 | sase-pv.land--3 | active | opus / claude | 2026-08-19T02:06:35.739219+00:00 | [1](../agents/bbugyi200.athena.sase-pv.land--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-pv.land--3/prompt.md) | — |
| <a id="member-1"></a>1 | sase-pv.land--1 | completed | opus / claude | 2026-08-19T01:43:10.962915+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pv.land--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pv.land--1/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-pv.land--mon-1 | failed | opus / claude | 2026-08-19T01:53:42.181400+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pv.land--mon-1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-pv.land--mon-0 | failed | opus / claude | 2026-08-19T01:44:49.329057+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pv.land--mon-0/chat.md) |
| <a id="member-2"></a>2 | sase-pv.land--2 | completed | opus / claude | 2026-08-19T01:45:53.660260+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pv.land--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pv.land--2/chat.md) |
| <a id="member-plan"></a>plan | sase-pv.land--plan | completed | opus / claude | 2026-08-19T01:03:16.667020+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pv.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pv.land--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-pv.land--mon | failed | opus / claude | 2026-08-19T01:25:03.951041+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pv.land--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`915cdee`](https://github.com/sase-org/sase/commit/915cdeeefd711ea8ede50b90cad9449699712922) | build(deps): ratchet the sase-core-rs window to \>=0.29.0,\<0.30.0 | 2026-08-19 02:23:12 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-pv.1](bbugyi200.athena.sase-pv.1.md) (family · 5) | sase-pv hood | completed 3, failed 2 |
| [sase-pv.2](../agents/bbugyi200.athena.sase-pv.2/README.md) | sase-pv hood | completed |
| [sase-pv.3](../agents/bbugyi200.athena.sase-pv.3/README.md) | sase-pv hood | completed |
| [sase-pv.4](../agents/bbugyi200.athena.sase-pv.4/README.md) | sase-pv hood | completed |
| [sase-pv.5](../agents/bbugyi200.athena.sase-pv.5/README.md) | sase-pv hood | completed |
| [sase-pv.6](../agents/bbugyi200.athena.sase-pv.6/README.md) | sase-pv hood | completed |
| [sase-pv.7](../agents/bbugyi200.athena.sase-pv.7/README.md) | sase-pv hood | completed |
| [sase-pv.7.f0](../agents/bbugyi200.athena.sase-pv.7.f0/README.md) | sase-pv hood | completed |
| [sase-pv.8](bbugyi200.athena.sase-pv.8.md) (family · 3) | sase-pv hood | completed 2, failed 1 |
| [sase-pv.9](../agents/bbugyi200.athena.sase-pv.9/README.md) | sase-pv hood | completed |
