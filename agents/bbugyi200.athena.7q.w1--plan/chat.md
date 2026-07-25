# Chat History - ace-run (7q.w1--plan)

- **TIMESTAMP:** 2026-07-13 09:57:14 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 7q.w1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7q_w1__plan-260713_094059.md`
- 2. --epic — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260713_094059.md`

**Plan:** /home/bryan/.sase/plans/202607/projects_repos_workspaces_redesign.md


## Prompt

#gh:gh_sase-org__sase %w:7q Can you help me reinvent / redesign some concepts in sase around projects/repos/workspace directories?

- sase "projects" are created only when the user specifies a new argument to a VCS xprompt workflow that resolves to a
  valid project name (for `#git`, any project name that uses valid characters is accepted; for `#gh`, the project
  name/argument must be a valid existing GitHub repo of the form `<org>/<repo>`).
- sase "repos" are any repo known by sase. This includes main/primary project repos (so _some_ repos are associated directly with
  projects), companion repos (these should be renamed to "sidecar" repos--replace all references), and linked repos.
  Notably, this does NOT include workspace repos/directories.
- sase "workspaces" are the same thing as workspace repos/directories. Each sase agent claims a single workspace before
  launch that it does not release until completion. Workspaces are always associated with a main project repo.
- Add these new terms (projects, repos, and workspaces) to the memory/glossary.md file. Define them all under the same
  glossary entry.
- The "Projects" tab of the "SASE Admin Center" should be re-designed. Namely, it should now contain only 3 sub-tabs:
  "Projects", "Repos", and "Workspaces".
  - The "Projects" sub-tab should provide similar functionality to the current "ACTIVE" sub-tab that we have today. Make
    sure we only show true sase projects (as defined above) on this sub-tab (in #sshot, you can see that we are showing
    some non-projects on the "ACTIVE" sub-tab currently). Projects should only have two states, enabled and disabled
    (always enabled unless the user explicitly disables from the "Projects" sub-tab of the "Projects" tab). Both enabled
    and disabled projects should be shown on the "Projects" sub-tab. Two new keymaps should be added that allow the user
    to switch to the repos/workspaces tabs, respectively, and filter for repos/workspaces associated with the currently
    selected project.
  - The "Repos" sub-tab should show all valid repos and should be filterable using a valid project name (provide a nice
    project selection menu if the user decides to filter from this tab).
  - The "Workspaces" sub-tab should show all valid (i.e. already created by the `sase workspace open` command and
    associated with an enabled project--unless filtering for a disabled project's workspaces) workspaces / workspace
    directories.
  - Make sure you show as much useful and practical information as you can on these subtabs!
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

This is a large piece of work that should be split into phases. I'll let you decide how many phases to create, but
keep in mind that each phase will be completed by a distinct agent instance (i.e. a distinct `claude` / `agy` /
`codex` / `qwen` / `opencode` command). Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.

 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/projects_repos_workspaces_redesign.md`

> # Plan: Redesign SASE Projects / Repos / Workspaces + Admin Center Projects Tab
> ## Product context
> SASE's project-adjacent concepts have grown organically and are now muddled:
> - The Admin Center "Projects" tab (`ACTIVE / sibling / inactive / all` sub-tabs) shows **non-projects**: any
>   subdirectory of `~/.sase/projects/` is treated as a project by the Rust enumeration (`list_project_records` defaults
>   missing `PROJECT_STATE:` to `active`). Directories created only by `skill_uses.jsonl` telemetry (e.g. `basher`,
>   `symvision`, `toobig` in the 2026-07-13 screenshot) appear as "active projects" with warnings like "ProjectSpec file
>   not found" and "WORKSPACE_DIR is not set".
> - Linked-repo bookkeeping records (`PROJECT_STATE: sibling`) masquerade as a third project state even though linked
>   repos are not projects.

*See full plan file for details.*

