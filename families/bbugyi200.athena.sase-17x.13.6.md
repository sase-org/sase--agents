# Family: sase-17x.13.6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-17x](../users/bbugyi200/machines/athena/hoods/sase-17x/README.md) / sase-17x.13.6

Owner: `bbugyi200.athena` · Hood: `sase-17x` · Members: 5 · Bead: [sase-17x.13.6](https://github.com/sase-org/sase--beads/blob/main/pages/sase-17x/sase-17x.13.6.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-17x.13.6--mon-0 [failed]"]
  n1["sase-17x.13.6--2 [completed]"]
  n0 --> n1
  n2["sase-17x.13.6--plan [completed]"]
  n0 --> n2
  n3["sase-17x.13.6--mon [failed]"]
  n0 --> n3
  n4["sase-17x.13.6--1 [completed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-17x.13.6--mon-0 | failed | gpt-5.6-terra / codex | 2026-09-25T04:43:11.988162+00:00 → 2026-09-25T04:45:38.322285+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-17x.13.6--mon-0/chat.md) |
| <a id="member-2"></a>2 | sase-17x.13.6--2 | completed | gpt-5.6-terra / codex | 2026-09-25T04:45:56.382804+00:00 → 2026-09-25T04:54:01.805692+00:00 | [1](../agents/bbugyi200.athena.sase-17x.13.6--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-17x.13.6--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17x.13.6--2/chat.md) |
| <a id="member-plan"></a>plan | sase-17x.13.6--plan | completed | gpt-5.6-terra / codex | 2026-09-25T04:24:42.811194+00:00 → 2026-09-25T04:38:01.024842+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-17x.13.6--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17x.13.6--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-17x.13.6--mon | failed | gpt-5.6-terra / codex | 2026-09-25T04:37:24.927512+00:00 → 2026-09-25T04:39:45.595292+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-17x.13.6--mon/chat.md) |
| <a id="member-1"></a>1 | sase-17x.13.6--1 | completed | gpt-5.6-terra / codex | 2026-09-25T04:40:02.790887+00:00 → 2026-09-25T04:43:33.081694+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-17x.13.6--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-17x.13.6--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`fad9b5d`](https://github.com/sase-org/sase/commit/fad9b5d03db1b2812dcd10576d1eeefe4aec3de4) | feat(command-line): add dynamic completion sources | 2026-09-25 00:48:31 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-17x.13.1](../agents/bbugyi200.athena.sase-17x.13.1/README.md) | sase-17x.13 hood | active |
| [sase-17x.13.10.1](bbugyi200.athena.sase-17x.13.10.1.md) (family · 3) | sase-17x.13 hood | completed 2, failed 1 |
| [sase-17x.13.10.2](bbugyi200.athena.sase-17x.13.10.2.md) (family · 3) | sase-17x.13 hood | completed 2, failed 1 |
| [sase-17x.13.10.3](../agents/bbugyi200.athena.sase-17x.13.10.3/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.10.4](../agents/bbugyi200.athena.sase-17x.13.10.4/README.md) | sase-17x.13 hood | active |
| [sase-17x.13.10.5](bbugyi200.athena.sase-17x.13.10.5.md) (family · 3) | sase-17x.13 hood | completed 2, failed 1 |
| [sase-17x.13.10.6](../agents/bbugyi200.athena.sase-17x.13.10.6/README.md) | sase-17x.13 hood | waiting |
| [sase-17x.13.10.land](../agents/bbugyi200.athena.sase-17x.13.10.land/README.md) | sase-17x.13 hood | waiting |
| [sase-17x.13.2](../agents/bbugyi200.athena.sase-17x.13.2/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.3](bbugyi200.athena.sase-17x.13.3.md) (family · 5) | sase-17x.13 hood | completed 3, failed 2 |
| [sase-17x.13.4](../agents/bbugyi200.athena.sase-17x.13.4/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.5](../agents/bbugyi200.athena.sase-17x.13.5/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.7](../agents/bbugyi200.athena.sase-17x.13.7/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.8](../agents/bbugyi200.athena.sase-17x.13.8/README.md) | sase-17x.13 hood | completed |
| [sase-17x.13.9](bbugyi200.athena.sase-17x.13.9.md) (family · 15) | sase-17x.13 hood | completed 8, failed 7 |
| [sase-17x.13.land](bbugyi200.athena.sase-17x.13.land.md) (family · 3) | sase-17x.13 hood | failed 3 |
| [sase-17x.1](../agents/bbugyi200.athena.sase-17x.1/README.md) | sase-17x hood | active |
| [sase-17x.10](bbugyi200.athena.sase-17x.10.md) (family · 3) | sase-17x hood | active 3 |
| [sase-17x.11](../agents/bbugyi200.athena.sase-17x.11/README.md) | sase-17x hood | active |
| [sase-17x.12](../agents/bbugyi200.athena.sase-17x.12/README.md) | sase-17x hood | active |
| [sase-17x.2](../agents/bbugyi200.athena.sase-17x.2/README.md) | sase-17x hood | active |
| [sase-17x.3](../agents/bbugyi200.athena.sase-17x.3/README.md) | sase-17x hood | active |
| [sase-17x.4](../agents/bbugyi200.athena.sase-17x.4/README.md) | sase-17x hood | active |
| [sase-17x.5](bbugyi200.athena.sase-17x.5.md) (family · 3) | sase-17x hood | active 2, completed 1 |
| [sase-17x.6](../agents/bbugyi200.athena.sase-17x.6/README.md) | sase-17x hood | active |
| [sase-17x.7](../agents/bbugyi200.athena.sase-17x.7/README.md) | sase-17x hood | active |
| [sase-17x.8](../agents/bbugyi200.athena.sase-17x.8/README.md) | sase-17x hood | active |
| [sase-17x.9](../agents/bbugyi200.athena.sase-17x.9/README.md) | sase-17x hood | active |
| [sase-17x.land](bbugyi200.athena.sase-17x.land.md) (family · 3) | sase-17x hood | active 3 |
