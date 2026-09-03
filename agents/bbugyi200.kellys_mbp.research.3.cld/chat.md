# Chat History - ace-run (research.3.cld)

- **TIMESTAMP:** 2026-09-03 16:37:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_162220.md`

## Prompt

%id(cld, clan=research.3) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I would like to add a new `,X` keymap to the "Agents" tab
that works in a very similar way to the `,x` keymap but targets the most recently
launched agent. Notably, this keymap should be able to target an agent that hasn't
started yet (i.e. the associated proc that launches the agent hasn't finished running
yet). The goal of this new keymap is to allow users to very quickly kill and edit the
last agent that they launched, which should be useful since users often realize they
want to change the prompt they just used to launch an agent (e.g. after hitting the
`<enter>` key too quickly, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by exploring the Agents tab and the `,x` keymap implementation.

Research written to `sase/repos/research/202609/kill_and_edit_last_launched_agent.md`.

## What I found

**The feature is two separate problems, and the code already has a seam for each.**

**Targeting.** "Most recently launched" should mean *the last launch this ACE session submitted* — not the newest row on disk. `_submit_launch_proc` (`_launch_procs.py:55`) already gets a placeholder `ObservedProc` back synchronously from `register_pending` and already keys the submitted prompt off it. Recording one more field there is the entire targeting mechanism. The disk-scan alternatives (`get_most_recent_agent_name`, newest artifact timestamp) are both blind to the in-flight window *and* will happily retarget onto family members, clan members, or agents your agent spawned.

**Acting before the agent exists.** Don't cancel the launch — defer the kill and *don't* defer the edit:
- The prompt is known at T0 (in `_launch_submitted_prompts`, and durably in the proc's operation-request sidecar), so the prompt bar can mount instantly.
- `_on_launch_proc_complete` already receives `AgentLaunchResult[]` carrying `artifacts_dir`, `agent_name`, `pid` — an exact handle on what to kill, via the ordinary well-tested kill path.

Cancelling the launch proc is the wrong path: `stop_proc_shell` is guarded to proc-shell lifecycle rows only (new core-backend plumbing), and by the time a human reacts the child has usually already claimed a name, made the artifact dir, and spawned a detached process — so you'd orphan state and still need the deferred kill as a fallback.

**The recommended shape** is small: `,X` = *resolve the last launch → reveal the row → run the existing `,x` flow on it*, with a deferred-kill branch when the proc is still in flight. Refactor `_kill_and_edit_agent` to accept an explicit target, reuse `_edit_and_relaunch_agents_bulk` for multi-agent launches, and reuse the relaunch cleanup barrier.

**Two things I'd flag before you commit to it:**

1. The barrier's 30s timeout (`_relaunch_barrier.py:20`) is tuned for a cleanup round-trip, not "wait out a whole launch *then* a cleanup." If a launch runs long, the barrier releases the parked relaunch and the forced-name-reuse race it exists to prevent comes back. The doc proposes folding "a pending launch kill exists" into `_relaunch_cleanup_is_pending` so the gate spans T0→kill-settled.

2. **Measure first.** Run `SASE_AGENT_LAUNCH_TIMING=1` on a few real launches. If T0→completion is reliably under ~1.5s, the in-flight phase isn't worth building and a "still starting, try again" toast is the whole feature. If it's commonly 3–10s — which the 30s slow-stage threshold in `launch_timing.py` suggests is expected — the in-flight phase *is* the feature, and Phase 1 alone won't solve your actual problem.
