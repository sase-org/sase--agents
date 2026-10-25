# Session: sase-1nn.8.4.3.5.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-1nn](../users/bbugyi200/machines/athena/hoods/sase-1nn/README.md) / sase-1nn.8.4.3.5.1

Owner: `bbugyi200.athena` · Hood: `sase-1nn` · Members: 3 · Bead: [sase-1nn.8.4.3.5.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1nn/sase-1nn.8.4.3.5.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1nn.8.4.3.5.1--mon [failed]"]
  n1["sase-1nn.8.4.3.5.1--plan [completed]"]
  n0 --> n1
  n2["sase-1nn.8.4.3.5.1--1 [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | sase-1nn.8.4.3.5.1--mon | failed | muse-spark-1.3-contributor / muse | 2026-10-25T02:54:37.542715+00:00 → 2026-10-25T02:57:07.309731+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.1--mon/chat.md) |
| <a id="member-plan"></a>plan | sase-1nn.8.4.3.5.1--plan | completed | muse-spark-1.3-contributor / muse | 2026-10-25T02:24:40.417288+00:00 → 2026-10-25T02:55:22.722427+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.1--plan/chat.md) |
| <a id="member-1"></a>1 | sase-1nn.8.4.3.5.1--1 | active | muse-spark-1.3-contributor / muse | 2026-10-25T02:58:35.244856+00:00 | [1](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.1--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.1--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`3d13864`](https://github.com/sase-org/sase/commit/3d13864e7632da0911e98ef2ba7e00e669527556) | chore(integrate): archive recovery evidence and remove tracked .sase-evidence | 2026-10-24 23:02:56 EDT |

## Variables

| Role | Variable | Value |
|---|---|---|
| plan | `artifacts` | \[{bead: sase-1nv.5, kind: file, label: sase-1nv.5 complete recovery evidence (99 files + manifest), path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261024222317/sase-1nv5-recovery-eviden… |

#### artifacts

**Role:** `plan`

```yaml
- bead: sase-1nv.5
  kind: file
  label: sase-1nv.5 complete recovery evidence (99 files + manifest)
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261024222317/sase-1nv5-recovery-evidence-complete.tar-1c82bbdbda69.gz
  ref: file:explicit:ddc1ff91f98de4e168df0d63
  source_path: /tmp/sase-integrate-evidence/sase-1nv5-recovery-evidence-complete.tar.gz
```

Values are truncated for display; see each member's agent meta.json for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1nn.8.4.3.5.2](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.2/README.md) | sase-1nn.8.4.3.5 hood | completed |
| [sase-1nn.8.4.3.5.3](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.3/README.md) | sase-1nn.8.4.3.5 hood | waiting |
| [sase-1nn.8.4.3.5.land](../agents/bbugyi200.athena.sase-1nn.8.4.3.5.land/README.md) | sase-1nn.8.4.3.5 hood | waiting |
| [sase-1nn.8.4.3.1](bbugyi200.athena.sase-1nn.8.4.3.1.md) (session · 3) | sase-1nn.8.4.3 hood | completed 2, failed 1 |
| [sase-1nn.8.4.3.2](../agents/bbugyi200.athena.sase-1nn.8.4.3.2/README.md) | sase-1nn.8.4.3 hood | completed |
| [sase-1nn.8.4.3.3](bbugyi200.athena.sase-1nn.8.4.3.3.md) (session · 3) | sase-1nn.8.4.3 hood | completed 2, failed 1 |
| [sase-1nn.8.4.3.4](bbugyi200.athena.sase-1nn.8.4.3.4.md) (session · 2) | sase-1nn.8.4.3 hood | completed 1, failed 1 |
| [sase-1nn.8.4.3.land](bbugyi200.athena.sase-1nn.8.4.3.land.md) (session · 3) | sase-1nn.8.4.3 hood | failed 3 |
| [sase-1nn.8.4.1](bbugyi200.athena.sase-1nn.8.4.1.md) (session · 3) | sase-1nn.8.4 hood | completed 2, failed 1 |
| [sase-1nn.8.4.2](bbugyi200.athena.sase-1nn.8.4.2.md) (session · 2) | sase-1nn.8.4 hood | completed 1, failed 1 |
| [sase-1nn.8.4.land](bbugyi200.athena.sase-1nn.8.4.land.md) (session · 13) | sase-1nn.8.4 hood | completed 7, failed 6 |
| [sase-1nn.8.1](../agents/bbugyi200.athena.sase-1nn.8.1/README.md) | sase-1nn.8 hood | active |
| [sase-1nn.8.2](bbugyi200.athena.sase-1nn.8.2.md) (session · 5) | sase-1nn.8 hood | active 5 |
| [sase-1nn.8.3](bbugyi200.athena.sase-1nn.8.3.md) (session · 2) | sase-1nn.8 hood | active 2 |
| [sase-1nn.8.land](bbugyi200.athena.sase-1nn.8.land.md) (session · 3) | sase-1nn.8 hood | active 3 |
| [sase-1nn.1](../agents/bbugyi200.athena.sase-1nn.1/README.md) | sase-1nn hood | active |
| [sase-1nn.2](bbugyi200.athena.sase-1nn.2.md) (session · 5) | sase-1nn hood | active 5 |
| [sase-1nn.3](bbugyi200.athena.sase-1nn.3.md) (session · 3) | sase-1nn hood | active 3 |
| [sase-1nn.4](../agents/bbugyi200.athena.sase-1nn.4/README.md) | sase-1nn hood | active |
| [sase-1nn.5](bbugyi200.athena.sase-1nn.5.md) (session · 15) | sase-1nn hood | active 15 |
| [sase-1nn.6](../agents/bbugyi200.athena.sase-1nn.6/README.md) | sase-1nn hood | active |
| [sase-1nn.7](bbugyi200.athena.sase-1nn.7.md) (session · 2) | sase-1nn hood | active 2 |
| [sase-1nn.land](bbugyi200.athena.sase-1nn.land.md) (session · 3) | sase-1nn hood | active 3 |
