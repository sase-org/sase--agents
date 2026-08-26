# Chat History - ace-run (0e1)

- **TIMESTAMP:** 2026-08-26 07:42:12 EDT
- **MODEL:** claude/opus
- **AGENT:** 0e1

## Prompt

#gh:gh_sase-org__sase We recently added paging support for the `sase bead show` command. Do we make sure that this is both fast and disabled by default when a sase agent is detected (e.g. if the `SASE_AGENT` environment variable is set--figue out the best way to detect if a sase agent is running or not)? If not, use your /sase_plan skill to plan the appropriate changes.


## Response

I'll investigate the current paging implementation for `sase bead show` before deciding whether a plan is needed.

The pager already has an agent check. Let me verify whether `SASE_AGENT` is actually the right detection signal and whether the fast path is truly fast.

Let me confirm empirically end-to-end.

Let me verify the agent guard holds even when a TTY *is* present (the case where the `isatty` short-circuit wouldn't save us).

Confirmed the guard works. Let me check the one path that bypasses it — explicit `--pager always`.

Already handled — no plan needed. Let me close out the turn properly.

`submission_required: false` — no repo changes this turn, so nothing to declare.

## Yes — both are already handled

The `SASE_AGENT` check is already in `src/sase/cli_pager.py:115`, added with the paging feature itself (`2ed9dc7c9 feat(bead): page show output and accept multiple ids`).

**`SASE_AGENT` is the right signal.** It's the established convention across the repo for "am I running inside a sase agent" — `launch_request.py:174`, `monitor/handoff.py:33`, `artifact_cli/read.py:311`, `pending_handoff_write.py:26`, `var_handler.py:378` all use exactly this. It's set by the launcher (`launch_request_planning.py:256`) and stripped from child environments by `agent/env_hygiene.py`. `SASE_AGENT_NAME` is the *identity* (who), `SASE_AGENT` is the *predicate* (whether) — the predicate is correct here.

**Verified empirically, not just by reading.** I ran `page_or_print` under a real pty so `isatty()` was true, monkeypatching `Popen` to record spawns:

| condition | pager spawned? |
|---|---|
| TTY + `SASE_AGENT=1` | **no** |
| TTY, no `SASE_AGENT` | yes |

And end-to-end: `sase bead show sase-j0` emitted all 786 lines directly with no pager, no hang.

**It's fast.** In a real agent shell stdout is a pipe, so `_paging_decision` returns `None` at `cli_pager.py:102` on the `isatty()` check — before `shutil.which("less")`, before any subprocess, before the `_estimated_display_rows` cell-width scan over the body. The `SASE_AGENT` check is the belt-and-braces path for providers that do allocate a pty. Overhead when disabled is effectively zero.

Test coverage exists at `tests/test_cli_pager.py:150` (the `agent=True` parametrize case asserts `calls == []`).

## One residual worth your call

`--pager always` bypasses the agent guard — the `SASE_AGENT` check sits inside the `if mode is PagerMode.AUTO` branch at `cli_pager.py:114`. I confirmed on a pty with `SASE_AGENT=1` that `--pager always` spawns `less -R`, and since `-F`/`quit-if-one-screen` is only added in AUTO mode (`cli_pager.py:138`) with `LESS=RX` rather than `FRX`, that `process.wait()` at line 90 has no timeout and would block indefinitely.

This is defensible as designed — `always` is explicit opt-in, and your question was about the *default*, which is correct. The only way an agent trips it is by deliberately passing `--pager always` on a pty-allocating provider. Mildly relevant: the parser epilog at `parser_bead_queries.py:370` advertises `sase bead show sase-64 --pager always` as an example, so an agent copying it verbatim is the plausible route in.

I didn't change anything, since nothing was broken relative to what you asked. If you want the `always` hole closed too, the fix is small — hoist the `SASE_AGENT` check above the AUTO branch (or force `-F` under an agent so `less` self-exits) — say the word and I'll plan or just do it. I also held off filing a task bead for it, figuring you'd rather decide than have one appear.
