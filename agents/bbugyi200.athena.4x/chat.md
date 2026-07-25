# Chat History - ace-run (4x--plan)

- **TIMESTAMP:** 2026-07-10 16:56:45 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 4x--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-4x__plan-260710_163651.md`
- 2. --epic — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260710_163651.md`

**Plan:** /home/bryan/.sase/plans/202607/fakey_provider.md


## Prompt

#gh:gh_sase-org__sase Can you help me design and implement a new fake agent CLI provider, named `fakey`?

- The CLI agent should have first-class support within sase and will be used to test sase agent launches and to test various expected agent CLI behavior, like failures (and sase agent retries), for example.
- This agent should have sane and useful defaults but should also be highly configurable. For example we should be able to configure it to fail with a specific failure message.
- As a first use case we should write some PNG screenshot tests using this agent CLI that demonstrate how agent retries work. Make sure that our ability to E2E test agent CLI failure retries is top-notch (if it's not already) by the end of this work (I plan to refine the way sase handles retrying failed agents soon, so good testing will be needed).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

This is a large piece of work that should be split into phases. I'll let you decide how many phases to create, but
keep in mind that each phase will be completed by a distinct agent instance (i.e. a distinct `claude` / `agy` /
`codex` / `qwen` / `opencode` command). Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.

 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/fakey_provider.md`

> # Plan: `fakey` — a first-class fake agent CLI provider for testing launches, failures, and retries
> ## Summary
> Add **fakey**, a deterministic fake agent CLI that ships with SASE itself (a `fakey` console script) plus a first-class
> `sase_llm` provider (`FakeyProvider`) so it launches, streams, fails, and retries exactly like `claude` / `codex` /
> `qwen` / `opencode` / `agy`. Fakey's behavior is scripted through a layered **scenario** system (sane defaults → env
> knobs → scenario file → prompt-embedded scenario block), giving both tests and interactive TUI sessions precise control
> over replies, failures (message, exit code, channel), delays, streaming, token usage, cross-invocation attempt sequences
> ("fail twice, then succeed"), and file-based sync barriers for deterministic E2E timing.
> On top of fakey we build the retry-testing story end to end: real-subprocess E2E tests of the retry pipeline
> (`run_agent_exec_retry.py`) and two tiers of PNG snapshot coverage for retry rendering — fixture-driven goldens of every

*See full plan file for details.*

