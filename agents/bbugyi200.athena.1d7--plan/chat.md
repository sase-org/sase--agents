# Chat History - ace-run (1d7--plan)

- **TIMESTAMP:** 2026-11-17 06:19:29 EST
- **MODEL:** claude/opus
- **AGENT:** 1d7--plan

**Plan:** /home/bryan/.sase/plans/202611/gate_handoff_continuation_nodes.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/gate_handoff_continuation_nodes.md`

> # Publish the starter turn's continuation node on gate handoffs
> ## Why
> On 2026-11-17, epic phase `tailnet-x.13` (project `gh_bbugyi200__tailnet`, apollo) ran a
> long sudo-gate recovery chain inside one agent session: `--plan` (monitor handoff), then
> five agent turns `--1` … `--5`, each of which ended by staging a typed `sase_sudo` gate.
> Each gate's follow-up turn launches with `#fork:tailnet-x.13`, so it replays the whole
> session through versioned continuation replay
> (`src/sase/history/chat_fork/continuation/replay.py`).
> The sixth turn (`--6`, run `20261117060310`) failed after 29 seconds, before the
> provider started:

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The `tailnet-x.13` sase agent (on my apoollo machine) just failed (I had to
restart it). Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Still looking for the failed `tailnet-x.13` agent. Reading the tailnet notes now to see how to reach apollo.

Found `tailnet-x.13` on apollo: it's running again after your restart. Now looking for what's left of the failed run before the restart.

Checking how a successful turn normally records its continuation node, using a surviving sibling run (`tailnet-x.10--1`) for comparison.

Still tracing the `--5` turn's missing artifacts. Checking apollo's dismissal index for what happened to the `tailnet-x.13` session at 11:04.

The user dismissed the failed session at 11:04:07, which archived its artifacts. Looking for that archive so I can inspect the `--5` turn's metadata.

Dismissal removed the artifacts without a bundle, so I'll work from code. Finding where a finished turn writes its `continuation_node_ref` and what can make that step skip.

The node is never written for gated turns: the prepared prompt is there, but there's no `nodes/`, `records/`, or `manifest.json`. Finding the turn-exit path for gated handoffs.

No existing bead covers this. Reading how the monitor path publishes its node and how a gate's follow-up turn is launched, so the plan can mirror the monitor path.

Root cause is clear. Checking two last details for the plan: what gate-turn transcripts contain, and what response text the plan/question gate paths have available.

Before planning, checking whether the restart dropped work from the failed session: the new run reported rescuing leftover local commits and worktree changes from workspace #10.

No existing test covers the over-budget refusal. Checking whether the docs describe gate-handoff continuation, so the plan updates them if needed.

No docs cover this, so the change is code and tests only. Writing the plan.

Validation wants `title` and `goal` in the frontmatter. Adding them.

Plan validates. Proposing it.

Yes, this is a real SASE bug and worth fixing. I've staged a plan for your approval: `sase_plan_gate_handoff_continuation_nodes.md`, a single medium task, with no sase-core change.

**What failed:** `tailnet-x.13--6` (run `20261117060310`) died 29 seconds in, before Codex started. It was building its `#fork:tailnet-x.13` history and refused to launch with `protected_content_over_budget`. The block it refused on was the `--5` turn's transcript, which had grown to 458 KB against a 256 KB per-block cap.

**Why it got that big:**
- **The bug:** when a turn hands off to a gate, SASE never saves that turn's compact continuation record (its `agent_delta` node). Monitor handoffs do save it (`src/sase/axe/run_agent_exec_monitor.py`); gate handoffs don't (`src/sase/axe/run_agent_exec_gate.py`).
- **The fallback:** without that record, the next turn's history pastes in the previous turn's whole chat transcript instead.
- **The multiplier:** each transcript already contains the history pasted into its own prompt. So every sudo-gate hop re-pasted all the earlier ones. The `tailnet-x.13` transcripts went 10K → 35K → 103K → 210K → 458K. By `--5`, the plan turn appeared 16 times in a single prompt.
- **It's systemic:** all 39 surviving gated turns on apollo, in several projects (plan, question and sudo gates), are missing the record. Any long gate chain will hit this.

**The plan:**
1. Save the turn's continuation record when it hands off to a gate, the same way the monitor path does, across all three gate paths (staged, plan and question).
2. Pass the real model reply into that record.
3. Make the over-budget error name the turn and its size, instead of an opaque hash.
4. Add regression tests, including a nested replay that must not re-paste transcripts.

**Two things to act on now:**
- **The restarted `tailnet-x.13` will probably hit this again.** It's already on a new sudo-gate chain (`--1` is running), and the same doubling will trip the cap after about five more gated hops unless the fix lands and apollo updates first.
- **The `--5` source fix isn't in any repo.** Gated handoffs pass uncommitted changes forward to the next turn rather than committing them. Because `--6` failed, your restart moved that work into rescue patches on apollo:
  - The nine-file `nut` fix (PATH handling and the needs-root readers) on `ed452db`: `~/.sase/rescue/202611/20261117T110606Z-ws10-external-projects-nut-6d47a6cb/worktree.patch`
  - Tailnet edits (`hosts/athena/nut/README.md` and a new `nut.toml`): `~/.sase/rescue/202611/20261117T110557Z-ws10-lease-checkout-475ae71d/`

  The binary installed at `/usr/local/bin/nut` (sha `ddbbc4ec…`) was built from that unsaved `nut` fix. The new agent doesn't know about the patches, so if it rebuilds from `ed452db` it will lose the fix. Point it at the `nut` patch before it does. It has already restored its own host config, so check its version before applying the tailnet patch over it.
