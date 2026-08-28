# Family: sase-ud.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ud](../users/bbugyi200/machines/athena/hoods/sase-ud/README.md) / sase-ud.2

Owner: `bbugyi200.athena` · Hood: `sase-ud` · Members: 6 · Bead: [sase-ud.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ud/sase-ud.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ud.2--mon-0 [failed]"]
  n1["sase-ud.2--plan [completed]"]
  n0 --> n1
  n2["sase-ud.2--mon [failed]"]
  n0 --> n2
  n3["sase-ud.2--2 [completed]"]
  n0 --> n3
  n4["sase-ud.2--1 [completed]"]
  n0 --> n4
  n5["sase-ud.2--code [completed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-ud.2--mon-0 | failed | gpt-5.5 / codex | 2026-08-26T19:29:20.124343+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ud.2--mon-0/chat.md) |
| <a id="member-plan"></a>plan | sase-ud.2--plan | completed | gpt-5.6-sol / codex | 2026-08-26T18:05:14.540945+00:00 → 2026-08-26T18:53:48.340416+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.2--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-ud.2--mon | failed | gpt-5.5 / codex | 2026-08-26T18:53:40.737748+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ud.2--mon/chat.md) |
| <a id="member-2"></a>2 | sase-ud.2--2 | completed | gpt-5.5 / codex | 2026-08-26T19:51:13.791819+00:00 → 2026-08-26T19:56:19.140825+00:00 | [1](../agents/bbugyi200.athena.sase-ud.2--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-ud.2--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.2--2/chat.md) |
| <a id="member-1"></a>1 | sase-ud.2--1 | completed | gpt-5.5 / codex | 2026-08-26T19:11:30.361128+00:00 → 2026-08-26T19:29:27.665315+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ud.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ud.2--1/chat.md) |
| <a id="member-code"></a>code | sase-ud.2--code | completed | gpt-5.5 / codex | 2026-08-26T18:08:22.462308+00:00 → 2026-08-26T18:53:48.340416+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ud.2--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`e16872c`](https://github.com/sase-org/sase/commit/e16872c9deaa9e48cf73e9d26196adf6bae621d8) | feat(shells): add shells substrate | 2026-08-26 15:53:46 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ud.1](../agents/bbugyi200.athena.sase-ud.1/README.md) | sase-ud hood | completed |
| [sase-ud.10](bbugyi200.athena.sase-ud.10.md) (family · 2) | sase-ud hood | completed 2 |
| [sase-ud.11](bbugyi200.athena.sase-ud.11.md) (family · 2) | sase-ud hood | completed 2 |
| [sase-ud.12](bbugyi200.athena.sase-ud.12.md) (family · 2) | sase-ud hood | completed 2 |
| [sase-ud.13](bbugyi200.athena.sase-ud.13.md) (family · 2) | sase-ud hood | failed 2 |
| [sase-ud.13.1.1](../agents/bbugyi200.athena.sase-ud.13.1.1/README.md) | sase-ud hood | completed |
| [sase-ud.13.1.2](bbugyi200.athena.sase-ud.13.1.2.md) (family · 8) | sase-ud hood | completed 5, failed 3 |
| [sase-ud.13.1.3](bbugyi200.athena.sase-ud.13.1.3.md) (family · 2) | sase-ud hood | failed 2 |
| [sase-ud.13.1.3.1.1](bbugyi200.athena.sase-ud.13.1.3.1.1.md) (family · 5) | sase-ud hood | dismissed 5 |
| [sase-ud.13.1.3.1.2](../agents/bbugyi200.athena.sase-ud.13.1.3.1.2/README.md) | sase-ud hood | dismissed |
| [sase-ud.13.1.3.1.3](../agents/bbugyi200.athena.sase-ud.13.1.3.1.3/README.md) | sase-ud hood | dismissed |
| [sase-ud.13.1.3.1.4](bbugyi200.athena.sase-ud.13.1.3.1.4.md) (family · 21) | sase-ud hood | active 2, completed 8, failed 11 |
| [sase-ud.13.1.3.1.4](../agents/bbugyi200.athena.sase-ud.13.1.3.1.4/README.md) | sase-ud hood | active |
| [sase-ud.13.1.3.1.5.1](bbugyi200.athena.sase-ud.13.1.3.1.5.1.md) (family · 3) | sase-ud hood | dismissed 3 |
| [sase-ud.13.1.3.1.5.land](../agents/bbugyi200.athena.sase-ud.13.1.3.1.5.land/README.md) | sase-ud hood | dismissed |
| [sase-ud.13.1.3.1.land](bbugyi200.athena.sase-ud.13.1.3.1.land.md) (family · 4) | sase-ud hood | dismissed 3, failed 1 |
| [sase-ud.13.1.4](bbugyi200.athena.sase-ud.13.1.4.md) (family · 11) | sase-ud hood | completed 6, failed 5 |
| [sase-ud.13.1.5](../agents/bbugyi200.athena.sase-ud.13.1.5/README.md) | sase-ud hood | completed |
| [sase-ud.13.1.land](bbugyi200.athena.sase-ud.13.1.land.md) (family · 3) | sase-ud hood | completed 1, failed 1, waiting 1 |
| [sase-ud.14](../agents/bbugyi200.athena.sase-ud.14/README.md) | sase-ud hood | completed |
| [sase-ud.3](bbugyi200.athena.sase-ud.3.md) (family · 2) | sase-ud hood | completed 2 |
| [sase-ud.4](../agents/bbugyi200.athena.sase-ud.4/README.md) | sase-ud hood | completed |
| [sase-ud.5](../agents/bbugyi200.athena.sase-ud.5/README.md) | sase-ud hood | completed |
| [sase-ud.6](bbugyi200.athena.sase-ud.6.md) (family · 2) | sase-ud hood | completed 2 |
| [sase-ud.7](bbugyi200.athena.sase-ud.7.md) (family · 4) | sase-ud hood | completed 3, failed 1 |
| [sase-ud.8](../agents/bbugyi200.athena.sase-ud.8/README.md) | sase-ud hood | completed |
| [sase-ud.9](../agents/bbugyi200.athena.sase-ud.9/README.md) | sase-ud hood | completed |
| [sase-ud.land](../agents/bbugyi200.athena.sase-ud.land/README.md) | sase-ud hood | active |
