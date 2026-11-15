# Chat History - ace-run (1cn--plan)

- **TIMESTAMP:** 2026-11-15 13:01:55 EST
- **MODEL:** claude/opus
- **AGENT:** 1cn--plan

**Plan:** /home/bryan/.sase/plans/202611/phantom_starting_claim_rows.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/phantom_starting_claim_rows.md`

> # Stop stale workspace-claim placeholders from inflating the TUI "starting" count
> ## Problem
> A long-running `sase tui` shows `N starting` in the Agents headline (for example
> `14 [3 running · 2 starting · 2 waiting · …]`) when no agent is actually starting. A
> freshly launched TUI over the same disk state shows no `starting` count. The phantom
> count never clears; only a TUI restart clears it.
> ## Root cause (confirmed against a live TUI)
> A read-only dump of a live TUI's `_agents` roster found the two phantom rows. Both were
> **workspace pre-claim placeholders**:
> ```

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Why does the TUI show that there are two agents starting when I don't believe that
is true. See the ~/tmp/screenshots/20261115_124534.png screenshot for context. Is this
something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

The header's "starting" count is the number of hidden agents whose status is `STARTING`. Next I'll check which real agents currently have that status.

I'm reproducing the TUI's agent loader to see which two rows it marks `STARTING`.

Nothing is `STARTING` right now, so I'm checking which runs existed around 12:45 to work out what those two rows were.

No procs or `ace-run` artifacts were in a starting state around 12:45. Next I'll take a fresh TUI screenshot to see whether a newly started TUI also shows the phantom "starting" count.

I'm tracing which code path can leave hidden `STARTING` rows behind in a long-running TUI, starting with pending-launch placeholders.

I'm reading the TUI's incomplete-load merge, which carries cached rows forward between refreshes. That is the likeliest place stale `STARTING` rows survive.

I'm checking the TUI's named-proc and fleet projection sources. These are rebuilt from in-process state rather than from disk, so they could keep `STARTING` rows that a fresh TUI wouldn't have.

Your TUI freezes its heap with `gc.freeze()`, so the probe couldn't find the App object that way. Next I'll locate it by walking the main thread's stack.

I have the root cause and a reproduction. Now I'll invoke the planning skill.

I've written the plan. Next I'll validate it with the plan schema checker.

The plan passed validation. Next I'll submit it for your review.

Those two "starting" agents don't exist. The TUI kept two leftover temporary rows that are never shown and never cleaned up, and it counts them as "starting". Yes, this should be fixed: the count stays wrong until the TUI restarts, and the same flaw can hide a real running agent. I've written and submitted a plan for the fix.

**What I checked**
- A freshly started TUI over the same agents shows `16 [4 running · 2 waiting · 4 failed · 6 done]`, with no "starting".
- Your long-running TUI (pid 88182) still showed `2 starting` at 12:53, after your kill-and-dismiss of 15 agents.
- To identify the two rows, I ran a small read-only Python script inside your TUI process (`sys.remote_exec`) that dumped its in-memory agent list to a file in `/tmp`. Both rows were in state `STARTING`, with no artifacts timestamp and a process that has since exited:
  - `ace(run)-261115_121202`: the bob-cli launch at 12:12 (agent `1ck`, which you killed with kill-and-edit).
  - `ace(run)-261115_123045`: the `sase-1t0.1` launch at 12:30.

**Why it happens**
1. When an agent launches, the launcher first reserves a workspace under its own process id, with no artifacts timestamp. A moment later it hands the reservation to the real agent process and adds the timestamp.
2. If the TUI refreshes during that short gap, it records a `STARTING` row for the reservation.
3. Later refreshes are partial updates layered over the cached list (in `merge_incomplete_load_after_complete_history`). Nothing ever matches that row again: it has no timestamp, it is still flagged as live, and its process id differs from the real agent's. So it is carried forward forever.
4. `STARTING` rows are never displayed, so you can't see or dismiss it. They still feed the `starting` number in the header. Only a full reload clears the list, and that happens once, at startup.

An offline simulation of the same merge code found a worse version of this flaw that hasn't bitten you yet. If the TUI caches a timestamped reservation as `STARTING` before the agent's real record appears, the real row is thrown away. The agent then disappears from the list and is counted as "starting" instead. Agents in a clan (like the epic phases) escape this; standalone agents don't.

**The plan** (`sase_plan_phantom_starting_claim_rows.md`, size medium)
- Mark rows that come from workspace reservations so the merge can recognise them.
- Record on each refresh whether it re-read the reservations.
- Drop cached reservation rows whenever a refresh re-read them; otherwise drop one as soon as the agent's real record arrives.
- Let a real agent record always replace a cached reservation row.
- Add tests for both versions of the bug.

It's waiting for your approval. Until the fix lands, restarting the TUI clears the phantom count.
