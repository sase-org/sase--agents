# Session: sase-1sb.2.1.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-1sb](../users/bbugyi200/machines/athena/hoods/sase-1sb/README.md) / sase-1sb.2.1.land

Owner: `bbugyi200.athena` · Hood: `sase-1sb` · Members: 3 · Bead: [sase-1sb.2.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1sb/sase-1sb.2.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-1sb.2.1.land--gate [completed]"]
  n1["sase-1sb.2.1.land--plan [active]"]
  n0 --> n1
  n2["sase-1sb.2.1.land--code [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | sase-1sb.2.1.land--gate | completed | gpt-6-astra / codex | 2026-11-12T10:32:30.939549+00:00 → 2026-11-12T10:33:32.629604+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-1sb.2.1.land--gate/chat.md) |
| <a id="member-plan"></a>plan | sase-1sb.2.1.land--plan | active | gpt-6-astra / codex | 2026-11-12T10:16:58.981858+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-1sb.2.1.land--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-1sb.2.1.land--plan/chat.md) |
| <a id="member-code"></a>code | sase-1sb.2.1.land--code | active | gpt-6-luna / codex | 2026-11-12T10:34:31.500426+00:00 | 0 | — | — |

## Variables

| Role | Variable | Value |
|---|---|---|
| plan | `artifacts` | \[{bead: sase-1sb.2.1, kind: file, label: sase-1sb.2.1 landing trust gaps and edit-lock race reproductions, path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261111203826/landing-evidence-0… |

#### artifacts

**Role:** `plan`

```yaml
- bead: sase-1sb.2.1
  kind: file
  label: sase-1sb.2.1 landing trust gaps and edit-lock race reproductions
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261111203826/landing-evidence-07a343a9cf06.txt
  ref: file:explicit:f7ff68994727a64108f4cdd2
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/land-trust/landing-evidence.txt
```

Values are truncated for display; see each member's agent meta.json for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1sb.2](bbugyi200.athena.sase-1sb.2.md) (session · 3) | ancestor | active 1, completed 2 |
| [sase-1sb.2.1.1](bbugyi200.athena.sase-1sb.2.1.1.md) (session · 5) | sase-1sb.2.1 hood | completed 4, failed 1 |
| [sase-1sb.2.1.2](../agents/bbugyi200.athena.sase-1sb.2.1.2/README.md) | sase-1sb.2.1 hood | completed |
| [sase-1sb.2.1.3](bbugyi200.athena.sase-1sb.2.1.3.md) (session · 5) | sase-1sb.2.1 hood | completed 4, failed 1 |
| [sase-1sb.2.1.4](../agents/bbugyi200.athena.sase-1sb.2.1.4/README.md) | sase-1sb.2.1 hood | completed |
| [sase-1sb.1](../agents/bbugyi200.athena.sase-1sb.1/README.md) | sase-1sb hood | completed |
| [sase-1sb.3](../agents/bbugyi200.athena.sase-1sb.3/README.md) | sase-1sb hood | completed |
| [sase-1sb.4](bbugyi200.athena.sase-1sb.4.md) (session · 3) | sase-1sb hood | completed 2, failed 1 |
| [sase-1sb.5](../agents/bbugyi200.athena.sase-1sb.5/README.md) | sase-1sb hood | completed |
| [sase-1sb.6](../agents/bbugyi200.athena.sase-1sb.6/README.md) | sase-1sb hood | completed |
| [sase-1sb.7](bbugyi200.athena.sase-1sb.7.md) (session · 3) | sase-1sb hood | completed 3 |
| [sase-1sb.land](../agents/bbugyi200.athena.sase-1sb.land/README.md) | sase-1sb hood | waiting |
