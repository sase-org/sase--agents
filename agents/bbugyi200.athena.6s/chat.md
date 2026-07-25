# Chat History - ace-run (6s--plan)

- **TIMESTAMP:** 2026-07-12 11:47:50 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 6s--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-6s__plan-260712_113539.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_113539.md`

**Plan:** /home/bryan/.sase/plans/202607/linked_repos_clone_dir_migration.md


## Prompt

#gh:gh_sase-org__sase Can you help me migrate normal linked repos (i.e. not companion repos like `sase--plans`) to use the sase/repos/linked/ directory instead of the sase/repos/ directory?

- We should also start clearing the sase/repos/linked/ directory when preparing the workspace directory for sase agents (so we should delete exactly one workspace directory's linked repo clones before every sase agent launch).
- With that said it would be nice if we didn't have to pay the full cost of cloning linked repos every time an agent calls the sase workspace open command. Try your best to keep make this fast somehow.
- This change should come with no backward compatibility code but you should go through all of the sase projects on this machine (run the `sase project list` command to find these) and delete any sase/repos/ subdirectories that correspond with linked repos associated with that project.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/linked_repos_clone_dir_migration.md`

> # Migrate Normal Linked Repo Clones to `sase/repos/linked/` (with Launch-Time Clearing + Fast Restore Cache)
> ## Problem & Goals
> Today every host-scoped clone lives directly in `<workspace_checkout>/sase/repos/<name>`, mixing two very different
> kinds of repos:
> - **Companion repos** — the SDD storage repos (`<project>--plans`, `<project>--research`). These are managed by the SDD
>   store, must persist across agent runs, and are prepared/committed by SDD machinery.
> - **Normal linked repos** — explicitly configured `linked_repos` entries (e.g. `sase-core`, `sase-github`, `sase-nvim`,
>   `sase-telegram` in this project's `sase.yml`, plus the global `chezmoi` entry, and `bob-plugins` for the bob-cli
>   project). Agents are supposed to access these only through the audited `sase workspace open -r "<reason>"` flow.
> Because normal linked clones persist across launches, an agent can wander into a stale clone from a previous run without

*See full plan file for details.*

