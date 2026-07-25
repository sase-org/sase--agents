# Chat History - ace-run (6s.f-0--plan)

- **TIMESTAMP:** 2026-07-12 12:23:39 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 6s.f-0--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-6s_f_0__plan-260712_120918.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_120918.md`

**Plan:** /home/bryan/.sase/plans/202607/companion_clone_dir_prefix_strip.md


## Prompt

#gh:gh_sase-org__sase #fork:6s Can you now help me start storing companion repos in directories with names that strip the `<project>--` prefix from the actual GitHub repo name? For example, the `sase--plans` repo should be cloned to the sase/repos/plans/ directory instead of the sase/repos/sase--plans/ directory. Again, there should be no backward compatibility code (you should migrate all sase projects as necessary).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/companion_clone_dir_prefix_strip.md`

> # Strip the `<project>--` Prefix from Companion Repo Clone Directory Names
> ## Problem & Goals
> SDD companion repos are currently cloned into workspace checkouts at directories named after the full GitHub repo
> basename:
> ```
> <workspace_checkout>/sase/repos/sase--plans       # repo sase-org/sase--plans
> <workspace_checkout>/sase/repos/sase--research    # repo sase-org/sase--research
> ```
> The `<project>--` prefix is pure noise inside a workspace that already belongs to exactly one project: every path a user
> or agent types (e.g. `@sase/repos/sase--plans/202607/foo.md` in prompts) repeats the project name.

*See full plan file for details.*

