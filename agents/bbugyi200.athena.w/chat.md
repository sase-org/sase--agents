# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 19:54:25 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** w

## Prompt

#gh:gh_sase-org__sase I recently added a first demo video for sase. Can you do some research and determine, in your opinion, my three best next options for my three next demo videos? Use these descriptions with your /sase_run skill to propose the launch of three agents, each of which will be tasked with writing the VHS tape file that generates a video that adheres to this description. %m:claude/claude-fable-5

## Response

I'll research the existing demo setup first — the recent commit renaming the demo-video recipe suggests there's demo infrastructure to look at.

I have a good picture of the demo infrastructure now. Let me dig into the ACE feature surface and the existing seed script so my recommendations are grounded in what's actually demoable.

All three launch requests are submitted and awaiting your approval in the notification inbox. Here's what I found and why I picked these three.

**Research summary.** Your first demo (`sase_ace_prompt_input.tape`) covers the *launch ergonomics* story: xprompt completion, `@` file completion, and the multi-agent prompt stack ending on "Launch all". The original tooling research doc (`sdd/research/202606/sase_ace_demo_video_tooling_consolidated.md`) lists the remaining strong public beats as agent observability, ChangeSpec coordination, and durability/automation — and it happens that `demos/scripts/seed_sase_ace_demo` already seeds most of the state those need: four `nova--*` agent runs across codex/claude/gemini with completed and failed outcomes, plus five ChangeSpecs spanning the full WIP→Submitted lifecycle with hooks, commits, and comments.

**My three picks**, each now a pending `LaunchApproval` whose agent will plan via `/sase_plan` before writing the tape and regenerating `demos/out/` with `just demos -y`:

1. **Agents tab observability** (`launch-e23085a6`) — the core value prop: many agent runs on one keyboard-driven surface. Beats: seeded multi-provider rows with completed/failed contrast, `h`/`l` fold/expand, prompt/diff/tools detail panels, and a `z` panel zoom. Fully hermetic with today's seeder.
2. **PRs tab ChangeSpec lifecycle** (`launch-4912af38`) — the coordination story: one structured ChangeSpec per CL/PR. Beats: five color-coded statuses across the lifecycle, the rich `nova_prompt_input` detail (commits, PASSED hooks, comments, deltas), fold-mode section cycling, and optional query filtering.
3. **AXE automation dashboard** (`launch-2d0f2bc5`) — the always-on story: runtime/cycle status, lumberjacks/chops, and a bang-mode `!!` background command streaming output from a seeded deterministic script (no LLM latency). This is the only one with a feasibility question — the current tape runs with `-x` (no axe) — so the prompt explicitly tells the agent to investigate what renders hermetically before committing to beats.

Together with the prompt-input demo these complete a natural arc: launch → observe → ship → automate, one demo per ACE tab.

**What I considered and skipped:** an onboarding/tab-guide tour (the `tab_onboarding_quickstart` redesign is WIP as of today, so that demo would go stale immediately) and an Admin Center sweep (your research doc explicitly advises against config-heavy panels in early videos). Both remain good candidates for videos four and five.

No repo files were changed (request JSONs live in `/tmp` and `~/.sase/launch_requests/`), so `just check` isn't needed. Once you approve or reject the requests in ACE, the responses will land in each request's `launch_response.json`.
