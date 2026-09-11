# Family: toobig-57.test\_provider\_usage\_indicator\_presentation.0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [toobig-57](../users/bbugyi200/machines/athena/hoods/toobig-57/README.md) / toobig-57.test\_provider\_usage\_indicator\_presentation.0

Owner: `bbugyi200.athena` · Hood: `toobig-57` · Members: 7

## Lineage

```mermaid
flowchart TD
  n0["toobig-57.test_provider_usage_indicator_presentation.0--3 [active]"]
  n1["toobig-57.test_provider_usage_indicator_presentation.0--mon-1 [failed]"]
  n0 --> n1
  n2["toobig-57.test_provider_usage_indicator_presentation.0--plan [completed]"]
  n0 --> n2
  n3["toobig-57.test_provider_usage_indicator_presentation.0--2 [completed]"]
  n0 --> n3
  n4["toobig-57.test_provider_usage_indicator_presentation.0--1 [completed]"]
  n0 --> n4
  n5["toobig-57.test_provider_usage_indicator_presentation.0--mon-0 [failed]"]
  n0 --> n5
  n6["toobig-57.test_provider_usage_indicator_presentation.0--mon [failed]"]
  n0 --> n6
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-3"></a>3 | toobig-57.test\_provider\_usage\_indicator\_presentation.0--3 | active | grok-4.6 / grok | 2026-09-11T18:05:23.757026+00:00 | [1](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--3/prompt.md) | — |
| <a id="member-mon-1"></a>mon-1 | toobig-57.test\_provider\_usage\_indicator\_presentation.0--mon-1 | failed | grok-4.6 / grok | 2026-09-11T18:01:52.962429+00:00 → 2026-09-11T18:05:10.662001+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--mon-1/chat.md) |
| <a id="member-plan"></a>plan | toobig-57.test\_provider\_usage\_indicator\_presentation.0--plan | completed | grok-4.6 / grok | 2026-09-11T17:15:48.875327+00:00 → 2026-09-11T17:22:57.280536+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--plan/chat.md) |
| <a id="member-2"></a>2 | toobig-57.test\_provider\_usage\_indicator\_presentation.0--2 | completed | grok-4.6 / grok | 2026-09-11T17:57:43.817891+00:00 → 2026-09-11T18:02:10.229073+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--2/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--2/chat.md) |
| <a id="member-1"></a>1 | toobig-57.test\_provider\_usage\_indicator\_presentation.0--1 | completed | grok-4.6 / grok | 2026-09-11T17:33:59.595538+00:00 → 2026-09-11T17:55:40.762978+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--1/prompt.md) | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--1/chat.md) |
| <a id="member-mon-0"></a>mon-0 | toobig-57.test\_provider\_usage\_indicator\_presentation.0--mon-0 | failed | grok-4.6 / grok | 2026-09-11T17:55:21.221656+00:00 → 2026-09-11T17:57:39.362514+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--mon-0/chat.md) |
| <a id="member-mon"></a>mon | toobig-57.test\_provider\_usage\_indicator\_presentation.0--mon | failed | grok-4.6 / grok | 2026-09-11T17:22:47.613440+00:00 → 2026-09-11T17:34:00.062179+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.toobig-57.test_provider_usage_indicator_presentation.0--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`1218967`](https://github.com/sase-org/sase/commit/121896776f4b53b8798d9cb2342cc3e74866a17b) | test: split provider-usage indicator presentation tests | 2026-09-11 14:15:00 EDT |
