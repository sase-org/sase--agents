# Chat History - ace-run (4y--plan)

- **TIMESTAMP:** 2026-07-10 17:08:50 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 4y--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-4y__plan-260710_165209.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-4y__code-260710_165209.md`
- 3. --code-0 — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260710_165209.md`

**Plan:** /home/bryan/.sase/plans/202607/linked_repo_local_workspaces.md


## Prompt

#gh:gh_sase-org__sase We currently support a `worspace.strategy` config field for `linked_repos` that accepts a value of `none` to indicate that the linked repo's primary workspace directory should always be used. Can you help me get rid of this field completely and start having all linked repos use the same workspace strategy?

- The ability to set `none` as a linked repo's workspace strategy is only used for the chezmoi repo (configured in the ~/.local/share/chezmoi/home/dot_config/sase/sase.yml file).
- The only reason that I did this is because my chezmoi repo is a linked repo that is shared by multiple main sase projects.
- This means that if two different agents working on different sase projects but the same workspace number were to try to open a chezmoi workspace currently, the second one to open the workspace would wipe out the changes from the first one.
- We can fix this however, by starting to clone linked repo workspace directories locally in our current workspace directory. Let's use the new local (already ignored by git) .sase/workspaces/ directory for this.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/linked_repo_local_workspaces.md`

> # Plan: Retire `linked_repos[].workspace.strategy` — Local Per-Workspace Linked Repo Clones
> ## Problem
> Linked repos currently support a `workspace.strategy` config field with two values:
> - `suffix` (default): numbered linked workspaces are materialized under a **shared, project-key-derived root** (e.g.
>   `~/.local/state/sase/workspaces/<org>/<linked-repo>/<linked-repo>_<N>`). The path is keyed only by (linked repo,
>   workspace number) — it is completely independent of the _host_ project. Two agents working on **different main
>   projects** (or the linked repo's own project) that share a workspace number resolve to the **same checkout**, and both
>   agent launch (`prepare_linked_repo_workspaces_if_needed`) and `sase workspace open` run `prepare_workspace()` on it,
>   wiping the other agent's in-progress changes.
> - `none`: the linked repo's primary directory is always used directly. This exists **only** to protect the chezmoi repo

*See full plan file for details.*

