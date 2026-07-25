# Chat History - ace-run (7q--plan)

- **TIMESTAMP:** 2026-07-13 08:42:52 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 7q--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7q__plan-260713_083210.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260713_083210.md`

**Plan:** /home/bryan/.sase/plans/202607/delete_workspace_repos_dir.md


## Prompt

#gh:gh_sase-org__sase We currently delete the sase/repos/linked/ directory during workspace directory preperation in order to ensure that linked repos that were opened by previous agents in this workspace are not visible to the new agent we are about to launch. Can you help me start just deleting the entire sase/repos/ directory instead? This means that we will need to automatically clone the companion repos that are configured to auto-clone (currently just the `plans` repo) after deleting this directory but before launching the new agent. Make sure we are smart about this auto-cloning so we don't take too much of a performance hit for this.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/delete_workspace_repos_dir.md`

> # Delete the entire `sase/repos/` directory during workspace prep
> ## Problem & Context
> Workspace-directory preparation currently clears only `sase/repos/linked/` before launching a new agent (by renaming
> linked clones into the internal `sase/repos/.linked-cache/`, introduced in commit `df60999b5`). Everything else under
> `sase/repos/` survives across launches:
> - `sase/repos/plans` and `sase/repos/research` — durable SDD companion clones.
> - `sase/repos/.linked-cache/` — the rename-based stash of previously-opened linked clones.
> - Legacy junk from older layouts (e.g. a stale `sase/repos/<project>--plans` dir from the pre-`df60999b5` naming) that
>   nothing ever cleans up.
> This is both an isolation hole and a hygiene problem:

*See full plan file for details.*

