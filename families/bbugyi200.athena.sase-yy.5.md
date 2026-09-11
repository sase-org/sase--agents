# Family: sase-yy.5

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-yy](../users/bbugyi200/machines/athena/hoods/sase-yy/README.md) / sase-yy.5

Owner: `bbugyi200.athena` · Hood: `sase-yy` · Members: 5 · Bead: [sase-yy.5](https://github.com/sase-org/sase--beads/blob/main/pages/sase-yy/sase-yy.5.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-yy.5--plan [active]"]
  n1["sase-yy.5--gate [failed]"]
  n0 --> n1
  n2["sase-yy.5--mon [failed]"]
  n0 --> n2
  n3["sase-yy.5--code [completed]"]
  n0 --> n3
  n4["sase-yy.5--1 [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-yy.5--plan | active | gpt-5.6-sol / codex | 2026-09-09T18:28:08.367676+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-yy.5--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-yy.5--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-yy.5--gate | failed | gpt-5.6-sol / codex | 2026-09-09T18:35:44.651646+00:00 → 2026-09-09T18:35:57.740951+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-yy.5--gate/chat.md) |
| <a id="member-mon"></a>mon | sase-yy.5--mon | failed | gpt-5.5 / codex | 2026-09-09T19:48:08.910193+00:00 → 2026-09-09T20:21:59.845005+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-yy.5--mon/chat.md) |
| <a id="member-code"></a>code | sase-yy.5--code | completed | gpt-5.5 / codex | 2026-09-09T18:36:37.999896+00:00 → 2026-09-09T19:48:35.380998+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-yy.5--code/chat.md) |
| <a id="member-1"></a>1 | sase-yy.5--1 | failed | gpt-5.5 / codex | 2026-09-09T20:22:27.866347+00:00 → 2026-09-10T07:36:25.612033+00:00 | [1](../agents/bbugyi200.athena.sase-yy.5--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-yy.5--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`ea096db`](https://github.com/sase-org/sase/commit/ea096dbfcb3198cac511181c2270d44d478b5b17) | feat(agent): bind prompt stack waits to predecessors | 2026-09-09 20:34:34 EDT |
| — | sase | [`ba73bc3`](https://github.com/sase-org/sase/commit/ba73bc30e4c0438e8861dfbe3e95a3754d121252) | feat(artifact-links): consume reduced event truth | 2026-09-10 09:59:41 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-yy.1](bbugyi200.athena.sase-yy.1.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.2](bbugyi200.athena.sase-yy.2.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.3](../agents/bbugyi200.athena.sase-yy.3/README.md) | sase-yy hood | completed |
| [sase-yy.4](bbugyi200.athena.sase-yy.4.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.6](bbugyi200.athena.sase-yy.6.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.6](../agents/bbugyi200.athena.sase-yy.6/README.md) | sase-yy hood | waiting |
| [sase-yy.7](../agents/bbugyi200.athena.sase-yy.7/README.md) | sase-yy hood | completed |
| [sase-yy.8.1](../agents/bbugyi200.athena.sase-yy.8.1/README.md) | sase-yy hood | completed |
| [sase-yy.8.2](bbugyi200.athena.sase-yy.8.2.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.8.3](bbugyi200.athena.sase-yy.8.3.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.8.4](bbugyi200.athena.sase-yy.8.4.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.8.5](bbugyi200.athena.sase-yy.8.5.md) (family · 3) | sase-yy hood | completed 2, failed 1 |
| [sase-yy.8.6.1](../agents/bbugyi200.athena.sase-yy.8.6.1/README.md) | sase-yy hood | completed |
| [sase-yy.8.6.2](../agents/bbugyi200.athena.sase-yy.8.6.2/README.md) | sase-yy hood | active |
| [sase-yy.8.6.3](../agents/bbugyi200.athena.sase-yy.8.6.3/README.md) | sase-yy hood | waiting |
| [sase-yy.8.6.4](../agents/bbugyi200.athena.sase-yy.8.6.4/README.md) | sase-yy hood | waiting |
| [sase-yy.8.6.5](../agents/bbugyi200.athena.sase-yy.8.6.5/README.md) | sase-yy hood | completed |
| [sase-yy.8.6.6](../agents/bbugyi200.athena.sase-yy.8.6.6/README.md) | sase-yy hood | waiting |
| [sase-yy.8.6.land](../agents/bbugyi200.athena.sase-yy.8.6.land/README.md) | sase-yy hood | waiting |
| [sase-yy.8.land](bbugyi200.athena.sase-yy.8.land.md) (family · 5) | sase-yy hood | completed 2, failed 3 |
| [sase-yy.land](bbugyi200.athena.sase-yy.land.md) (family · 3) | sase-yy hood | failed 3 |
