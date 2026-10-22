# Agent: sase-1n6.5.1.5.2.1.2--1

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [sase-1n6](../../users/bbugyi200/machines/athena/hoods/sase-1n6/README.md) / [sase-1n6.5.1.5.2.1.2](../../sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.2.md) / sase-1n6.5.1.5.2.1.2--1

**Global name:** `bbugyi200.athena.sase-1n6.5.1.5.2.1.2--1` · **State:** completed · **Source run:** `run-71375e30662c1049634754064dc64063`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** sase-1n6

## Summary

- Bead: [sase-1n6.5.1.5.2.1.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1n6/sase-1n6.5.1.5.2.1.2.md)
- Model: gpt-6-luna
- Provider: codex
- Timing: 2026-10-20T21:02:39.550743+00:00 → 2026-10-20T21:21:42.956571+00:00
- Commits: 0
- Variables: [1](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Variables

| Variable | Value |
|---|---|
| `artifacts` | \[{bead: sase-1n6.5.1.5.2.1.2, kind: file, label: Green rehearsal 39495874381 run metadata, path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261020170011/39495874381-api-d5fec920aaa0.json,… |

#### artifacts

```yaml
- bead: sase-1n6.5.1.5.2.1.2
  kind: file
  label: Green rehearsal 39495874381 run metadata
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261020170011/39495874381-api-d5fec920aaa0.json
  ref: file:explicit:50fd3359e020644fc0d1bc88
  source_path: /tmp/sase-live-proof-4adee846/39495874381-api.json
- bead: sase-1n6.5.1.5.2.1.2
  kind: markdown
  label: Acceptance mapping for compared SHA 4adee846
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261020170011/sase-live-proof-4adee846-acceptance-d95df327df45.md
  ref: file:explicit:f27fe0e4e8e21041282b6bfd
  source_path: /tmp/sase-live-proof-4adee846-acceptance.md
- bead: sase-1n6.5.1.5.2.1.2
  kind: file
  label: Run logs and core containment evidence for SHA 4adee846
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261020170011/sase-live-proof-4adee846-evidence.tar-4a2627e11649.gz
  ref: file:explicit:79476a9749f868b5d7c7f2d4
  source_path: /tmp/sase-live-proof-4adee846-evidence.tar.gz
```

Values are truncated for display; see [meta.json](meta.json) for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-1n6.5.1.5.2](../bbugyi200.athena.sase-1n6.5.1.5.2/README.md) | ancestor | completed |
| [sase-1n6.5](../../sessions/bbugyi200.athena.sase-1n6.5.md) (session · 3) | ancestor | failed 3 |
| [sase-1n6.5.1.5.2.1.1](../../sessions/bbugyi200.athena.sase-1n6.5.1.5.2.1.1.md) (session · 3) | sase-1n6.5.1.5.2.1 hood | completed 2, failed 1 |
| [sase-1n6.5.1.5.2.1.land](../bbugyi200.athena.sase-1n6.5.1.5.2.1.land/README.md) | sase-1n6.5.1.5.2.1 hood | waiting |
| [sase-1n6.5.1.5.1](../bbugyi200.athena.sase-1n6.5.1.5.1/README.md) | sase-1n6.5.1.5 hood | completed |
| [sase-1n6.5.1.5.land](../bbugyi200.athena.sase-1n6.5.1.5.land/README.md) | sase-1n6.5.1.5 hood | waiting |
| [sase-1n6.5.1.1](../bbugyi200.athena.sase-1n6.5.1.1/README.md) | sase-1n6.5.1 hood | active |
| [sase-1n6.5.1.2](../../sessions/bbugyi200.athena.sase-1n6.5.1.2.md) (session · 5) | sase-1n6.5.1 hood | active 5 |
| [sase-1n6.5.1.3](../bbugyi200.athena.sase-1n6.5.1.3/README.md) | sase-1n6.5.1 hood | active |
| [sase-1n6.5.1.4](../bbugyi200.athena.sase-1n6.5.1.4/README.md) | sase-1n6.5.1 hood | active |
| [sase-1n6.5.1.land](../../sessions/bbugyi200.athena.sase-1n6.5.1.land.md) (session · 3) | sase-1n6.5.1 hood | active 3 |
| [sase-1n6.1](../bbugyi200.athena.sase-1n6.1/README.md) | sase-1n6 hood | completed |
| [sase-1n6.10](../bbugyi200.athena.sase-1n6.10/README.md) | sase-1n6 hood | waiting |
| [sase-1n6.2](../bbugyi200.athena.sase-1n6.2/README.md) | sase-1n6 hood | completed |
| [sase-1n6.3](../bbugyi200.athena.sase-1n6.3/README.md) | sase-1n6 hood | completed |
| [sase-1n6.4](../../sessions/bbugyi200.athena.sase-1n6.4.md) (session · 3) | sase-1n6 hood | completed 2, failed 1 |
| [sase-1n6.6](../bbugyi200.athena.sase-1n6.6/README.md) | sase-1n6 hood | waiting |
| [sase-1n6.7](../../sessions/bbugyi200.athena.sase-1n6.7.md) (session · 3) | sase-1n6 hood | failed 3 |
| [sase-1n6.7.1.1](../bbugyi200.athena.sase-1n6.7.1.1/README.md) | sase-1n6 hood | active |
| [sase-1n6.7.1.2](../../sessions/bbugyi200.athena.sase-1n6.7.1.2.md) (session · 5) | sase-1n6 hood | active 5 |
| [sase-1n6.7.1.3](../bbugyi200.athena.sase-1n6.7.1.3/README.md) | sase-1n6 hood | active |
| [sase-1n6.7.1.4](../../sessions/bbugyi200.athena.sase-1n6.7.1.4.md) (session · 3) | sase-1n6 hood | active 3 |
| [sase-1n6.7.1.5](../../sessions/bbugyi200.athena.sase-1n6.7.1.5.md) (session · 3) | sase-1n6 hood | active 3 |
| [sase-1n6.7.1.land](../../sessions/bbugyi200.athena.sase-1n6.7.1.land.md) (session · 15) | sase-1n6 hood | active 13, completed 1, failed 1 |
| [sase-1n6.8](../bbugyi200.athena.sase-1n6.8/README.md) | sase-1n6 hood | completed |
| [sase-1n6.9](../bbugyi200.athena.sase-1n6.9/README.md) | sase-1n6 hood | waiting |
| [sase-1n6.land](../bbugyi200.athena.sase-1n6.land/README.md) | sase-1n6 hood | waiting |
