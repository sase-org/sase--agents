# Family: 0d6

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0d6](../users/bbugyi200/machines/athena/hoods/0d6/README.md) / 0d6

Owner: `bbugyi200.athena` · Hood: `0d6` · Members: 8

## Lineage

```mermaid
flowchart TD
  n0["0d6--mon-0 [failed]"]
  n1["0d6--plan [completed]"]
  n0 --> n1
  n2["0d6--mon [failed]"]
  n0 --> n2
  n3["0d6--2 [completed]"]
  n0 --> n3
  n4["0d6--code [completed]"]
  n0 --> n4
  n5["0d6--3 [active]"]
  n0 --> n5
  n6["0d6--mon-1 [failed]"]
  n0 --> n6
  n7["0d6--1 [completed]"]
  n0 --> n7
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | 0d6--mon-0 | failed | sonnet / claude | 2026-08-25T00:39:05.607973+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0d6--mon-0/chat.md) |
| <a id="member-plan"></a>plan | 0d6--plan | completed | opus / claude | 2026-08-24T23:18:42.670528+00:00 → 2026-08-25T00:22:10.462275+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0d6--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0d6--plan/chat.md) |
| <a id="member-mon"></a>mon | 0d6--mon | failed | sonnet / claude | 2026-08-25T00:22:01.114024+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0d6--mon/chat.md) |
| <a id="member-2"></a>2 | 0d6--2 | completed | sonnet / claude | 2026-08-25T00:42:02.447705+00:00 → 2026-08-25T00:43:56.797508+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0d6--2/prompt.md) | [Chat](../agents/bbugyi200.athena.0d6--2/chat.md) |
| <a id="member-code"></a>code | 0d6--code | completed | sonnet / claude | 2026-08-24T23:39:13.993275+00:00 → 2026-08-25T00:22:10.462275+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0d6--code/chat.md) |
| <a id="member-3"></a>3 | 0d6--3 | active | sonnet / claude | 2026-08-25T01:01:06.727383+00:00 | [1](../agents/bbugyi200.athena.0d6--3/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0d6--3/prompt.md) | — |
| <a id="member-mon-1"></a>mon-1 | 0d6--mon-1 | failed | sonnet / claude | 2026-08-25T00:43:48.509065+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0d6--mon-1/chat.md) |
| <a id="member-1"></a>1 | 0d6--1 | completed | sonnet / claude | 2026-08-25T00:37:58.093731+00:00 → 2026-08-25T00:39:14.124352+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0d6--1/prompt.md) | [Chat](../agents/bbugyi200.athena.0d6--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 3 | sase | [`9c7c10a`](https://github.com/sase-org/sase/commit/9c7c10aa2a9f73445db7361a6dfaf0e0dbec9877) | feat(axe,xprompt): expand disabled-region handling to fork setup, embedded workflows, and VCS tag parsing | 2026-08-24 21:06:01 EDT |
