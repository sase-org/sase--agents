# Family: sase-11l.11.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11l](../users/bbugyi200/machines/athena/hoods/sase-11l/README.md) / sase-11l.11.1

Owner: `bbugyi200.athena` · Hood: `sase-11l` · Members: 7 · Bead: [sase-11l.11.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11l/sase-11l.11.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11l.11.1--3 [completed]"]
  n1["sase-11l.11.1--1 [completed]"]
  n0 --> n1
  n2["sase-11l.11.1--mon [failed]"]
  n0 --> n2
  n3["sase-11l.11.1--2 [completed]"]
  n0 --> n3
  n4["sase-11l.11.1--mon-1 [failed]"]
  n0 --> n4
  n5["sase-11l.11.1--mon-0 [failed]"]
  n0 --> n5
  n6["sase-11l.11.1--plan [completed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-3"></a>3 | sase-11l.11.1--3 | completed | grok-4.6 / grok | 2026-09-19T01:26:29.636834+00:00 → 2026-09-19T02:51:09.190818+00:00 | [1](../agents/bbugyi200.athena.sase-11l.11.1--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-11l.11.1--3/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--3/chat.md) |
| <a id="member-1"></a>1 | sase-11l.11.1--1 | completed | grok-4.6 / grok | 2026-09-19T00:32:43.808461+00:00 → 2026-09-19T00:43:15.384329+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.1--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--1/chat.md) |
| <a id="member-mon"></a>mon | sase-11l.11.1--mon | failed | grok-4.6 / grok | 2026-09-18T23:55:25.643465+00:00 → 2026-09-19T00:32:33.436121+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--mon/chat.md) |
| <a id="member-2"></a>2 | sase-11l.11.1--2 | completed | grok-4.6 / grok | 2026-09-19T00:45:50.655409+00:00 → 2026-09-19T01:02:11.807894+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.1--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--2/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-11l.11.1--mon-1 | failed | grok-4.6 / grok | 2026-09-19T01:00:07.794329+00:00 → 2026-09-19T01:26:22.951061+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--mon-1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-11l.11.1--mon-0 | failed | grok-4.6 / grok | 2026-09-19T00:42:44.943174+00:00 → 2026-09-19T00:45:43.454481+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-11l.11.1--plan | completed | grok-4.6 / grok | 2026-09-18T22:10:47.073257+00:00 → 2026-09-18T23:57:31.773583+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.1--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`0e4cfe9`](https://github.com/sase-org/sase/commit/0e4cfe92cb9a0f007de7e44149c47e4495686cab) | feat(hold): unify CLI and directive selector parity | 2026-09-18 22:41:35 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11l.11.2](bbugyi200.athena.sase-11l.11.2.md) (family · 5) | sase-11l.11 hood | completed 3, failed 2 |
| [sase-11l.11.3](bbugyi200.athena.sase-11l.11.3.md) (family · 3) | sase-11l.11 hood | completed 2, failed 1 |
| [sase-11l.11.4](bbugyi200.athena.sase-11l.11.4.md) (family · 5) | sase-11l.11 hood | completed 3, failed 2 |
| [sase-11l.11.5.1](bbugyi200.athena.sase-11l.11.5.1.md) (family · 7) | sase-11l.11 hood | completed 4, failed 3 |
| [sase-11l.11.5.land](../agents/bbugyi200.athena.sase-11l.11.5.land/README.md) | sase-11l.11 hood | active |
| [sase-11l.11.land](bbugyi200.athena.sase-11l.11.land.md) (family · 3) | sase-11l.11 hood | failed 3 |
| [sase-11l.1](bbugyi200.athena.sase-11l.1.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.10](bbugyi200.athena.sase-11l.10.md) (family · 11) | sase-11l hood | active 1, completed 4, failed 6 |
| [sase-11l.2](../agents/bbugyi200.athena.sase-11l.2/README.md) | sase-11l hood | completed |
| [sase-11l.3](bbugyi200.athena.sase-11l.3.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.4](bbugyi200.athena.sase-11l.4.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.5](bbugyi200.athena.sase-11l.5.md) (family · 3) | sase-11l hood | failed 3 |
| [sase-11l.5](../agents/bbugyi200.athena.sase-11l.5/README.md) | sase-11l hood | dismissed |
| [sase-11l.5.1.1](bbugyi200.athena.sase-11l.5.1.1.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.5.1.2](bbugyi200.athena.sase-11l.5.1.2.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.5.1.2.1.1](../agents/bbugyi200.athena.sase-11l.5.1.2.1.1/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.2](../agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.3](../agents/bbugyi200.athena.sase-11l.5.1.2.1.3/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.4](../agents/bbugyi200.athena.sase-11l.5.1.2.1.4/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.land](bbugyi200.athena.sase-11l.5.1.2.1.land.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.5.1.2.1.land](../agents/bbugyi200.athena.sase-11l.5.1.2.1.land/README.md) | sase-11l hood | waiting |
| [sase-11l.5.1.3](bbugyi200.athena.sase-11l.5.1.3.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.5.1.land](bbugyi200.athena.sase-11l.5.1.land.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.6](../agents/bbugyi200.athena.sase-11l.6/README.md) | sase-11l hood | completed |
| [sase-11l.7](../agents/bbugyi200.athena.sase-11l.7/README.md) | sase-11l hood | completed |
| [sase-11l.8](../agents/bbugyi200.athena.sase-11l.8/README.md) | sase-11l hood | completed |
| [sase-11l.9](../agents/bbugyi200.athena.sase-11l.9/README.md) | sase-11l hood | completed |
| [sase-11l.land](bbugyi200.athena.sase-11l.land.md) (family · 3) | sase-11l hood | failed 3 |
