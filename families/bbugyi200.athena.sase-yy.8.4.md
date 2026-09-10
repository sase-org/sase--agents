# Family: sase-yy.8.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-yy](../users/bbugyi200/machines/athena/hoods/sase-yy/README.md) / sase-yy.8.4

Owner: `bbugyi200.athena` · Hood: `sase-yy` · Members: 3 · Bead: [sase-yy.8.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-yy/sase-yy.8.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-yy.8.4--plan [active]"]
  n1["sase-yy.8.4--code [active]"]
  n0 --> n1
  n2["sase-yy.8.4--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-yy.8.4--plan | active | opus / claude | 2026-09-10T21:59:49.717326+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-yy.8.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-yy.8.4--plan/chat.md) |
| <a id="member-code"></a>code | sase-yy.8.4--code | active | gpt-5.5 / codex | 2026-09-10T22:14:31.050309+00:00 | [1](../agents/bbugyi200.athena.sase-yy.8.4--code/README.md#commits) | — | — |
| <a id="member-gate"></a>gate | sase-yy.8.4--gate | failed | opus / claude | 2026-09-10T22:14:12.526432+00:00 → 2026-09-10T22:14:19.406795+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-yy.8.4--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`2dcd6a1`](https://github.com/sase-org/sase/commit/2dcd6a136c715427c3916581a4e942822dc47155) | feat(artifact-links): make cutover import resumable | 2026-09-10 19:37:26 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-yy.8.1](../agents/bbugyi200.athena.sase-yy.8.1/README.md) | sase-yy.8 hood | completed |
| [sase-yy.8.2](bbugyi200.athena.sase-yy.8.2.md) (family · 3) | sase-yy.8 hood | completed 2, failed 1 |
| [sase-yy.8.3](bbugyi200.athena.sase-yy.8.3.md) (family · 3) | sase-yy.8 hood | completed 2, failed 1 |
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
