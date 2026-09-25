# Family: sase-13i.4.f0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-13i](../users/bbugyi200/machines/athena/hoods/sase-13i/README.md) / sase-13i.4.f0

Owner: `bbugyi200.athena` · Hood: `sase-13i` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["sase-13i.4.f0--plan [active]"]
  n1["sase-13i.4.f0--gate [failed]"]
  n0 --> n1
  n2["sase-13i.4.f0--code [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-13i.4.f0--plan | active | opus / claude | 2026-09-20T11:40:14.639472+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-13i.4.f0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-13i.4.f0--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-13i.4.f0--gate | failed | opus / claude | 2026-09-20T11:54:50.643865+00:00 → 2026-09-20T11:56:07.603721+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-13i.4.f0--gate/chat.md) |
| <a id="member-code"></a>code | sase-13i.4.f0--code | completed | sonnet / claude | 2026-09-20T11:56:31.275181+00:00 → 2026-09-20T15:56:58.016741+00:00 | [1](../agents/bbugyi200.athena.sase-13i.4.f0--code/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-13i.4.f0--code/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-13i.4.f0--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`a8869ac`](https://github.com/sase-org/sase/commit/a8869ac679d958628f874cd16249cb34f3b7b7c0) | fix(tui): keep collapsed-clan tribe panels and fleet rows across Agents-tab applies | 2026-09-20 11:53:35 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-13i.4](../agents/bbugyi200.athena.sase-13i.4/README.md) | ancestor | active |
| [sase-13i.4.f0.f0](bbugyi200.athena.sase-13i.4.f0.f0.md) (family · 3) | descendant | active 1, failed 2 |
| [sase-13i.1](../agents/bbugyi200.athena.sase-13i.1/README.md) | sase-13i hood | active |
| [sase-13i.2](../agents/bbugyi200.athena.sase-13i.2/README.md) | sase-13i hood | active |
| [sase-13i.3](../agents/bbugyi200.athena.sase-13i.3/README.md) | sase-13i hood | active |
| [sase-13i.land](../agents/bbugyi200.athena.sase-13i.land/README.md) | sase-13i hood | active |
