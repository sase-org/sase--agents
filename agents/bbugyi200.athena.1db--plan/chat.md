# Chat History - ace-run (1db--plan)

- **TIMESTAMP:** 2026-11-17 07:22:48 EST
- **MODEL:** claude/opus
- **AGENT:** 1db--plan

**Plan:** /home/bryan/.sase/plans/202611/axe_missing_script_during_code_swap.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/axe_missing_script_during_code_swap.md`

> # Defer axe script jobs whose script vanishes mid code swap
> ## Problem
> The axe error digest keeps reporting one-off failures like:
> ```
> Routine:    waits
> Job:        agent_auto_restart
> Error:      Job script not found: sase_job_agent_auto_restart (job: agent_auto_restart)
> ```
> These are races with a code swap, not real configuration errors:
> - 2026-11-17 07:15:51 (`agent_auto_restart`): a `sase dev update` was reinstalling the

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261117_071626.txt file for context. %m:@xlarge

## Response

Still digging: the failed run's record isn't in the run directory, so I'm checking where the missing-script outcome gets recorded and how the error digest picks it up.

Now loading the planning skill.

Writing the plan now.

Yes, we can and should fix this. I've proposed a plan for it, which is now waiting for your approval. Nothing has been changed yet.

**What happened:** this isn't a real missing script. The error fired at 07:15:51.72, the same moment a `sase dev update` was reinstalling sase with `uv tool install`. During that reinstall, uv briefly removes the old command scripts before writing the new ones. `sase_job_agent_auto_restart` was rewritten at 07:15:51.61 and its `~/.local/bin` symlink at 07:15:51.70. It exists now. The digest's only other recent case is the 11-16 10:21 `tg_outbound` error, and that one overlapped a `just install-dev` run.

`agent_auto_restart` gets hit most because its trigger watches `locks/code-swap-v2.lock`, the lock that updates and installs take. So the job wakes up exactly when its own script is temporarily missing. An earlier fix (also checking the venv's own `bin/` folder) doesn't help here, because that's the folder uv is rewriting.

**The plan (one agent, small):**
- **Swap check:** add a helper in `src/sase/dev_update/code_swap_lock.py` that says whether an update or install is in progress. It counts one only if the process holding the lock is still alive. It reads the lock file's contents and never takes the lock itself, so it can't hold up an update.
- **Runner change:** in `src/sase/axe/chop_runner_script.py`, when a job's script is missing *and* an update or install is in progress, record the run as `skipped` with a reason. It doesn't count as a completed run, and it doesn't reach the error digest. The job retries once the install releases the lock. If no update is running, or the check itself fails, a missing script is still reported as `missing_script` as before, so genuinely broken setups stay visible.
- **Tests and docs:** tests for both the new check and the runner change, plus one sentence in `docs/reference/automation/scheduler-jobs.md`.

The plan deliberately doesn't change what `agent_auto_restart` watches. Watching that lock is how it catches agents that die around an update.
