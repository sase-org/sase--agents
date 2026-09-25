# Family: sase-11y.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11y](../users/bbugyi200/machines/athena/hoods/sase-11y/README.md) / sase-11y.5

Owner: `bbugyi200.athena` · Hood: `sase-11y` · Members: 7 · Bead: [sase-11y.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11y/sase-11y.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11y.5--2 [active]"]
  n1["sase-11y.5--mon-0 [active]"]
  n0 --> n1
  n2["sase-11y.5--gate [active]"]
  n0 --> n2
  n3["sase-11y.5--plan [active]"]
  n0 --> n3
  n4["sase-11y.5--mon [failed]"]
  n0 --> n4
  n5["sase-11y.5--1 [active]"]
  n0 --> n5
  n6["sase-11y.5--code [completed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-11y.5--2 | active | grok-4.6 / grok | 2026-09-19T12:53:14.349142+00:00 | [1](../agents/bbugyi200.athena.sase-11y.5--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-11y.5--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.5--2/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-11y.5--mon-0 | active | grok-4.6 / grok | 2026-09-19T12:15:10.794650+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.5--mon-0/chat.md) |
| <a id="member-gate"></a>gate | sase-11y.5--gate | active | grok-4.6 / grok | 2026-09-19T10:23:43.169298+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.5--gate/chat.md) |
| <a id="member-plan"></a>plan | sase-11y.5--plan | active | grok-4.6 / grok | 2026-09-19T10:14:45.142966+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11y.5--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.5--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-11y.5--mon | failed | grok-4.6 / grok | 2026-09-19T11:18:26.206021+00:00 → 2026-09-19T12:08:45.053611+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.5--mon/chat.md) |
| <a id="member-1"></a>1 | sase-11y.5--1 | active | grok-4.6 / grok | 2026-09-19T12:08:43.837947+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11y.5--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11y.5--1/chat.md) |
| <a id="member-code"></a>code | sase-11y.5--code | completed | grok-4.6 / grok | 2026-09-19T10:24:42.003967+00:00 → 2026-09-19T11:20:21.388576+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11y.5--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`3fb42fa`](https://github.com/sase-org/sase/commit/3fb42fa11ee2ba0539a085484edb2e3f98e6dd1f) | feat(service): add platform unit integration | 2026-09-18 09:07:18 EDT |
| 2 | sase | [`23c740a`](https://github.com/sase-org/sase/commit/23c740a9aab8eb0f6a2e24abfab9e5cfb02321c0) | feat(service): finish native platform units and init integration | 2026-09-19 09:57:17 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11y.1](../agents/bbugyi200.athena.sase-11y.1/README.md) | sase-11y hood | active |
| [sase-11y.10](bbugyi200.athena.sase-11y.10.md) (family · 3) | sase-11y hood | active 3 |
| [sase-11y.10.1.1](../agents/bbugyi200.athena.sase-11y.10.1.1/README.md) | sase-11y hood | active |
| [sase-11y.10.1.2](bbugyi200.athena.sase-11y.10.1.2.md) (family · 3) | sase-11y hood | active 2, completed 1 |
| [sase-11y.10.1.3](bbugyi200.athena.sase-11y.10.1.3.md) (family · 3) | sase-11y hood | active 3 |
| [sase-11y.10.1.3.1.1](../agents/bbugyi200.athena.sase-11y.10.1.3.1.1/README.md) | sase-11y hood | active |
| [sase-11y.10.1.3.1.2](bbugyi200.athena.sase-11y.10.1.3.1.2.md) (family · 3) | sase-11y hood | active 3 |
| [sase-11y.10.1.3.1.3](../agents/bbugyi200.athena.sase-11y.10.1.3.1.3/README.md) | sase-11y hood | active |
| [sase-11y.10.1.3.1.4](../agents/bbugyi200.athena.sase-11y.10.1.3.1.4/README.md) | sase-11y hood | active |
| [sase-11y.10.1.3.1.5](../agents/bbugyi200.athena.sase-11y.10.1.3.1.5/README.md) | sase-11y hood | active |
| [sase-11y.10.1.3.1.land](../agents/bbugyi200.athena.sase-11y.10.1.3.1.land/README.md) | sase-11y hood | active |
| [sase-11y.10.1.4](bbugyi200.athena.sase-11y.10.1.4.md) (family · 9) | sase-11y hood | active 7, completed 1, failed 1 |
| [sase-11y.10.1.5](../agents/bbugyi200.athena.sase-11y.10.1.5/README.md) | sase-11y hood | active |
| [sase-11y.10.1.6](../agents/bbugyi200.athena.sase-11y.10.1.6/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.1](../agents/bbugyi200.athena.sase-11y.10.1.7.1/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.2](../agents/bbugyi200.athena.sase-11y.10.1.7.2/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.3](../agents/bbugyi200.athena.sase-11y.10.1.7.3/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.4](../agents/bbugyi200.athena.sase-11y.10.1.7.4/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.5](../agents/bbugyi200.athena.sase-11y.10.1.7.5/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.6](../agents/bbugyi200.athena.sase-11y.10.1.7.6/README.md) | sase-11y hood | active |
| [sase-11y.10.1.7.land](../agents/bbugyi200.athena.sase-11y.10.1.7.land/README.md) | sase-11y hood | active |
| [sase-11y.10.1.land](bbugyi200.athena.sase-11y.10.1.land.md) (family · 3) | sase-11y hood | active 3 |
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
| [sase-11y.6](bbugyi200.athena.sase-11y.6.md) (family · 3) | sase-11y hood | active 2, completed 1 |
| [sase-11y.7](bbugyi200.athena.sase-11y.7.md) (family · 12) | sase-11y hood | active 3, completed 5, failed 4 |
| [sase-11y.7.f0](../agents/bbugyi200.athena.sase-11y.7.f0/README.md) | sase-11y hood | active |
| [sase-11y.7.f1](bbugyi200.athena.sase-11y.7.f1.md) (family · 2) | sase-11y hood | active 2 |
| [sase-11y.8](../agents/bbugyi200.athena.sase-11y.8/README.md) | sase-11y hood | active |
| [sase-11y.9](../agents/bbugyi200.athena.sase-11y.9/README.md) | sase-11y hood | active |
| [sase-11y.land](bbugyi200.athena.sase-11y.land.md) (family · 3) | sase-11y hood | active 3 |
