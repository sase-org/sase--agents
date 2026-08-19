# Family: 084

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [084](../users/bbugyi200/machines/athena/hoods/084/README.md) / 084

Owner: `bbugyi200.athena` · Hood: `084` · Members: 4

## Lineage

```mermaid
flowchart TD
  n0["084--mon [failed]"]
  n1["084--1 [completed]"]
  n0 --> n1
  n2["084--plan [completed]"]
  n0 --> n2
  n3["084--code [completed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | 084--mon | failed | grok-4.6 / grok | 2026-08-19T21:15:35.134995+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.084--mon/chat.md) |
| <a id="member-1"></a>1 | 084--1 | completed | grok-4.6 / grok | 2026-08-19T21:20:21.441193+00:00 | [1](../agents/bbugyi200.athena.084--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.084--1/prompt.md) | [Chat](../agents/bbugyi200.athena.084--1/chat.md) |
| <a id="member-plan"></a>plan | 084--plan | completed | grok-4.6 / grok | 2026-08-19T19:49:04.731114+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.084--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.084--plan/chat.md) |
| <a id="member-code"></a>code | 084--code | completed | grok-4.6 / grok | 2026-08-19T20:16:57.026450+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.084--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`e0644ef`](https://github.com/sase-org/sase/commit/e0644efad3b457e2a2196c89ef0c19f067e6bdfe) | chore: Add SDD prompt and plan for jinja\_diagnostics\_known\_vars | 2026-06-27 11:43:03 EDT |
| — | sase | [`9eb77c1`](https://github.com/sase-org/sase/commit/9eb77c1dd4683024e9dffb765989ad4dcaeba080) | fix: recognize prompt jinja runtime variables | 2026-06-27 11:50:40 EDT |
| 1 | sase | [`ae87b18`](https://github.com/sase-org/sase/commit/ae87b1849141374e755429ca46ae9467cc936841) | fix(llm): auto-disable Claude on weekly-limit errors | 2026-08-19 17:35:37 EDT |
