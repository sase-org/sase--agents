# Family: toobig-53.test\_machine\_init.0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [toobig-53](../users/bbugyi200/machines/athena/hoods/toobig-53/README.md) / toobig-53.test\_machine\_init.0

Owner: `bbugyi200.athena` · Hood: `toobig-53` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["toobig-53.test_machine_init.0--1 [dismissed]"]
  n1["toobig-53.test_machine_init.0--mon [dismissed]"]
  n0 --> n1
  n2["toobig-53.test_machine_init.0--plan [dismissed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-1"></a>1 | toobig-53.test\_machine\_init.0--1 | dismissed | grok-4.6 / grok | 2026-09-10T06:44:11.096836 → 2026-09-10T06:48:08.193815 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-53.test_machine_init.0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-53.test_machine_init.0--1/chat.md) |
| <a id="member-mon"></a>mon | toobig-53.test\_machine\_init.0--mon | dismissed | grok-4.6 / grok | 2026-09-10T06:37:41.991739 → 2026-09-10T06:42:27.556028 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-53.test_machine_init.0--mon/chat.md) |
| <a id="member-plan"></a>plan | toobig-53.test\_machine\_init.0--plan | dismissed | grok-4.6 / grok | 2026-09-10T06:26:08.776329 → 2026-09-10T06:37:54.732987 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-53.test_machine_init.0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-53.test_machine_init.0--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`4c2a903`](https://github.com/sase-org/sase/commit/4c2a90304438883b6c29aae0cc0b43d949aa6ed3) | test(dispatch): split machine-init tests into focused modules | 2026-09-10 06:45:34 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [toobig-53.artifact\_link\_event\_publisher.0](bbugyi200.athena.toobig-53.artifact_link_event_publisher.0.md) (family · 5) | toobig-53 hood | dismissed 5 |
| [toobig-53.artifact\_link\_outbox.0](../agents/bbugyi200.athena.toobig-53.artifact_link_outbox.0/README.md) | toobig-53 hood | dismissed |
| [toobig-53.file\_completion\_accept.0](bbugyi200.athena.toobig-53.file_completion_accept.0.md) (family · 3) | toobig-53 hood | dismissed 3 |
| [toobig-53.test\_ace\_png\_snapshots\_model\_completion.0](../agents/bbugyi200.athena.toobig-53.test_ace_png_snapshots_model_completion.0/README.md) | toobig-53 hood | dismissed |
| [toobig-53.test\_checks\_providers.0](../agents/bbugyi200.athena.toobig-53.test_checks_providers.0/README.md) | toobig-53 hood | dismissed |
| [toobig-53.trail\_chrome.0](../agents/bbugyi200.athena.toobig-53.trail_chrome.0/README.md) | toobig-53 hood | dismissed |
