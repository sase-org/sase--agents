# Chat History - ace-run (1l--plan)

- **TIMESTAMP:** 2026-07-07 23:22:01 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 1l--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-1l__plan-260707_230624.md`
- 2. --epic — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260707_230624.md`

**Plan:** /home/bryan/.sase/plans/202607/sdd_separate_repo.md


## Prompt

#gh:gh_sase-org__sase Can you help me start allowing sase VCS xprompt workflows to opt in to using a separate repo for their sdd files instead of storing them directly in the sdd/ directory? See the research in the sdd/research/202607/github_sdd_repo_consolidated.md file for inspiration but know that you are responsible for the final design so make sure you truly agree with any recommendations made in the research file that you choose to adopt.

This is a large piece of work that should be split into phases. I'll let you decide how many phases to create, but
keep in mind that each phase will be completed by a distinct agent instance (i.e. a distinct `claude` / `agy` /
`codex` / `qwen` / `opencode` command). Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.

 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/sdd_separate_repo.md`

> # Plan: Separate SDD Repository — Provider-Level Opt-In for VCS Workflows
> ## Product Context
> SASE stores prompt snapshots, plans, research notes, and bead state under `sdd/` in the main code repository when
> `sdd.version_controlled: true`, and in a local standalone git repo at `<primary>/.sase/sdd` otherwise. The goal: let VCS
> xprompt workflows (the `#gh`, `#git`, … workflow providers) **opt in** to a third storage mode where SDD artifacts live
> in a **separate companion repository** hosted alongside the code repo (for GitHub: `<owner>/<repo>-sdd`, e.g.
> `sase-org/sase-sdd`), cloned locally into `<primary>/.sase/sdd`. BareGit keeps its current in-tree behavior. Providers
> that don't opt in see zero change.
> Design source: `sdd/research/202607/github_sdd_repo_consolidated.md`. This plan adopts its core recommendation
> (companion repo cloned into `.sase/sdd`, policy enum + resolved store, provider-declared opt-in, materialization hook)

*See full plan file for details.*

