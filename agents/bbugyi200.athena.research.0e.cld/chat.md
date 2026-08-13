# Chat History - ace-run (research.0e.cld)

- **TIMESTAMP:** 2026-08-13 07:15:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0e.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260813_065838.md`

## Prompt

%id(cld, clan=research.0e) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I am in the middle of implementing sase monitors (see the sase-kp epic bead for context, which is still in-progress). Can you do some research with the goal of helping me improve this feature even further? End your analysis with a ranked list of recommended improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by understanding the current state of the monitor feature and the epic bead context.

I have enough evidence. Writing the report now.

Research written to `sase/repos/research/202608/sase_monitor_improvements.md` (opened the `sase--research` sidecar via `/sase_repo`; the sase repo itself is untouched).

## What I found

**The design is right; the supervisor is where it leaks.** Modeling a monitor as an ordinary agent-family member paid off exactly as the plan predicted — no new store, 289-line `store.py`, and family roster / runtime / chat / `#fork` all work for free. Test coverage is ~3k lines and solid.

The problems concentrate in one function, `supervise._stream_output()`, which drives both output streaming *and* timeout enforcement from a blocking `readline()` loop. I confirmed three failures by running the shipped code against real subprocesses:

| Command shape | Result |
| --- | --- |
| Continuous output | Timeout never fires — 12s into a 2s budget |
| Partial line (`\r` progress bars) | Supervisor blocks 8s on a 2s budget; nothing reaches `live_reply.md`, so "live output" isn't live |
| Backgrounds a grandchild | Monitor stays `running` 10s after the command exited; `stop` is silently dropped |

All three have one fix: `sase.tasks.supervisor` already does this correctly — child stdout goes straight to the log fd, with `child.poll()` on a 50ms tick. Adopting that shape *removes* code.

Three findings compound it: monitors persist the supervisor pid but never the command's **pgid** (tasks do), so a hard-killed supervisor strands an unkillable command tree and **wedges the lane** — and if the command string matches, `start_monitor()` silently returns the dead record as though it were live. The monitored command also inherits the dead starter's `SASE_AGENT`/`SASE_ARTIFACTS_DIR`, which every other subprocess boundary in the repo scrubs. And `live_reply.md` is uncapped on disk — the 2 MiB budget is memory-only, so the plan's "must not fill the artifacts store" isn't enforced.

One small, invisible one: inside an agent, `sase monitor start` **prints nothing** — `kill_agent_runner_group()` is `NoReturn`, so everything after it in the handler (including `-j/--json`) is dead code. The only test there asserts `handed_off is False`.

## Top of the ranked list

1. Replace `_stream_output()` with the `tasks.supervisor` shape — fixes 3 findings, net code removal
2. Persist `monitor_pgid`; use it for stop, escalation, reconciliation
3. Reconcile orphaned monitors in the axe scheduler (beside the existing stale-claim sweep)
4. Print the start summary *before* the handoff kill; test the in-agent path
5. Scrub agent identity from the monitored command's env — do this before `kp.9` lands, since `sase bead work` reads it

17 recommendations total; the report also covers idle-timeout as the highest-value *new* feature, the tight index-polling loops in `--follow`, and a deliberate revisit of the Rust boundary for the projection layer only.

I didn't file any task beads — several findings are in-scope for the open phases (`kp.8`/`kp.12`) rather than new work. Say the word and I'll run `/sase_new_task` on the ones that should stand alone.

I'll commit the research file I created in this session.

The untracked file is the research report I wrote this session. Committing it via the commit skill.

Another agent pushed a report at the same path. Let me inspect both sides.

Both sides are distinct, complete reports written in parallel at the same path. Upstream's is already pushed, so I'll keep it there and place mine at its own filename.

Adding a cross-reference so the two parallel reports on this topic are navigable.

Rebase clean, one commit ahead. Finalizing the stitch bookkeeping and push.

Committed and pushed.

## What happened

The commit hit a rebase conflict: another agent had researched the same question in parallel this session and pushed `8dff9fb docs: research monitor durability improvements` to the **exact same path** — `202608/sase_monitor_improvements.md`.

Both files are complete, independent reports against the same snapshot (`sase@22319c52d`), reaching compatible conclusions from different angles. Discarding either would lose real work, so I resolved it by keeping upstream's file untouched at the original path and moving mine to `202608/sase_monitor_supervisor_gaps.md`, with a short companion pointer added near the top so the two are navigable from each other.

**Result:** `7d935f3 docs(research): analyze sase monitor supervision gaps` — 1 file, 482 insertions. `git status --short --branch` reports `## main...origin/main` with no ahead/behind and a clean tree, so it is committed and pushed.

Two notes:

- The finalizer listed `research` twice (once as linked repo, once as SDD sidecar) but both point at the same path, so the single commit covers both entries.
- `sase_git_commit --resume` exited 0 with the primary commit and push succeeded; **agent-hood/prompt-archive publication was deferred** because the agents sync lock was busy. It is queued and retries automatically — no action needed, but that's the one piece I did not see complete.

I did not amend the commit message to name the new filename — amending after the rebase would have changed the SHA that the deferred stitch bookkeeping had already recorded. The message body describes the findings accurately regardless of path.
