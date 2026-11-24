# Chat History - ace-run (1fp--plan)

- **TIMESTAMP:** 2026-11-24 07:09:36 EST
- **MODEL:** claude/opus
- **AGENT:** 1fp--plan

**Plan:** /home/bryan/.sase/plans/202611/l_jump_running_monitor.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/l_jump_running_monitor.md`

> # `l` jumps to a session's or clan's lone running monitor
> ## Problem
> In the screencast, the Agents tab cursor sits on the collapsed agent-session row
> `research.65.linker.w0.r0` (project `love`, status `WAITING SPOTIFY`, `⚙1`). Its only
> live work is the monitor turn `research.65.linker.w0.r0--mon`. Pressing `l` only expands
> the session: the cursor stays on the session row, and the user has to press `jj` to
> reach the monitor.
> ## Root cause
> `l` → `action_expand_or_layout` → `_expand_fold`
> (`src/sase/ace/tui/actions/agents/_folding_agent_groups.py`). The "jump to the lone

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The `l` keymap on the "Agents" tab should select a running monitor if its the only
node running in an agent clan. See the ~/tmp/screencasts/20261124_065555.mp4 screencast
for context. Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

The code already has a rule for this: `l` on a clan row with exactly one running member jumps to that member. I'm now checking why that rule doesn't fire when the only running member is a monitor.

I'm working out whether the row in the screencast is a clan or a session, and why the existing jump-to-running-member rule skips the monitor.

Narrowing the "only running node" check: a session can briefly run finalizer steps (e.g. the `#gh` diff/commit rows) alongside its monitor, so I'm checking how those rows hang off the session.

I have the root cause and the design. Reading the lint/test note so the plan names the right verification steps, then I'll write the plan.

I have everything I need. Writing the plan now.

The plan passes validation. Submitting it.

I've written the fix plan and submitted it for your review. I haven't changed any code yet. Coding starts after you approve.

**What's going wrong:** the row in your screencast (`research.65.linker.w0.r0`) is an agent **session**, not a clan. `l` already jumps to a clan's only running member, but only on clan rows. On a session row, `l` just opens the fold one level, so the cursor stays put and you need `jj` to reach the `--mon` row. I checked this against the live agent data, and the codebase already has a helper that finds a session's running monitor.

**Planned behavior:**
- **Session row:** `l` selects the session's monitor (expanding the session first if needed), but only when that monitor is running and is the session's only running turn. You can jump back with Ctrl+O, and `h` returns to the session as usual.
- **Everything else stays the same:** if a session has no running monitor, or an agent turn is still running next to it, `l` behaves exactly as it does today. Running agent turns and gate turns are not jump targets; you only asked about monitors.
- **One trade-off:** while the monitor is the only thing running, `l` on an already-expanded session jumps instead of revealing hidden steps. You can still reveal them by pressing `l` on the monitor row.
- **Footer hint:** shows `l running monitor` whenever `l` would land on a monitor.
- **Also in the plan:** the help-screen line, the `default_config.yml` comment, the docs pages that describe `l`, and tests. `just check` must pass.

**One decision for you at approval (`clan_drill`):** when a clan's only running node is a session's monitor, should one `l` on the clan row jump straight to the monitor? I defaulted to yes, since that's the literal reading of your request. The alternative is one level per press: the first `l` selects the session, and a second `l` reaches the monitor.

I sized it `medium`, so the coder will implement it directly from the plan.
