# Chat History - ace-run (sase-7r.land--plan)

- **TIMESTAMP:** 2026-07-19 21:24:31 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-7r.land--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-sase_7r_land__plan-260719_191106.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260719_191106.md`

**Plan:** /home/bryan/.sase/plans/202607/clan_summary_directive_edit.md


## Prompt

#gh:gh_sase-org__sase
%id(land, clan=sase-7r)
%model:@big_epic_lander
%auto
%w:sase-7r.1,sase-7r.2,sase-7r.3,sase-7r.4,sase-7r.5,sase-7r.6,sase-7r.7
You are the land agent for epic bead sase-7r: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-7r` (children, linked plan file), then `sase bead show` on each child
   bead. Confirm every bead note was addressed, and read the actual source code and the epic's commits (bead IDs
   appear in commit messages) to confirm the work previous agents reported complete really is.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-7r, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Close the epic with `sase bead close sase-7r`. AFTER closing, run `just symvision` if available
   (epic-symbol whitelist entries for sase-7r expire at close) and remove the stale entries and unused code
   it reports. Finally, set `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by
   `sase bead show`).

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Make step 3 the plan's final phase (close, run symvision, mark the plan file done)
so the agent that executes the plan finishes the landing. Otherwise do step 3 now.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/clan_summary_directive_edit.md`

> # Plan: Preserve clan summaries in prompt edits, then land sase-7r
> ## Context
> Epic sase-7r taught the declaring `%clan` directive two new named arguments — `summary=` (quoted string or `[[ ... ]]`
> text block) and `summary_script=` — plus a `::` double-colon shorthand (`%clan:<name>:: <text>` /
> `%clan(<args>):: <text>`) that directive parsing rewrites into `summary=[[...]]`
> (`src/sase/xprompt/_directive_shorthand.py`). Epic clans launched by `sase bead work` now always declare
> `%clan(<epic_id>, tribe=epic, summary_script=sase_clan_summary_epic)` (`src/sase/bead/work.py`), and the chezmoi
> `research_swarm` xprompt declares an inline `summary=[[...]]`.
> The prompt-edit helpers in `src/sase/xprompt/directive_edit.py` predate the epic and were never taught the new
> arguments. Two confirmed gaps (both reproduced against the current tree):

*See full plan file for details.*

