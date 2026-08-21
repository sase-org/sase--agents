# Chat History - ace-run (09e.f0--code)

- **TIMESTAMP:** 2026-08-21 11:27:20 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 09e.f0--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-09e_f0__plan-260821_110357.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-09e_f0__code-260821_110357.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @sase/repos/plans/202608/optional_research_swarm_priority.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement the approved opt-in `#research_swarm` priority plan, starting with the repo-open skill and the xprompt/artifact memory this change depends on.

Next I’ll open the research-artifacts repo and load the xprompt, skill, and artifact notes this change depends on.

The research-artifacts checkout is open. I’ll inspect the swarm xprompt, tests, and docs next so the priority input matches the existing contract.

I’ll check how other xprompts handle nullable int inputs and `%wait(priority=...)` so this matches the existing expansion contract.

The source template still has no priority input, so I’ll add the nullable `int`, the Jinja `is not none` guards, and the matching tests and docs.

Install is still running because the local Rust core build takes a while; I’ll wait for it to finish before running tests.

That install ran in the SASE workspace, not the research-artifacts checkout. I’ll install and test from the opened repo next.

The second install was still in the SASE workspace. I’ll stop it and run install from the research-artifacts repo.

The research-artifacts env is installed. I’ll run the xprompt tests, then the full lint and test gates.

Lint and tests passed. I’ll gather the finalizer context and check which repos actually changed.

`#research_swarm` now has an opt-in `priority` input. A supplied integer is applied to all four swarm agents; omitting it leaves them on SASE’s implicit queue priority.

The change lives in `sase-research-artifacts`:

- `priority` is a typed `int` with YAML `null` default. Each of `cdx`, `cld`, `final`, and `image` renders `%wait(priority=N)` only when `priority is not none`, so `0` is a real priority rather than omission.
- `wait` is unchanged: it still gates only the two researchers. The lead still waits on both, and the image agent still waits on and forks from the lead.
- README and `docs/xprompts.md` document the optional integer, that it applies to every member, and that omission does not override implicit priority.

Validation: `just test tests/test_xprompt_loading.py` (12 passed, including omit / `5` / `0` / `wait` composition) and `just check` (ruff, mypy, 37 passed). No leftover “defaults to 20” or always-emitted-priority claims.

A commit declaration was submitted for the research-artifacts repo with:

`feat: add opt-in priority input to #research_swarm`
