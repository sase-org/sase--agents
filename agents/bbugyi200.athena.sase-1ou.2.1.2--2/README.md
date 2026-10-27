# Agent: sase-1ou.2.1.2--2

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [sase-1ou](../../users/bbugyi200/machines/athena/hoods/sase-1ou/README.md) / [sase-1ou.2.1.2](../../sessions/bbugyi200.athena.sase-1ou.2.1.2.md) / sase-1ou.2.1.2--2

**Global name:** `bbugyi200.athena.sase-1ou.2.1.2--2` · **State:** completed · **Source run:** `run-ca613dda99d9179b932cfe40ab856cb1`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** sase-1ou

## Summary

- Bead: [sase-1ou.2.1.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ou/sase-1ou.2.1.2.md)
- Model: gpt-6-astra
- Provider: codex
- Timing: 2026-10-27T19:33:05.138708+00:00 → 2026-10-27T20:25:22.908890+00:00
- Commits: 0
- Variables: [1](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Variables

| Variable | Value |
|---|---|
| `artifacts` | \[{bead: sase-1ou.2.1.2, kind: file, label: ToolRun contention completed verification bundle, path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261027153040/evidence-bundle-511072056f0d.jso… |

#### artifacts

```yaml
- bead: sase-1ou.2.1.2
  kind: file
  label: ToolRun contention completed verification bundle
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261027153040/evidence-bundle-511072056f0d.json
  ref: file:explicit:b13e06f116130351ef4438d2
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.sase/toolrun-contention/evidence-bundle.json
- bead: sase-1ou.2.1.2
  kind: file
  label: Corrected WAL probe deadline measurements
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261027153040/controlled-audit-corrected-362ebcb0f967.json
  ref: file:explicit:c8e2e1dd2954f633e244ccb6
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.sase/toolrun-contention/controlled-audit-corrected.json
```

Values are truncated for display; see [meta.json](meta.json) for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1ou.2](../../sessions/bbugyi200.athena.sase-1ou.2.md) (session · 3) | ancestor | failed 3 |
| [sase-1ou.2.1.1](../bbugyi200.athena.sase-1ou.2.1.1/README.md) | sase-1ou.2.1 hood | completed |
| [sase-1ou.2.1.land](../../sessions/bbugyi200.athena.sase-1ou.2.1.land.md) (session · 3) | sase-1ou.2.1 hood | active 1, completed 1, failed 1 |
| [sase-1ou.1](../bbugyi200.athena.sase-1ou.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.3](../../sessions/bbugyi200.athena.sase-1ou.3.md) (session · 7) | sase-1ou hood | completed 4, failed 3 |
| [sase-1ou.4](../../sessions/bbugyi200.athena.sase-1ou.4.md) (session · 5) | sase-1ou hood | completed 3, failed 2 |
| [sase-1ou.5](../../sessions/bbugyi200.athena.sase-1ou.5.md) (session · 3) | sase-1ou hood | failed 3 |
| [sase-1ou.5.1.1](../bbugyi200.athena.sase-1ou.5.1.1/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.2](../bbugyi200.athena.sase-1ou.5.1.2/README.md) | sase-1ou hood | completed |
| [sase-1ou.5.1.3](../../sessions/bbugyi200.athena.sase-1ou.5.1.3.md) (session · 3) | sase-1ou hood | completed 2, failed 1 |
| [sase-1ou.5.1.4](../../sessions/bbugyi200.athena.sase-1ou.5.1.4.md) (session · 2) | sase-1ou hood | active 1, completed 1 |
| [sase-1ou.5.1.land](../bbugyi200.athena.sase-1ou.5.1.land/README.md) | sase-1ou hood | waiting |
| [sase-1ou.land](../bbugyi200.athena.sase-1ou.land/README.md) | sase-1ou hood | waiting |
