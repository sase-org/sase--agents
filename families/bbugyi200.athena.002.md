# Family: 002

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [002](../users/bbugyi200/machines/athena/hoods/002/README.md) / 002

Owner: `bbugyi200.athena` · Hood: `002` · Members: 10

## Lineage

```mermaid
flowchart TD
  n0["002--mon-0 [failed]"]
  n1["002--plan [completed]"]
  n0 --> n1
  n2["002--2 [completed]"]
  n0 --> n2
  n3["002--mon-1 [failed]"]
  n0 --> n3
  n4["002--3 [active]"]
  n0 --> n4
  n5["002--4 [active]"]
  n0 --> n5
  n6["002--mon [failed]"]
  n0 --> n6
  n7["002--code [completed]"]
  n0 --> n7
  n8["002--mon-2 [failed]"]
  n0 --> n8
  n9["002--1 [completed]"]
  n0 --> n9
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | 002--mon-0 | failed | gpt-5.5 / codex | 2026-08-13T22:50:54.390109+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.002--mon-0/chat.md) |
| <a id="member-plan"></a>plan | 002--plan | completed | opus / claude | 2026-08-13T21:38:06.384113+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.002--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.002--plan/chat.md) |
| <a id="member-2"></a>2 | 002--2 | completed | gpt-5.5 / codex | 2026-08-13T23:38:34.153023+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.002--2/prompt.md) | [Chat](../agents/bbugyi200.athena.002--2/chat.md) |
| <a id="member-mon-1"></a>mon-1 | 002--mon-1 | failed | gpt-5.5 / codex | 2026-08-13T23:55:10.343830+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.002--mon-1/chat.md) |
| <a id="member-3"></a>3 | 002--3 | active | gpt-5.5 / codex | 2026-08-14T00:10:44.737900+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.002--3/prompt.md) | — |
| <a id="member-4"></a>4 | 002--4 | active | gpt-5.5 / codex | 2026-08-14T00:25:00.088965+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.002--4/prompt.md) | — |
| <a id="member-mon"></a>mon | 002--mon | failed | gpt-5.5 / codex | 2026-08-13T22:10:13.471196+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.002--mon/chat.md) |
| <a id="member-code"></a>code | 002--code | completed | gpt-5.5 / codex | 2026-08-13T21:50:59.552463+00:00 | [1](../agents/bbugyi200.athena.002--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.002--code/chat.md) |
| <a id="member-mon-2"></a>mon-2 | 002--mon-2 | failed | gpt-5.5 / codex | 2026-08-14T00:22:48.968559+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.002--mon-2/chat.md) |
| <a id="member-1"></a>1 | 002--1 | completed | gpt-5.5 / codex | 2026-08-13T22:36:59.638634+00:00 | [1](../agents/bbugyi200.athena.002--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.002--1/prompt.md) | [Chat](../agents/bbugyi200.athena.002--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`d5d2dfa`](https://github.com/sase-org/sase/commit/d5d2dfaf0d6a2ad9d6c6c29c775aaa0c4373c99c) | chore: Add SDD prompt and plan for bead\_search\_command | 2026-06-18 12:12:52 UTC |
| — | sase | [`5254b39`](https://github.com/sase-org/sase/commit/5254b3905b992a090714af3cbbf7efa5ede9f737) | chore(beads): add bead search epic plan beads | 2026-06-18 12:18:13 UTC |
| code | sase | [`2e2facb`](https://github.com/sase-org/sase/commit/2e2facb945fb9a9461b14ff2788525b41764fbc7) | fix: release monitor handoff waits after successor success | 2026-08-13 22:11:40 UTC |
| 1 | sase | [`a9642c6`](https://github.com/sase-org/sase/commit/a9642c63c17a79b52f5848d005a54672079d468e) | fix(tui): avoid disabled trace cache mutation | 2026-08-13 22:52:07 UTC |
