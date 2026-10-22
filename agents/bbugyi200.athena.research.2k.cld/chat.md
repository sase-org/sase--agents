# Chat History - ace-run (research.2k.cld)

- **TIMESTAMP:** 2026-09-25 17:10:22 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2k.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_162143.md`

## Prompt

%id(cld, clan=research.2k)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2k.cdx`, `research.2k.grk`, `research.2k.mus`, `research.2k.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

There was recently a
failure (30-60 minutes ago) on this machine that caused all sase agents to fail and
required me to restart all affected agents. Can you do some research with the goal of
auditing those failures and the actions that I took to rectify the situation? Continue
this research by exploring the different UX solutions I could consider adding to the TUI
in order to make recovering from these types of failures easier. End your analysis with
a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm going through SASE logs from 15:40–16:30 today to rebuild the failure timeline.

Found a likely trigger: at 15:08 the TUI crashed with an "agent scan wire schema mismatch: got 10, expected 9" error. I'm now checking the dev-update log to see what was installed then.

The root cause is confirmed: a dev update at 15:07 installed a sase-core-rs that emits agent-scan wire schema v10, while Python still expected v9. Next I'm matching the git history to the fix.

I've found the manual Claude Code session the user opened at 15:16 in the primary checkout to fix the broken `sase tui`. I'm pulling its full timeline of commands and conclusions.

The timeline is now clear. Next I'm checking what recovery affordances the TUI already has (retry, kill, bead work, restart, update) so the UX options build on existing primitives.

The audit picture is complete. Before writing, I'm checking two design hooks: whether failure stage and retry lineage are recorded, and how the existing provider auto-retry works.

Found an existing `sase core health` command that could serve as the probe. Checking what it verifies, then writing the report.

Filename is free. Writing the report.

Confirmed. Applying the count corrections.

Corrections applied. Now registering the report as a durable artifact.

Registration succeeded (`file:explicit:51716c3da6c86bef2753dc6f`). Submitting the final declaration.

I've written the report and registered it as a durable snapshot. My recommendation: build an **Incident Recovery layer** in four stages, with a safer update flow first.

**What broke.** At 15:02 you ran Update from the TUI. It moved sase-core to its latest commit, `2a0fc2a`, which is a breaking change from bead `sase-17m.8`. The update ignored sase's `sase-core-revision.txt` pin, which was still `c31b8cf`. The matching Python fix belonged to `sase-17m.9`, which was still in progress. The only check after installing was "does the core import", so the TUI restarted onto the mismatched build.
- From 15:06, anything that reads the agent list failed with "agent scan wire schema mismatch: got 10, expected 9": the TUI, `sase agent list`, background scheduler jobs, and agent startup.
- 9 agents died during startup, before any model turn ran. Waiting agents kept being released into the broken setup, and each death blocked the agents waiting on it.
- One more agent, `sase-19o.1`, failed after its commit landed, because of a second core bug in the artifact-index migration.
- The outage lasted about 63 minutes, until `d86bcc3ac` was pushed at 16:09. The TUI was down from 15:08 to 15:33.

**Your recovery.**
- **Worked well:**
  - The raw Claude Code session you opened in the main checkout at 15:16 was the decisive move. SASE's own agent launches were broken, so going outside it was right. It diagnosed the problem in 7 seconds.
  - The two `sbd work -Y` commands got all six epics moving again within 10 minutes.
- **Risky:** at 15:37 you ran `rm -rf sase_14`. The workspace log shows #14 had been handed to your new `0sc--plan` agent 36 seconds after you dismissed its old owner. The planner survived only because it writes its plan outside the workspace.
- **Costly:** `sbd work -Y` restarted 21 agents from their original bead prompts instead of resuming the failed turns, and showed no preview first. `sase-17d.12.2` went from its 7th turn back to turn 1, and waiting agents were killed when their waits could have been re-armed.
- **Busywork:** you marked 104 notifications read by hand.

**Still open:**
- `0rv.w0.f0.w0` has been waiting since 10:30 on a dependency that can never finish.
- `sase-17m.9` owns the same work the hotfix shipped, and was still running at 16:39. It may redo or conflict with the fix.
- `sase core health` reports an error on current master. `src/sase/core/health.py:198` still expects launch schema 1, but the fix bumped it to 2.

**Recommendation, in build order:**
1. **Safer updates:** check the new core build against sase's Python constants before switching to it, keep the last working build, check again after restart, and add a "Roll back last update" button. This alone would have prevented today.
2. **TUI safe mode:** when core and Python disagree, the TUI stays up. It shows the mismatch and offers rollback, a health check, and a fixer session opened in tmux outside SASE's agent launcher (what you did by hand).
3. **Incident banner and Recovery panel:** failures sharing an error are grouped into one incident, and one "Replay affected" action runs after a preview:
   - agents that died before starting are relaunched as-is, keeping name, workspace and checkpoint;
   - agents that failed after committing get their finishing step resumed;
   - blocked waiting agents are re-armed rather than killed.
   It also includes a workspaces view that knows who holds each workspace, and resolves all of the incident's notifications at once.
4. **Automatic pause:** new launches are held once repeated identical startup failures occur, and resume when the health check passes. Tripping on the third failure today would have avoided 6 of the 9 deaths.

The report also lists what would have happened today with each layer in place, where each piece should live between sase-core and the Python side, a suggested build sequence, and 7 other defects I found. I didn't file task beads for any of them.

The report was committed to the research repo.

Files are in `sase/repos/research/202609`:
- mass_agent_failure_recovery_ux__cld.md — registered as `file:explicit:51716c3da6c86bef2753dc6f`, label `research:202609/mass_agent_failure_recovery_ux__cld.md`
