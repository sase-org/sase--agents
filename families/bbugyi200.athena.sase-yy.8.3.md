# Family: sase-yy.8.3

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-yy](../users/bbugyi200/machines/athena/hoods/sase-yy/README.md) / sase-yy.8.3

Owner: `bbugyi200.athena` · Hood: `sase-yy` · Members: 3 · Bead: [sase-yy.8.3](https://github.com/sase-org/sase--beads/blob/main/pages/sase-yy/sase-yy.8.3.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-yy.8.3--code [completed]"]
  n1["sase-yy.8.3--gate [failed]"]
  n0 --> n1
  n2["sase-yy.8.3--plan [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-yy.8.3--code | completed | gpt-5.5 / codex | 2026-09-10T20:56:34.925815+00:00 → 2026-09-10T21:58:53.018756+00:00 | [1](../agents/bbugyi200.athena.sase-yy.8.3--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-yy.8.3--code/chat.md) |
| <a id="member-gate"></a>gate | sase-yy.8.3--gate | failed | gpt-5.6-sol / codex | 2026-09-10T20:56:04.218597+00:00 → 2026-09-10T20:56:15.116569+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-yy.8.3--gate/chat.md) |
| <a id="member-plan"></a>plan | sase-yy.8.3--plan | completed | gpt-5.6-sol / codex | 2026-09-10T20:49:28.006829+00:00 → 2026-09-10T21:58:53.018756+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-yy.8.3--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-yy.8.3--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`840824c`](https://github.com/sase-org/sase/commit/840824c5bb71a9d78e46ee446625f47cdea0b7d4) | feat(sdd): reconcile artifact link event unions | 2026-09-10 17:53:38 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-yy.8.1](../agents/bbugyi200.athena.sase-yy.8.1/README.md) | sase-yy.8 hood | completed |
| [sase-yy.8.2](bbugyi200.athena.sase-yy.8.2.md) (family · 3) | sase-yy.8 hood | completed 2, failed 1 |
| [sase-yy.8.4](bbugyi200.athena.sase-yy.8.4.md) (family · 3) | sase-yy.8 hood | active 2, failed 1 |
| [sase-yy.8.5](../agents/bbugyi200.athena.sase-yy.8.5/README.md) | sase-yy.8 hood | waiting |
| [sase-yy.8.land](../agents/bbugyi200.athena.sase-yy.8.land/README.md) | sase-yy.8 hood | waiting |
| [sase-yy.1](bbugyi200.athena.sase-yy.1.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.2](bbugyi200.athena.sase-yy.2.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.3](../agents/bbugyi200.athena.sase-yy.3/README.md) | sase-yy hood | completed |
| [sase-yy.4](bbugyi200.athena.sase-yy.4.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.5](bbugyi200.athena.sase-yy.5.md) (family · 5) | sase-yy hood | active 1, completed 1, failed 3 |
| [sase-yy.6](bbugyi200.athena.sase-yy.6.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.6](../agents/bbugyi200.athena.sase-yy.6/README.md) | sase-yy hood | waiting |
| [sase-yy.7](../agents/bbugyi200.athena.sase-yy.7/README.md) | sase-yy hood | completed |
| [sase-yy.land](bbugyi200.athena.sase-yy.land.md) (family · 3) | sase-yy hood | failed 3 |
