# Family: sase-11l.5.1.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11l](../users/bbugyi200/machines/athena/hoods/sase-11l/README.md) / sase-11l.5.1.1

Owner: `bbugyi200.athena` · Hood: `sase-11l` · Members: 3 · Bead: [sase-11l.5.1.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11l/sase-11l.5.1.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11l.5.1.1--code [completed]"]
  n1["sase-11l.5.1.1--gate [failed]"]
  n0 --> n1
  n2["sase-11l.5.1.1--plan [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-11l.5.1.1--code | completed | gpt-5.5 / codex | 2026-09-16T17:58:00.351482+00:00 → 2026-09-16T19:44:50.101390+00:00 | [1](../agents/bbugyi200.athena.sase-11l.5.1.1--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-11l.5.1.1--code/chat.md) |
| <a id="member-gate"></a>gate | sase-11l.5.1.1--gate | failed | gpt-5.6-sol / codex | 2026-09-16T17:56:15.966176+00:00 → 2026-09-16T17:57:04.361687+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.5.1.1--gate/chat.md) |
| <a id="member-plan"></a>plan | sase-11l.5.1.1--plan | completed | gpt-5.6-sol / codex | 2026-09-16T17:49:08.402135+00:00 → 2026-09-16T19:44:50.101390+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.5.1.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.5.1.1--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`82a37b0`](https://github.com/sase-org/sase/commit/82a37b0c02100a37083217c21a6a4ee4a30eb2dc) | feat(xprompt): add hold directive surface | 2026-09-16 15:26:25 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11l.5](../agents/bbugyi200.athena.sase-11l.5/README.md) | ancestor | dismissed |
| [sase-11l.5.1.2](bbugyi200.athena.sase-11l.5.1.2.md) (family · 3) | sase-11l.5.1 hood | failed 3 |
| [sase-11l.5.1.2.1.1](../agents/bbugyi200.athena.sase-11l.5.1.2.1.1/README.md) | sase-11l.5.1 hood | completed |
| [sase-11l.5.1.2.1.2](../agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | sase-11l.5.1 hood | completed |
| [sase-11l.5.1.2.1.3](../agents/bbugyi200.athena.sase-11l.5.1.2.1.3/README.md) | sase-11l.5.1 hood | active |
| [sase-11l.5.1.2.1.4](../agents/bbugyi200.athena.sase-11l.5.1.2.1.4/README.md) | sase-11l.5.1 hood | active |
| [sase-11l.5.1.2.1.land](../agents/bbugyi200.athena.sase-11l.5.1.2.1.land/README.md) | sase-11l.5.1 hood | waiting |
| [sase-11l.5.1.3](bbugyi200.athena.sase-11l.5.1.3.md) (family · 3) | sase-11l.5.1 hood | completed 2, failed 1 |
| [sase-11l.5.1.land](../agents/bbugyi200.athena.sase-11l.5.1.land/README.md) | sase-11l.5.1 hood | waiting |
| [sase-11l.1](bbugyi200.athena.sase-11l.1.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.10](../agents/bbugyi200.athena.sase-11l.10/README.md) | sase-11l hood | waiting |
| [sase-11l.2](../agents/bbugyi200.athena.sase-11l.2/README.md) | sase-11l hood | completed |
| [sase-11l.3](bbugyi200.athena.sase-11l.3.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.4](bbugyi200.athena.sase-11l.4.md) (family · 3) | sase-11l hood | completed 2, failed 1 |
| [sase-11l.6](../agents/bbugyi200.athena.sase-11l.6/README.md) | sase-11l hood | waiting |
| [sase-11l.7](../agents/bbugyi200.athena.sase-11l.7/README.md) | sase-11l hood | completed |
| [sase-11l.8](../agents/bbugyi200.athena.sase-11l.8/README.md) | sase-11l hood | completed |
| [sase-11l.9](../agents/bbugyi200.athena.sase-11l.9/README.md) | sase-11l hood | waiting |
| [sase-11l.land](../agents/bbugyi200.athena.sase-11l.land/README.md) | sase-11l hood | waiting |
