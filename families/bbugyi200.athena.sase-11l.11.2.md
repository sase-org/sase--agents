# Family: sase-11l.11.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11l](../users/bbugyi200/machines/athena/hoods/sase-11l/README.md) / sase-11l.11.2

Owner: `bbugyi200.athena` · Hood: `sase-11l` · Members: 5 · Bead: [sase-11l.11.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11l/sase-11l.11.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11l.11.2--plan [completed]"]
  n1["sase-11l.11.2--1 [completed]"]
  n0 --> n1
  n2["sase-11l.11.2--2 [completed]"]
  n0 --> n2
  n3["sase-11l.11.2--mon [failed]"]
  n0 --> n3
  n4["sase-11l.11.2--mon-0 [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-11l.11.2--plan | completed | grok-4.6 / grok | 2026-09-19T02:59:06.439629+00:00 → 2026-09-19T03:39:36.142305+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.2--plan/chat.md) |
| <a id="member-1"></a>1 | sase-11l.11.2--1 | completed | grok-4.6 / grok | 2026-09-19T04:02:14.465396+00:00 → 2026-09-19T04:16:14.479115+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.2--1/chat.md) |
| <a id="member-2"></a>2 | sase-11l.11.2--2 | completed | grok-4.6 / grok | 2026-09-19T04:33:06.130512+00:00 → 2026-09-19T04:44:31.834977+00:00 | [1](../agents/bbugyi200.athena.sase-11l.11.2--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-11l.11.2--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.2--2/chat.md) |
| <a id="member-mon"></a>mon | sase-11l.11.2--mon | failed | grok-4.6 / grok | 2026-09-19T03:38:53.435441+00:00 → 2026-09-19T04:02:04.576761+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.2--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-11l.11.2--mon-0 | failed | grok-4.6 / grok | 2026-09-19T04:15:44.239247+00:00 → 2026-09-19T04:32:58.943584+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.2--mon-0/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`8de747c`](https://github.com/sase-org/sase/commit/8de747c36a0a1e01f56ce455d2bb14621f27ef6b) | feat(hold): serialize hold publication with admission transitions | 2026-09-19 00:40:12 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11l.11.1](bbugyi200.athena.sase-11l.11.1.md) (family · 7) | sase-11l.11 hood | completed 4, failed 3 |
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
