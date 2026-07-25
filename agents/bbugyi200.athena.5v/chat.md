# Chat History - ace-run (5v--plan)

- **TIMESTAMP:** 2026-07-11 13:39:15 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 5v--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-5v__plan-260711_132642.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260711_132642.md`

**Plan:** /home/bryan/.sase/plans/202607/unified_plans_dir_tier.md


## Prompt

#gh:gh_sase-org__sase We currently store epic plan files in the sdd repo's epics/ directory and plan files in its tales/ directory. Can you help me start only using a new plans/ directory instead and storing all tales and epics in that directory?

- We should be able to use the `tier` frontmatter field to determine which plan files are tales and which are epics.
- Make sure the `sase plan list` command has great support for displaying and filtering by tier.
- The `sase sdd init` command should handle this migration for us and set the `tier: tale` field for any tale plan files that don't have a `tier` property (among other fixes--you determine what's necessary).
- We will want to start making sure that this tier property is always added to plan files in the future.
- There are likely a lot of edge cases to cover here so make sure you consider them all.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/unified_plans_dir_tier.md`

> # Plan: Unify SDD `tales/` and `epics/` into a single `plans/` directory keyed by `tier` frontmatter
> ## Context
> Today, SDD plan artifacts are classified by their storage directory: task-level plans live in
> `<sdd_root>/tales/<YYYYMM>/*.md` and larger multi-phase plans in `<sdd_root>/epics/<YYYYMM>/*.md` (with `research/` as a
> third, unrelated kind). This directory-based classification is duplicated everywhere: the Rust core's plan discovery
> (`crates/sase_core/src/plan/read.rs` `REPO_PLAN_KINDS`), Python link validation (`sase/sdd/links.py`), path aliasing
> (`sase/sdd/_paths.py`), the write paths (`sase/sdd/_write.py`, `sase/plan_approval_actions.py`,
> `sase/workflows/commit/commit_hooks.py`, `sase/axe/run_agent_exec_plan_sdd.py` / `run_agent_exec_plan_accept.py`, the
> ACE TUI approval modals), diff badges, the commit finalizer, generated READMEs, skill templates, and bead examples.
> We want a single canonical `plans/` directory where the `tier` YAML frontmatter field (`tale` | `epic`) is the source of

*See full plan file for details.*

