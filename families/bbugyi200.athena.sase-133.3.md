# Family: sase-133.3

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-133](../users/bbugyi200/machines/athena/hoods/sase-133/README.md) / sase-133.3

Owner: `bbugyi200.athena` · Hood: `sase-133` · Members: 3 · Bead: [sase-133.3](https://github.com/sase-org/sase--beads/blob/main/pages/sase-133/sase-133.3.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-133.3--code [completed]"]
  n1["sase-133.3--plan [active]"]
  n0 --> n1
  n2["sase-133.3--gate [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-133.3--code | completed | grok-4.6 / grok | 2026-09-19T00:23:02.186537+00:00 → 2026-09-19T01:39:44.177852+00:00 | [1](../agents/bbugyi200.athena.sase-133.3--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-133.3--code/chat.md) |
| <a id="member-plan"></a>plan | sase-133.3--plan | active | gpt-5.6-sol / codex | 2026-09-19T00:15:28.571108+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-133.3--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-133.3--plan/chat.md) |
| <a id="member-gate"></a>gate | sase-133.3--gate | active | gpt-5.6-sol / codex | 2026-09-19T00:21:52.984033+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-133.3--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`2ec00fe`](https://github.com/sase-org/sase/commit/2ec00fe68360d40767990d563b9c432a42acf921) | feat(tui): render remote fleet rows with local Agents-tab parity | 2026-09-18 21:36:20 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-133.1](bbugyi200.athena.sase-133.1.md) (family · 3) | sase-133 hood | active 2, completed 1 |
| [sase-133.2](bbugyi200.athena.sase-133.2.md) (family · 3) | sase-133 hood | active 2, completed 1 |
| [sase-133.4](../agents/bbugyi200.athena.sase-133.4/README.md) | sase-133 hood | active |
| [sase-133.5.1](bbugyi200.athena.sase-133.5.1.md) (family · 3) | sase-133 hood | active 2, failed 1 |
| [sase-133.5.2](../agents/bbugyi200.athena.sase-133.5.2/README.md) | sase-133 hood | waiting |
| [sase-133.5.3](bbugyi200.athena.sase-133.5.3.md) (family · 3) | sase-133 hood | completed 1, failed 1, waiting 1 |
| [sase-133.5.4](../agents/bbugyi200.athena.sase-133.5.4/README.md) | sase-133 hood | waiting |
| [sase-133.5.land](../agents/bbugyi200.athena.sase-133.5.land/README.md) | sase-133 hood | waiting |
| [sase-133.land](bbugyi200.athena.sase-133.land.md) (family · 3) | sase-133 hood | active 3 |
| [sase-133.land](../agents/bbugyi200.athena.sase-133.land/README.md) | sase-133 hood | waiting |
