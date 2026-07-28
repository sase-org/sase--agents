# Chat History - ace-run (sase-9s.8)

- **TIMESTAMP:** 2026-07-26 10:15:47 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-9s.8

## Prompt

#gh:gh_sase-org__sase
%id(8, clan=sase-9s, bead=sase-9s.8)
%model:@small_phase_worker
%auto
%w:sase-9s.6,sase-9s.7
%w(bead=sase-9s.6)
%w(bead=sase-9s.7)
Can you complete the work for bead sase-9s.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me build the harness.

Now the no-TUI approval (verification item 1):

Now the kill path (item 5):

Now let me start a slow detached launch and probe the live TUI against it.

Done. `sase-9s.8` is closed; the epic `sase-9s` is untouched.

## What I did

Built an isolated harness (redirected `SASE_HOME`/XDG dirs, a scratch git project with a real SDD store, real plan gates) and drove the full approval chain with real processes. The only stubbed seam was `launch_bead_work_agents` — so no provider agents spawned, while plan validation, SDD archive+commit, bead DAG creation, graph publication, metadata backfill, and notification all ran for real.

## Results — all five verification items pass

1. **No TUI** — Approved via the mobile/Telegram gate executor from a plain shell. One `detached` row, `session_id: null`, command literally `sase bead work <plan> --yes-to-all --artifacts-dir …`, visible in `sase task list` with no `--all`, reached `success`, `sase task show` carried the real launch output, beads `verify-1/.1/.2` created, `agent_meta.json` gained all four host fields, completion notification arrived. Also confirmed the original Defect 2 fix at the source: `project_dir` was populated from `SASE_ACTIVE_PROJECT_DIR` with no `CLAUDE_PROJECT_DIR` anywhere.
2. **From the TUI** — Exactly one row, `kind=detached`; no `tui`-kind row ever represented a launch. A *fresh* headless `AceApp` that submitted nothing rendered `◆ detached` markers and its top-bar indicator showed `⚙ 2` for two running launches.
3. **Survives the TUI** — Both launches were still running when the TUI exited and later reached `success`; still visible on reopen.
4. **Loud failure** — Action data with neither signal raised `epic_launch_failed` carrying the `sase bead work … --yes-to-all` resume hint; no task, no fallback.
5. **Kill path** — `sase task kill --json` → `killed`, `exit_code: -15`, no orphan process; re-kill was a `changed: false` no-op.

Plus dedup: two gates for the same plan returned the same task id.

## One gap found (not fixed — plan says file it, and you asked me not to create beads)

**Every epic-launch row records `origin: "api"`.** `submit_epic_launch_task()` takes an `origin` but nothing threads one through — `prepare_epic_launch()` has no origin parameter, and none of its three call sites pass one. Phase `launch`'s design makes `origin` the field that says where a session-less launch came from (`ace`/`telegram`/`cli`/`axe`), so today the surfaces can't tell a Telegram approval from an ACE one. Want me to fix it, or file a bead?

## Needs your call

The verification report is written to `sase/repos/research/202607/detached_epic_launch_verification.md` but is **uncommitted** — I don't commit unless you ask. Since the research sidecar is a lazily-materialized clone, say the word and I'll commit it so it isn't lost.

Bead is confirmed closed. Committing the verification report.

Done.

- **Bead `sase-9s.8`** — verified `[CLOSED]`. Epic `sase-9s` untouched, no new beads created.
- **Research sidecar** — `202607/detached_epic_launch_verification.md` committed and pushed as `59b9a9d docs: record detached epic launch verification run (sase-9s.8)`. Working tree is clean and in sync with `origin/main`.

One non-blocking note: `sase commit` reported that post-commit **agent publication** could not be queued — `project 'sase--research' was not found`. That's the ChangeSpec bookkeeping step, not the commit; the sidecar isn't a registered project, so `--resume` fails the same way. The commit and push themselves succeeded.

Still open from the verification run (your call, no action taken): every epic-launch task row records `origin: "api"` because nothing threads an origin through `prepare_epic_launch()` — the surfaces can't distinguish a Telegram approval from an ACE one. Want that fixed, or filed?
