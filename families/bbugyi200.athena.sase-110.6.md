# Family: sase-110.6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-110](../users/bbugyi200/machines/athena/hoods/sase-110/README.md) / sase-110.6

Owner: `bbugyi200.athena` · Hood: `sase-110` · Members: 3 · Bead: [sase-110.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-110/sase-110.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-110.6--plan [active]"]
  n1["sase-110.6--code [completed]"]
  n0 --> n1
  n2["sase-110.6--gate [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-110.6--plan | active | gpt-5.6-sol / codex | 2026-09-15T11:52:59.240774+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-110.6--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-110.6--plan/chat.md) |
| <a id="member-code"></a>code | sase-110.6--code | completed | gpt-5.5 / codex | 2026-09-15T12:06:47.755433+00:00 → 2026-09-15T13:38:23.731602+00:00 | [1](../agents/bbugyi200.athena.sase-110.6--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-110.6--code/chat.md) |
| <a id="member-gate"></a>gate | sase-110.6--gate | active | gpt-5.6-sol / codex | 2026-09-15T12:06:14.324648+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-110.6--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`7a1a1ca`](https://github.com/sase-org/sase/commit/7a1a1ca3e46554fd99035617484773af8b57cf6e) | feat(sudo): support remote sudo handoff over ssh | 2026-09-15 09:33:47 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-110.1](bbugyi200.athena.sase-110.1.md) (family · 3) | sase-110 hood | active 2, completed 1 |
| [sase-110.2](bbugyi200.athena.sase-110.2.md) (family · 3) | sase-110 hood | active 2, completed 1 |
| [sase-110.3](../agents/bbugyi200.athena.sase-110.3/README.md) | sase-110 hood | active |
| [sase-110.4](bbugyi200.athena.sase-110.4.md) (family · 3) | sase-110 hood | active 2, completed 1 |
| [sase-110.5](../agents/bbugyi200.athena.sase-110.5/README.md) | sase-110 hood | active |
| [sase-110.7](bbugyi200.athena.sase-110.7.md) (family · 2) | sase-110 hood | active 2 |
| [sase-110.8](../agents/bbugyi200.athena.sase-110.8/README.md) | sase-110 hood | waiting |
| [sase-110.land](../agents/bbugyi200.athena.sase-110.land/README.md) | sase-110 hood | waiting |
