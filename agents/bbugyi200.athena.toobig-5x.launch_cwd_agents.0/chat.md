# Chat History - ace-run (toobig-5x.launch_cwd_agents.0)

- **TIMESTAMP:** 2026-09-23 08:11:02 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5x.launch_cwd_agents.0

## Prompt

%id(launch_cwd_agents.0, clan=toobig-5x)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/launch_cwd_agents.py` file up into multiple files? Use your best
%wait:toobig-5x.agent_display_clan_sections.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 710-line `src/sase/agent/launch_cwd_agents.py` into five modules, all under 500 lines:

- [launch_cwd_agents.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/agent/launch_cwd_agents.py:25) (235 lines) — thin orchestrator: prompt canonicalization, project-context resolution, then dispatch. Keeps the public `launch_agents_from_cwd_impl` entry point unchanged.
- [launch_cwd_segments.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/agent/launch_cwd_segments.py:1) (117) — `---`/ACE-unit/xprompt-swarm expansion with per-slot env metadata.
- [launch_cwd_guards.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/agent/launch_cwd_guards.py:1) (110) — the three pre-spawn policy guards. Logger name pinned to the old module so existing log filters and tests keep matching.
- [launch_cwd_fanout.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/agent/launch_cwd_fanout.py:1) (273) — multi-prompt, `%r:N` repeat, and alt-split branches.
- [launch_cwd_single.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/agent/launch_cwd_single.py:1) (177) — VCS/workspace resolution and single-agent execution.

Pure code move, no behavior change. Verified with 98 passing tests across the launch path (guard, repeat, force-reuse, multi-prompt e2e/launch/groups/fork, bead-work), plus clean `ruff check`, `ruff format --check`, and `mypy` on all five files.
