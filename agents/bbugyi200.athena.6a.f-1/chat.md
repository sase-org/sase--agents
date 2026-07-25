# Chat History - ace-run (6a.f-1--plan)

- **TIMESTAMP:** 2026-07-11 18:50:11 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 6a.f-1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-6a_f_1__plan-260711_181617.md`
- 2. --plan-0 — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-6a_f_1__plan_0-260711_181617.md`
- 3. --epic — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260711_181617.md`

**Plan:** /home/bryan/.sase/plans/202607/sdd_split_into_linked_repos.md


## Prompt

#gh:gh_sase-org__sase #fork:6a Can you now help me migrate the sdd repo to two different linked repos (sase--plans and sase--research)? This will require us to improve and generalize the concept of a linked repo a little bit.

- We should add a new linked_repos.<repo>.auto_clone config field that specifies whether or not we should automatically clone a linked repo while preparing the workspace directory before launching the agent. This field should default to false but we should set it to true for the new sase--plans linked repo.
- Agents that set the previously mentioned config field should not have their descriptions added to any agent files (ex: AGENTS.md).
- The new plans linked repo will contain the flattened contents of the current plans/ directory and will also contain the beads/ directory.
- The new research linked repo will contain a flattened version of our research directory. Make sure that you update all of our current research xprompts accordingly, which I believe are defined in the chezmoi repo.
- One or more of the phase agents you assign should use GPT image to generate great infographics for these repos. These infographics should be included in the readme files that are generated when we generate the GitHub repos, which is something that the sase init commands should do.
- Both of these linked repos should be added by default for any repo that is sase managed, which is something that is controlled by a project local configuration field.
- This might be a large, tricky migration so make sure you think this through thoroughly.

This is a large piece of work that should be split into phases. I'll let you decide how many phases to create, but
keep in mind that each phase will be completed by a distinct agent instance (i.e. a distinct `claude` / `agy` /
`codex` / `qwen` / `opencode` command). Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.

 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/sdd_split_into_linked_repos.md`

> # Plan: Split the SDD companion repo into `--plans` and `--research` linked repos
> ## Product context / goal
> Today each SASE project stores durable planning context in a single SDD companion GitHub repo (`<owner>/<repo>--sdd`,
> e.g. `sase-org/sase--sdd`) cloned per-workspace at `.sase/sdd/`, containing `plans/<YYYYMM>/` (with nested `prompts/`),
> `research/<YYYYMM>/`, `beads/`, plus legacy `tales/`, `legends/`, `myths/`, and a generated `README.md` +
> `assets/sdd-directory-map.png`.
> This plan retires that single companion in favor of **two linked repos**, generalizing the linked-repo concept to
> support them:
> - **`<repo>--plans`** (e.g. `sase-org/sase--plans`): the **flattened** contents of `plans/` (plan files at the repo
>   root, prompt snapshots under a root `prompts/` directory) **plus the `beads/` directory**. Configured with the new

*See full plan file for details.*

