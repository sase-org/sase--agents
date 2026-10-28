# Agent: sase-1ou.2.1.2--3

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [sase-1ou](../../users/bbugyi200/machines/athena/hoods/sase-1ou/README.md) / [sase-1ou.2.1.2](../../sessions/bbugyi200.athena.sase-1ou.2.1.2.md) / sase-1ou.2.1.2--3

**Global name:** `bbugyi200.athena.sase-1ou.2.1.2--3` · **State:** active · **Source run:** `run-2a4db04613c4506203802d5864c6c291`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** sase-1ou

## Summary

- Bead: [sase-1ou.2.1.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ou/sase-1ou.2.1.2.md)
- Model: gpt-6-astra
- Provider: codex
- Timing: 2026-10-27T21:27:26.869294+00:00
- Commits: [1](#commits)
- Variables: [1](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Commits

| Repo | Commit | Subject | Committed |
|---|---|---|---|
| sase | [`57d5f41`](https://github.com/sase-org/sase/commit/57d5f411e41e543ffa10d9a91ab45fd66f62ebb6) | fix(tool): delegate default contention budgets to Rust | 2026-10-27 17:40:35 EDT |

## Variables

| Variable | Value |
|---|---|
| `artifacts` | \[{bead: sase-1ou.2.1.2, kind: file, label: ToolRun final budget verification evidence bundle, path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261027172454/budget-evidence-bundle-c0c5b78e… |

#### artifacts

```yaml
- bead: sase-1ou.2.1.2
  kind: file
  label: ToolRun final budget verification evidence bundle
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261027172454/budget-evidence-bundle-c0c5b78e54dc.json
  ref: file:explicit:c0f4bd59f97240f4bbc90b82
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.sase/toolrun-contention/budget-evidence-bundle.json
- bead: sase-1ou.2.1.2
  kind: markdown
  label: ToolRun caller integration final evidence and landing table
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261027172454/land-evidence-f8af7bd71a01.md
  ref: file:explicit:b0d1fd4be5d7f8c6c632927d
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.sase/toolrun-contention/land-evidence.md
```

Values are truncated for display; see [meta.json](meta.json) for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1ou.2](../../sessions/bbugyi200.athena.sase-1ou.2.md) (session · 3) | ancestor | failed 3 |
| [sase-1ou.2.1.1](../bbugyi200.athena.sase-1ou.2.1.1/README.md) | sase-1ou.2.1 hood | active |
| [sase-1ou.2.1.land](../../sessions/bbugyi200.athena.sase-1ou.2.1.land.md) (session · 3) | sase-1ou.2.1 hood | active 3 |
| [sase-1ou.1](../bbugyi200.athena.sase-1ou.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.3](../../sessions/bbugyi200.athena.sase-1ou.3.md) (session · 7) | sase-1ou hood | completed 4, failed 3 |
| [sase-1ou.4](../../sessions/bbugyi200.athena.sase-1ou.4.md) (session · 5) | sase-1ou hood | completed 3, failed 2 |
| [sase-1ou.5](../../sessions/bbugyi200.athena.sase-1ou.5.md) (session · 3) | sase-1ou hood | failed 3 |
| [sase-1ou.5.1.1](../bbugyi200.athena.sase-1ou.5.1.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.2](../bbugyi200.athena.sase-1ou.5.1.2/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.3](../../sessions/bbugyi200.athena.sase-1ou.5.1.3.md) (session · 3) | sase-1ou hood | completed 2, failed 1 |
| [sase-1ou.5.1.4](../../sessions/bbugyi200.athena.sase-1ou.5.1.4.md) (session · 5) | sase-1ou hood | completed 3, failed 2 |
| [sase-1ou.5.1.land](../bbugyi200.athena.sase-1ou.5.1.land/README.md) | sase-1ou hood | completed |
| [sase-1ou.6.1](../bbugyi200.athena.sase-1ou.6.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.6.land](../../sessions/bbugyi200.athena.sase-1ou.6.land.md) (session · 2) | sase-1ou hood | active 1, completed 1 |
| [sase-1ou.land](../../sessions/bbugyi200.athena.sase-1ou.land.md) (session · 3) | sase-1ou hood | failed 3 |
