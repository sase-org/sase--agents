# Chat History - ace-run (7b--plan)

- **TIMESTAMP:** 2026-07-12 18:12:52 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 7b--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7b__plan-260712_174754.md`
- 2. --epic — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_174754.md`

**Plan:** /home/bryan/.sase/plans/202607/max_running_agents.md


## Prompt

#gh:gh_sase-org__sase I want to add the ability to configure a maximum number of sase agents that are allowed to be running at any given time. Can you help me implement this?

- I want the user to be able to override this both in their personal config but also on a prompt-by-prompt basis using an xprompt directive.
- I think we can accomplish this by using a new `runners` keyword argument to the existing `wait` directive, so users can override this in prompts (a prompt that sets runners to 0, for example, would wait until there are no agents running before it runs). 
- We should have a sase configuration field that defaults to 10 for this.
- While waiting for other agents to finish, we should use the standard waiting agent status for this, but make sure that it is clear at a glance that an agent is waiting because of this new configuration / `wait` key word.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! 

This is a large piece of work that should be split into phases. I'll let you decide how many phases to create, but
keep in mind that each phase will be completed by a distinct agent instance (i.e. a distinct `claude` / `agy` /
`codex` / `qwen` / `opencode` command). Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.

 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/max_running_agents.md`

> # Plan: Global Cap on Concurrently Running Agents (`max_running_agents` + `%wait(runners=N)`)
> ## Goal
> Add the ability to limit how many sase agents may be RUNNING at any given time:
> 1. A new user-config field, **`max_running_agents`** (top-level in `sase.yml`, int, default **10**, minimum 1).
> 2. A new **`runners=` keyword argument on the existing `%wait` directive** for per-prompt overrides (e.g.
>    `%wait(runners=0)` waits until _no_ agents are running before starting).
> 3. Agents held back by the cap use the **standard `WAITING` status**, but the display makes it clear at a glance that
>    they are waiting for a _runner slot_ (not a dependency or time floor), including a live "running / allowed" readout
>    and queue position.
> The feature must be **intuitive** (one mental model shared by config and directive), **reliable** (race-free admission,

*See full plan file for details.*

