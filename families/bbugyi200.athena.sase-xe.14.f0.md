# Family: sase-xe.14.f0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-xe](../users/bbugyi200/machines/athena/hoods/sase-xe/README.md) / sase-xe.14.f0

Owner: `bbugyi200.athena` · Hood: `sase-xe` · Members: 5

## Lineage

```mermaid
flowchart TD
  n0["sase-xe.14.f0--gate [failed]"]
  n1["sase-xe.14.f0--plan [dismissed]"]
  n0 --> n1
  n2["sase-xe.14.f0--1 [failed]"]
  n0 --> n2
  n3["sase-xe.14.f0--code [completed]"]
  n0 --> n3
  n4["sase-xe.14.f0--mon [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | sase-xe.14.f0--gate | failed | opus / claude | 2026-09-07T15:43:18.774394+00:00 → 2026-09-07T15:44:55.419862+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-xe.14.f0--gate/chat.md) |
| <a id="member-plan"></a>plan | sase-xe.14.f0--plan | dismissed | opus / claude | 2026-09-07T11:34:13.947537 → 2026-09-07T11:43:26.970589 | 0 | [Prompt](../agents/bbugyi200.athena.sase-xe.14.f0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-xe.14.f0--plan/chat.md) |
| <a id="member-1"></a>1 | sase-xe.14.f0--1 | failed | gpt-5 / codex | 2026-09-07T18:20:05.073394+00:00 → 2026-09-07T18:20:22.273326+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-xe.14.f0--1/prompt.md) | — |
| <a id="member-code"></a>code | sase-xe.14.f0--code | completed | gpt-5.5 / codex | 2026-09-07T15:45:02.831095+00:00 → 2026-09-07T17:17:22.416175+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-xe.14.f0--code/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-xe.14.f0--code/chat.md) |
| <a id="member-mon"></a>mon | sase-xe.14.f0--mon | failed | gpt-5.5 / codex | 2026-09-07T17:16:52.509935+00:00 → 2026-09-07T18:19:32.197407+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-xe.14.f0--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-xe.14](bbugyi200.athena.sase-xe.14.md) (family · 3) | ancestor | completed 2, failed 1 |
| [sase-xe.1](../agents/bbugyi200.athena.sase-xe.1/README.md) | sase-xe hood | active |
| [sase-xe.10](bbugyi200.athena.sase-xe.10.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.10](../agents/bbugyi200.athena.sase-xe.10/README.md) | sase-xe hood | waiting |
| [sase-xe.11](bbugyi200.athena.sase-xe.11.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.12](bbugyi200.athena.sase-xe.12.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.13](bbugyi200.athena.sase-xe.13.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.13](../agents/bbugyi200.athena.sase-xe.13/README.md) | sase-xe hood | waiting |
| [sase-xe.15](bbugyi200.athena.sase-xe.15.md) (family · 6) | sase-xe hood | active 1, completed 2, dismissed 1, failed 2 |
| [sase-xe.15](../agents/bbugyi200.athena.sase-xe.15/README.md) | sase-xe hood | waiting |
| [sase-xe.16.1](bbugyi200.athena.sase-xe.16.1.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.16.10](bbugyi200.athena.sase-xe.16.10.md) (family · 5) | sase-xe hood | active 1, completed 2, failed 2 |
| [sase-xe.16.11.1](../agents/bbugyi200.athena.sase-xe.16.11.1/README.md) | sase-xe hood | completed |
| [sase-xe.16.11.2](../agents/bbugyi200.athena.sase-xe.16.11.2/README.md) | sase-xe hood | active |
| [sase-xe.16.11.3](../agents/bbugyi200.athena.sase-xe.16.11.3/README.md) | sase-xe hood | waiting |
| [sase-xe.16.11.4](../agents/bbugyi200.athena.sase-xe.16.11.4/README.md) | sase-xe hood | waiting |
| [sase-xe.16.11.5](../agents/bbugyi200.athena.sase-xe.16.11.5/README.md) | sase-xe hood | waiting |
| [sase-xe.16.11.land](../agents/bbugyi200.athena.sase-xe.16.11.land/README.md) | sase-xe hood | waiting |
| [sase-xe.16.2](../agents/bbugyi200.athena.sase-xe.16.2/README.md) | sase-xe hood | completed |
| [sase-xe.16.3](../agents/bbugyi200.athena.sase-xe.16.3/README.md) | sase-xe hood | completed |
| [sase-xe.16.4](../agents/bbugyi200.athena.sase-xe.16.4/README.md) | sase-xe hood | completed |
| [sase-xe.16.5](../agents/bbugyi200.athena.sase-xe.16.5/README.md) | sase-xe hood | completed |
| [sase-xe.16.6](bbugyi200.athena.sase-xe.16.6.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.16.7](../agents/bbugyi200.athena.sase-xe.16.7/README.md) | sase-xe hood | completed |
| [sase-xe.16.8](../agents/bbugyi200.athena.sase-xe.16.8/README.md) | sase-xe hood | completed |
| [sase-xe.16.8.f0](bbugyi200.athena.sase-xe.16.8.f0.md) (family · 11) | sase-xe hood | completed 6, failed 5 |
| [sase-xe.16.9](bbugyi200.athena.sase-xe.16.9.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.16.land](bbugyi200.athena.sase-xe.16.land.md) (family · 5) | sase-xe hood | completed 2, failed 3 |
| [sase-xe.2](bbugyi200.athena.sase-xe.2.md) (family · 3) | sase-xe hood | active 1, dismissed 1, failed 1 |
| [sase-xe.3](../agents/bbugyi200.athena.sase-xe.3/README.md) | sase-xe hood | completed |
| [sase-xe.4](bbugyi200.athena.sase-xe.4.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.5](bbugyi200.athena.sase-xe.5.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.5](../agents/bbugyi200.athena.sase-xe.5/README.md) | sase-xe hood | waiting |
| [sase-xe.6](../agents/bbugyi200.athena.sase-xe.6/README.md) | sase-xe hood | dismissed |
| [sase-xe.7](bbugyi200.athena.sase-xe.7.md) (family · 3) | sase-xe hood | failed 3 |
| [sase-xe.7.f0](../agents/bbugyi200.athena.sase-xe.7.f0/README.md) | sase-xe hood | dismissed |
| [sase-xe.8](bbugyi200.athena.sase-xe.8.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.8](../agents/bbugyi200.athena.sase-xe.8/README.md) | sase-xe hood | waiting |
| [sase-xe.9](../agents/bbugyi200.athena.sase-xe.9/README.md) | sase-xe hood | completed |
| [sase-xe.land](bbugyi200.athena.sase-xe.land.md) (family · 3) | sase-xe hood | completed 2, failed 1 |
| [sase-xe.land](../agents/bbugyi200.athena.sase-xe.land/README.md) | sase-xe hood | waiting |
