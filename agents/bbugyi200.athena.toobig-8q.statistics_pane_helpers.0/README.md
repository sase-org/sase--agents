# Agent: toobig-8q.statistics\_pane\_helpers.0

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [toobig-8q](../../users/bbugyi200/machines/athena/hoods/toobig-8q/README.md) / toobig-8q.statistics\_pane\_helpers.0

**Global name:** `bbugyi200.athena.toobig-8q.statistics_pane_helpers.0` · **State:** completed · **Source run:** `run-6e6b027191d2306f5a7729d582780025`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** toobig-8q

## Summary

- Model: gpt-6-luna
- Provider: codex
- Timing: 2026-10-28T15:09:58.200617+00:00 → 2026-10-28T15:53:00.985413+00:00
- Commits: [1](#commits)
- Variables: [1](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Commits

| Repo | Commit | Subject | Committed |
|---|---|---|---|
| sase | [`2606ec6`](https://github.com/sase-org/sase/commit/2606ec67adee434a7f627e47f3c7171a2ace91fc) | refactor(tests): split Statistics pane helper fixtures | 2026-10-28 11:48:58 EDT |

## Variables

| Variable | Value |
|---|---|
| `artifacts` | \[{bead: sase-sk, kind: file, label: Oversized reset replay test file reported by toobig, path: /home/bryan/.sase/artifacts/agents/gh\_sase-org\_\_sase/20261028070158/test\_reset\_replay-64529345ef4a.py, r… |

#### artifacts

```yaml
- bead: sase-sk
  kind: file
  label: Oversized reset replay test file reported by toobig
  path: /home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261028070158/test_reset_replay-64529345ef4a.py
  ref: file:explicit:c061ba0b35bc68781b2fd78b
  source_path: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/test_reset_replay.py
```

Values are truncated for display; see [meta.json](meta.json) for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [toobig-8q.artifact\_link\_event\_publish.0](../bbugyi200.athena.toobig-8q.artifact_link_event_publish.0/README.md) | toobig-8q hood | completed |
| [toobig-8q.entry.0](../bbugyi200.athena.toobig-8q.entry.0/README.md) | toobig-8q hood | completed |
| [toobig-8q.snapshot\_capture.0](../bbugyi200.athena.toobig-8q.snapshot_capture.0/README.md) | toobig-8q hood | completed |
| [toobig-8q.statistics\_pane.0](../bbugyi200.athena.toobig-8q.statistics_pane.0/README.md) | toobig-8q hood | completed |
| [toobig-8q.statistics\_pane\_actions.0](../../sessions/bbugyi200.athena.toobig-8q.statistics_pane_actions.0.md) (session · 3) | toobig-8q hood | completed 2, failed 1 |
| [toobig-8q.test\_ace\_png\_snapshots\_config\_center\_statistics.0](../bbugyi200.athena.toobig-8q.test_ace_png_snapshots_config_center_statistics.0/README.md) | toobig-8q hood | active |
| [toobig-8q.test\_artifact\_link\_quarantine\_replay\_evidence.0](../bbugyi200.athena.toobig-8q.test_artifact_link_quarantine_replay_evidence.0/README.md) | toobig-8q hood | waiting |
| [toobig-8q.test\_axe\_runner\_workspace\_reclone.0](../bbugyi200.athena.toobig-8q.test_axe_runner_workspace_reclone.0/README.md) | toobig-8q hood | waiting |
| [toobig-8q.test\_reset\_replay.0](../bbugyi200.athena.toobig-8q.test_reset_replay.0/README.md) | toobig-8q hood | waiting |
