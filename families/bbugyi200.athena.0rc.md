# Family: 0rc

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0rc](../users/bbugyi200/machines/athena/hoods/0rc/README.md) / 0rc

Owner: `bbugyi200.athena` · Hood: `0rc` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0rc--plan [active]"]
  n1["0rc--gate [failed]"]
  n0 --> n1
  n2["0rc--code [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 0rc--plan | active | opus / claude | 2026-09-24T20:08:52.941223+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0rc--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0rc--plan/chat.md) |
| <a id="member-gate"></a>gate | 0rc--gate | failed | opus / claude | 2026-09-24T20:13:04.596565+00:00 → 2026-09-24T20:13:23.958460+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0rc--gate/chat.md) |
| <a id="member-code"></a>code | 0rc--code | completed | sonnet / claude | 2026-09-24T20:13:37.008507+00:00 → 2026-09-24T20:21:06.736495+00:00 | [1](../agents/bbugyi200.athena.0rc--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.0rc--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`740c08f`](https://github.com/sase-org/sase/commit/740c08f6183175ec46b6d2fdbfbfe229ae16f22a) | feat(ace): open effort completion on @ after %m:\<model\> space | 2026-09-24 16:19:55 EDT |
