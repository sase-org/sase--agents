# Chat History - ace-run (19z--plan)

- **TIMESTAMP:** 2026-11-08 09:01:23 EST
- **MODEL:** claude/opus
- **AGENT:** 19z--plan

**Plan:** /home/bryan/.sase/plans/202611/leader_j_stranded_fallback.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/leader_j_stranded_fallback.md`

> # Plan: `,j` final fallback to the most recently stranded agent
> ## Goal
> On the Agents tab, `,j` (`leader_mode.keys.jump_to_next_unread_done_agent`) currently
> tries the next unread completed agent and then falls back to `,J` (next stopped agent),
> toasting `No unread completed or stopped agents` on a double miss. Add a third and final
> tier. When neither an unread completed agent nor a stopped agent can be reached, `,j`
> jumps to the **most recently stranded** agent node. It toasts only when all three tiers
> miss.
> `,J` (`jump_to_next_stopped_agent`) does not change. No new keymap is added.
> ## Definitions (use these exactly)

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The `,j` keymap on the "Agents" tab already falls back to jumping to stopped nodes
(i.e. the `,J` keymap's behavior). Can you now help me make it so, if no stopped nodes
exist to jump to either, that this keymap jumps to the most recently stranded node as a
final fallback?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Status: I've mapped all the code, tests, and docs the change touches. A few checks remain (keymap metadata, the docs-writing rules, the test helpers) before I write the plan.

I have what I need. Writing the plan now.

The plan passes validation. Submitting it.

I've written and submitted the plan for the `,j` stranded fallback. It's waiting for your approval, and no code has changed yet.

**What the plan does**

`,j` on the Agents tab gets a third and final step:
1. Jump to the next unread completed agent (as now).
2. If there is none, jump to the next stopped agent (as now, same as `,J`).
3. **New:** if there is none, jump to the most recently stranded agent row.
4. The toast becomes `No unread completed, stopped, or stranded agents` and appears only when all three find nothing.

**What counts as "stranded" and "most recent"**
- A stranded node is an agent row whose own bead is marked stranded: the rows that show `STRANDED ⚐` or the bright `⚐`, and that the `stranded:true` query matches. Rows that are only blocked (the dim `⚐`) don't count.
- "Most recent" means when the work became stranded, which is the timestamp behind the `⚐ 31h` age label. Rows without that timestamp use their stop time instead.
- The keypress only reads the stranded report already held in memory, so it does no disk reads. If that report hasn't loaded yet, the press finds nothing and shows the toast.

**How it's built**
- The new jump reuses the code behind the existing unread and stopped jumps. That means it already reaches rows on other agent tabs and rows inside collapsed clans.
- Unlike the stopped jump, it doesn't switch the detail view to the Context panel. You resolve a stranded row with `Enter`, which already opens its resolve dialog.
- One shared helper decides which rows are stranded, used by both the new jump and the `stranded:true` query.
- The command palette now offers `,j` when only stranded rows exist.
- The plan also updates:
  - the `,j` labels (help modal, palette, keymap catalog);
  - the comment in `default_config.yml`;
  - two docs pages (`agents-tab-modes.md`, `perf-runbook.md`);
  - the existing tests, plus a new `tests/ace/tui/test_agent_stranded_navigation.py`.
- `,J` and the leader-mode footer don't change. `just check` is the final check.

**One decision for you when approving (`repeat_press`)**
- **cycle (default):** each repeated press moves to the next older stranded row and wraps around, like the other two steps. The first press still lands on the newest one.
- **most_recent:** every press lands on the single most recently stranded row.

It's sized `small` for one coding agent. Once you approve, the host launches the agent that implements it.
