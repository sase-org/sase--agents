# Family: sase-vk.3

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-vk](../users/bbugyi200/machines/athena/hoods/sase-vk/README.md) / sase-vk.3

Owner: `bbugyi200.athena` · Hood: `sase-vk` · Members: 3 · Bead: [sase-vk.3](https://github.com/sase-org/sase--beads/blob/main/pages/sase-vk/sase-vk.3.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-vk.3--plan [completed]"]
  n1["sase-vk.3--mon [failed]"]
  n0 --> n1
  n2["sase-vk.3--1 [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-vk.3--plan | completed | sonnet / claude | 2026-08-30T09:55:29.028699+00:00 → 2026-08-30T10:32:31.565041+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-vk.3--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-vk.3--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-vk.3--mon | failed | sonnet / claude | 2026-08-30T10:32:22.140612+00:00 → 2026-08-30T10:50:19.278031+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-vk.3--mon/chat.md) |
| <a id="member-1"></a>1 | sase-vk.3--1 | active | sonnet / claude | 2026-08-30T10:50:54.641313+00:00 | [1](../agents/bbugyi200.athena.sase-vk.3--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-vk.3--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`0860fcb`](https://github.com/sase-org/sase/commit/0860fcb200f35e3ec99cdd50cc9f54ad82ea857b) | docs(memory): rewrite Tier-1/Tier-2 memory vocabulary across docs and templates | 2026-08-30 06:52:22 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-vk.1](../agents/bbugyi200.athena.sase-vk.1/README.md) | sase-vk hood | dismissed |
| [sase-vk.2](../agents/bbugyi200.athena.sase-vk.2/README.md) | sase-vk hood | active |
| [sase-vk.land](../agents/bbugyi200.athena.sase-vk.land/README.md) | sase-vk hood | waiting |
| [sase-vk.land.w0](../agents/bbugyi200.athena.sase-vk.land.w0/README.md) | sase-vk hood | waiting |
| [sase-vk.land.w1](../agents/bbugyi200.athena.sase-vk.land.w1/README.md) | sase-vk hood | waiting |
