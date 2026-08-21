# Family: sase-ns.6.6.6.1

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-ns](../users/bbugyi200/machines/athena/hoods/sase-ns/README.md) / sase-ns.6.6.6.1

Owner: `bbugyi200.athena` · Hood: `sase-ns` · Members: 4 · Bead: [sase-ns.6.6.6.1](https://github.com/sase-org/sase--beads/blob/main/pages/sase-ns/sase-ns.6.6.6.1.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-ns.6.6.6.1--code [completed]"]
  n1["sase-ns.6.6.6.1--plan [completed]"]
  n0 --> n1
  n2["sase-ns.6.6.6.1--1 [active]"]
  n0 --> n2
  n3["sase-ns.6.6.6.1--mon [failed]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | sase-ns.6.6.6.1--code | completed | sonnet / claude | 2026-08-17T16:35:02.980830+00:00 | [2](../agents/bbugyi200.athena.sase-ns.6.6.6.1--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.6.6.1--code/chat.md) |
| <a id="member-plan"></a>plan | sase-ns.6.6.6.1--plan | completed | opus / claude | 2026-08-17T16:14:31.662764+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ns.6.6.6.1--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-ns.6.6.6.1--plan/chat.md) |
| <a id="member-1"></a>1 | sase-ns.6.6.6.1--1 | active | grok-4.6 / grok | 2026-08-17T10:50:49.865442+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-ns.6.6.6.1--1/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-ns.6.6.6.1--mon | failed | grok-4.6 / grok | 2026-08-17T10:33:03.742128+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-ns.6.6.6.1--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`7391a74`](https://github.com/sase-org/sase/commit/7391a745bc42971a1f7460a4f27721756959858a) | fix(stats): render schema-6 commits, patches, and xprompt truncation | 2026-08-17 17:18:36 UTC |
| code | sase | [`5e58fb1`](https://github.com/sase-org/sase/commit/5e58fb1c8b4a92e91056a179b9591d52beedd0d8) | fix(config): publish merged-config and owner-snapshot caches atomically | 2026-08-17 17:21:41 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-ns.6.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.6.2/README.md) | sase-ns.6.6.6 hood | dismissed |
| [sase-ns.6.6.6.3](bbugyi200.athena.sase-ns.6.6.6.3.md) (family · 2) | sase-ns.6.6.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.6.6.4](../agents/bbugyi200.athena.sase-ns.6.6.6.4/README.md) | sase-ns.6.6.6 hood | dismissed |
| [sase-ns.6.6.6.5](../agents/bbugyi200.athena.sase-ns.6.6.6.5/README.md) | sase-ns.6.6.6 hood | dismissed |
| [sase-ns.6.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.6.land/README.md) | sase-ns.6.6.6 hood | active |
| [sase-ns.6.6.1](../agents/bbugyi200.athena.sase-ns.6.6.1/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.2](../agents/bbugyi200.athena.sase-ns.6.6.2/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.3](../agents/bbugyi200.athena.sase-ns.6.6.3/README.md) | sase-ns.6.6 hood | dismissed |
| [sase-ns.6.6.4](bbugyi200.athena.sase-ns.6.6.4.md) (family · 4) | sase-ns.6.6 hood | completed 1, dismissed 2, failed 1 |
| [sase-ns.6.6.5](bbugyi200.athena.sase-ns.6.6.5.md) (family · 4) | sase-ns.6.6 hood | completed 1, dismissed 2, failed 1 |
| [sase-ns.6.6.land](bbugyi200.athena.sase-ns.6.6.land.md) (family · 4) | sase-ns.6.6 hood | dismissed 2, failed 2 |
| [sase-ns.6.6.land](../agents/bbugyi200.athena.sase-ns.6.6.land/README.md) | sase-ns.6.6 hood | completed |
| [sase-ns.6.1](bbugyi200.athena.sase-ns.6.1.md) (family · 2) | sase-ns.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.2](bbugyi200.athena.sase-ns.6.2.md) (family · 2) | sase-ns.6 hood | completed 1, dismissed 1 |
| [sase-ns.6.3](../agents/bbugyi200.athena.sase-ns.6.3/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.4](../agents/bbugyi200.athena.sase-ns.6.4/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.5](../agents/bbugyi200.athena.sase-ns.6.5/README.md) | sase-ns.6 hood | dismissed |
| [sase-ns.6.land](bbugyi200.athena.sase-ns.6.land.md) (family · 4) | sase-ns.6 hood | dismissed 2, failed 2 |
| [sase-ns.6.land](../agents/bbugyi200.athena.sase-ns.6.land/README.md) | sase-ns.6 hood | completed |
| [sase-ns.1](bbugyi200.athena.sase-ns.1.md) (family · 4) | sase-ns hood | completed 2, dismissed 1, failed 1 |
| [sase-ns.2](bbugyi200.athena.sase-ns.2.md) (family · 8) | sase-ns hood | completed 4, dismissed 1, failed 3 |
| [sase-ns.3](bbugyi200.athena.sase-ns.3.md) (family · 2) | sase-ns hood | completed 1, dismissed 1 |
| [sase-ns.4](../agents/bbugyi200.athena.sase-ns.4/README.md) | sase-ns hood | dismissed |
| [sase-ns.5](../agents/bbugyi200.athena.sase-ns.5/README.md) | sase-ns hood | dismissed |
| [sase-ns.land](bbugyi200.athena.sase-ns.land.md) (family · 4) | sase-ns hood | dismissed 1, failed 3 |
| [sase-ns.land](../agents/bbugyi200.athena.sase-ns.land/README.md) | sase-ns hood | completed |
