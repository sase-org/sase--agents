# Family: sase-m6.6.1.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-m6](../users/bbugyi200/machines/athena/hoods/sase-m6/README.md) / sase-m6.6.1.1

Owner: `bbugyi200.athena` · Hood: `sase-m6` · Members: 5 · Bead: [sase-m6.6.1.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-m6/sase-m6.6.1.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-m6.6.1.1--2 [completed]"]
  n1["sase-m6.6.1.1--1 [completed]"]
  n0 --> n1
  n2["sase-m6.6.1.1--plan [completed]"]
  n0 --> n2
  n3["sase-m6.6.1.1--mon-0 [failed]"]
  n0 --> n3
  n4["sase-m6.6.1.1--mon [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-m6.6.1.1--2 | completed | sonnet / claude | 2026-08-15T11:00:54.033989+00:00 | [1](../agents/bbugyi200.athena.sase-m6.6.1.1--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-m6.6.1.1--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.1--2/chat.md) |
| <a id="member-1"></a>1 | sase-m6.6.1.1--1 | completed | sonnet / claude | 2026-08-15T10:53:33.849265+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m6.6.1.1--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.1--1/chat.md) |
| <a id="member-plan"></a>plan | sase-m6.6.1.1--plan | completed | sonnet / claude | 2026-08-15T10:21:05.465846+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-m6.6.1.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.1--plan/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-m6.6.1.1--mon-0 | failed | sonnet / claude | 2026-08-15T10:54:23.470729+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.1--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-m6.6.1.1--mon | failed | sonnet / claude | 2026-08-15T10:53:05.018054+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-m6.6.1.1--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`2f9b59c`](https://github.com/sase-org/sase/commit/2f9b59cadb2a25169a15a58c8ab7aa5c05c2cfc4) | feat(ace): define and compile the shared query profile | 2026-08-15 07:02:27 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-m6.6](../agents/bbugyi200.athena.sase-m6.6/README.md) | ancestor | failed |
| [sase-m6.6.1.2](bbugyi200.athena.sase-m6.6.1.2.md) (family · 2) | sase-m6.6.1 hood | completed 2 |
| [sase-m6.6.1.3](../agents/bbugyi200.athena.sase-m6.6.1.3/README.md) | sase-m6.6.1 hood | completed |
| [sase-m6.6.1.4](../agents/bbugyi200.athena.sase-m6.6.1.4/README.md) | sase-m6.6.1 hood | completed |
| [sase-m6.6.1.5](bbugyi200.athena.sase-m6.6.1.5.md) (family · 4) | sase-m6.6.1 hood | completed 1, dismissed 2, failed 1 |
| [sase-m6.6.1.6](bbugyi200.athena.sase-m6.6.1.6.md) (family · 2) | sase-m6.6.1 hood | completed 1, dismissed 1 |
| [sase-m6.6.1.7](../agents/bbugyi200.athena.sase-m6.6.1.7/README.md) | sase-m6.6.1 hood | dismissed |
| [sase-m6.6.1.land](bbugyi200.athena.sase-m6.6.1.land.md) (family · 2) | sase-m6.6.1 hood | completed 1, dismissed 1 |
| [sase-m6.1](../agents/bbugyi200.athena.sase-m6.1/README.md) | sase-m6 hood | completed |
| [sase-m6.10](bbugyi200.athena.sase-m6.10.md) (family · 3) | sase-m6 hood | completed 2, failed 1 |
| [sase-m6.2](../agents/bbugyi200.athena.sase-m6.2/README.md) | sase-m6 hood | completed |
| [sase-m6.3](bbugyi200.athena.sase-m6.3.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.4](bbugyi200.athena.sase-m6.4.md) (family · 4) | sase-m6 hood | completed 3, failed 1 |
| [sase-m6.5](bbugyi200.athena.sase-m6.5.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.7](bbugyi200.athena.sase-m6.7.md) (family · 2) | sase-m6 hood | failed 2 |
| [sase-m6.7.1.1](../agents/bbugyi200.athena.sase-m6.7.1.1/README.md) | sase-m6 hood | dismissed |
| [sase-m6.7.1.2](bbugyi200.athena.sase-m6.7.1.2.md) (family · 4) | sase-m6 hood | completed 2, dismissed 1, failed 1 |
| [sase-m6.7.1.3](bbugyi200.athena.sase-m6.7.1.3.md) (family · 8) | sase-m6 hood | completed 4, dismissed 1, failed 3 |
| [sase-m6.7.1.4](bbugyi200.athena.sase-m6.7.1.4.md) (family · 3) | sase-m6 hood | completed 1, dismissed 1, failed 1 |
| [sase-m6.7.1.5](bbugyi200.athena.sase-m6.7.1.5.md) (family · 2) | sase-m6 hood | completed 1, dismissed 1 |
| [sase-m6.7.1.6](bbugyi200.athena.sase-m6.7.1.6.md) (family · 3) | sase-m6 hood | dismissed 2, failed 1 |
| [sase-m6.7.1.land](../agents/bbugyi200.athena.sase-m6.7.1.land/README.md) | sase-m6 hood | dismissed |
| [sase-m6.8](bbugyi200.athena.sase-m6.8.md) (family · 2) | sase-m6 hood | completed 2 |
| [sase-m6.8](../agents/bbugyi200.athena.sase-m6.8/README.md) | sase-m6 hood | waiting |
| [sase-m6.9](../agents/bbugyi200.athena.sase-m6.9/README.md) | sase-m6 hood | completed |
| [sase-m6.land](../agents/bbugyi200.athena.sase-m6.land/README.md) | sase-m6 hood | completed |
