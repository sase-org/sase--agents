# Chat History - ace-run (sase-95.7)

- **TIMESTAMP:** 2026-07-25 11:27:43 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-95.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-95, bead=sase-95.7)
%model:@small_phase_worker
%auto
%w:sase-95.4
%w(bead=sase-95.4)
Can you complete the work for bead sase-95.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me implement. First `epic_launch.py`:

Now replace the detached spawn with the task submission:

Now the worker path:

Now add the helper functions:

Now the consequence text and docs:

Now update the tests:

Now update `tests/test_bead/test_epic_launch.py`:

Done — bead `sase-95.7` is closed.

## What changed

**`src/sase/bead/epic_launch.py`**
- Replaced `spawn_detached_epic_launch()` (and its `_DetachedEpicLaunch` result) with `submit_epic_launch_task(plan_file, *, cwd, artifacts_dir, cl_name, session_id)`, which calls `sase.tasks.runner.submit_task()` directly with argv `[sys.executable, -m sase.bead.epic_launch --worker …]`, label `Epic launch · <plan stem>`, tags `epic`/`launch`, `origin="epic-launch"`, and the approval's `cl_name`.
- Session attribution defaults to `resolve_session_ref(None)` — the resolving ACE session, else the newest live one, else unattributed — and is best-effort (a failure runs the task unattributed rather than blocking the launch).
- `_run_detached_worker()` now runs `sase bead work` with **inherited** stdout/stderr under the supervisor (live output in the task log) when `SASE_TASK_LOG_PATH` is set, and reads that retained log (active + rotated) back for parsing and for the notification's `extra_files`. `--log-path` is still accepted and takes the old private-log path, so a worker spawned by a pre-upgrade version still behaves. Parsing/metadata back-fill/`notify_workflow_complete` are unchanged.
- Because the supervisor drains the log from another process, the post-exit read waits (bounded, 2s, success only) for the epic id to land rather than racing the drain thread.

**`src/sase/_plan_approval_epic.py`** — the `detached` branch submits the task; a submit failure now raises `PlanApprovalActionError("epic_launch_failed", …)` carrying the `sase bead work <plan> --yes-to-all` resume hint instead of returning a bare `False`. `skip`/`foreground` and the return-value contract are untouched; `response_dir` is kept for callers but no longer used (log capture belongs to the supervisor).

**`src/sase/plan_approval_choices.py`** — the epic consequence text now names where the task is visible (`sase task list` / ACE Tasks tab). **`docs/sdd.md`** — documents the durable task, its session attribution, and the equivalent hand-run `sase task run --label 'Epic launch · <plan>' -- sase bead work <plan> --yes-to-all`.

**Tests** — extended the existing suites: submitted argv/label/tags/origin/session, session resolution and the unattributed fallback, inherited-output worker with `extra_files` pointing at the task log, and the retargeted approval-path tests (host claim recorded before submit, submit failure keeps the durable claim, store health checked before submit).

## Verification

`just install`, `just check`, `just test` — 21934 passed, 7 skipped. One note: `just check`'s `sase validate` step fails on `init skills --check` (5 `sase_beads` provider SKILL.md files drifted in the chezmoi repo). I confirmed that failure predates this change by re-running it against a stashed tree, and it touches no file in this bead's scope, so I left it alone rather than writing to the chezmoi repo.

I did not commit, and left the parent epic `sase-95` open.

Bead is already closed. Committing now.

Committed and pushed; working tree clean and level with `origin/master`.

- **Commit** `441882db9` — `feat(beads): route approved epic launch through the task runner (sase-95.7)`, covering the six files from the finalizer list.
- **Bead** `sase-95.7` was already closed before the commit (verified via `sase bead show`); the commit's own close step was idempotent. Parent epic `sase-95` left open.
- One warning at the end: the primary commit and push succeeded, but agent-hood publication for hood `kq` deferred ("committing agent 'kq' is absent from project inventory") and will retry automatically. Nothing to do on my side.
