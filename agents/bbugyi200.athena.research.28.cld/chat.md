# Chat History - ace-run (research.28.cld)

- **TIMESTAMP:** 2026-09-22 11:32:11 EDT
- **MODEL:** claude/opus
- **AGENT:** research.28.cld

## Prompt

%id(cld, clan=research.28)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.28.mus`, `research.28.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We recently implemented the
`sase tool` command, which is just the first part of a larger plan (see the
sase_tool_epic_roadmap.md file in the research sidecar repo and the sase-135 epic bead
for context). I'm thinking about taking the next steps on this. Here's what I'm thinking
that those next steps should be:

- Add support for smoe way of enforcing that sase agents always use the `sase tool`
  command for certain commands. I want you to lead the design on this one, but one
  possible solution would be to implement a new `sase tool ensure-not-agent` command
  that commands (like the `just check` command, for example) could call at the start of
  their logic. This command could then fail if it detects a sase agent. Whatever
  solution we go with, make sure that sase agents are able to override this somehow (in
  case, for example, the `sase tool` command is broken).
- We should start making sase monitors wrap the command they run with the `sase tool`
  command. This should be possible since the `sase tool` command should be able to run
  any arbitrary command (you might need to implement this).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

I've read the roadmap; next I'm reviewing the sase-135 bead and the current `sase tool` implementation.

Now reading the monitor implementation and existing agent-detection env vars (e.g. `SASE_AGENT`, `SASE_MONITOR_ID` in the Justfile).

Confirmed a SIGKILL race between the monitor supervisor and the tool wrapper; now checking how monitors build their command argv (`proc_adapter.py`, `start.py`).

Still researching: I'm now sampling real monitor command history to see what monitors actually run.

Next I'm reading the relevant decision records and the lint/test memory to check the plan against settled decisions.

Checking the `sase_final` prepared-completion flow, since it binds a raw `just check` command that any wrapping must preserve.

Now prototyping the proposed recipe guard in a scratch dir to check `just` dependency ordering, the refusal path, and the bypass path.

Reproduced 5 out of 5 times: the supervisor's SIGKILL reaches the wrapper first and the TERM-ignoring grandchildren survive as orphans. Checking cleanup and how the ledger records it.

Confirmed: all 5 raced runs ended `lost`. Next I'm checking whether any `lost` runs in the real ledger still have live child process groups (orphan evidence).

Searching existing beads for duplicates of the two defects.

No duplicates and no causally related active epic (the cause is the closed `sase-135`). Checking the `bug` task type's required fields.

Filing the two bugs now (both as `open` drafts first, then marking them ready).

Created `sase-16a`; its push lost a race with a concurrent push, and the next mutation should re-sync. Filing the second bug.

Both bugs are filed (`sase-16a`, `sase-16c`). Before writing the report I'm confirming the chosen filename is free.

I have enough evidence. Writing the report now.

Report written. Registering it as an artifact now.

My bead is actually `sase-16b`. On `sase-16a`, my status update was a no-op (it was already `ready`), but I added a ref and a link that I need to remove.

My edge is the only one between `sase-16a` and `sase-16c`, so removing that pair is safe.

I'm doing the intended ref, link, and `ready` updates on the correct bead, `sase-16b`, and then rechecking `sase-16a`'s state.

My report cites `sase-16a` where it should say `sase-16b`. Fixing the report, then re-registering the artifact snapshot.

Re-registered. Now checking the beads checkout state and whether the stale link on `sase-16a` has cleared.

The link store now reports zero links for the pair, but `sase-16a`'s bead stream still holds an unmatched `link_added`. Running `sase bead doctor` read-only to see whether it detects this.

None of the doctor repairs address this, and agents must not hand-edit canonical bead events. Checking whether this link-removal defect is already filed.

No existing bead covers this. Taking a quick look at where `link_removed` events get written, so a bug report can name the root cause.

The notes are recorded. Next I'm confirming the bead store synced and both of my beads are `ready`.

Both beads are `ready` and the bead store is in sync. Checking both working trees before the final declaration.

I wrote the report and registered it (`research:202609/sase_tool_guard_and_monitor_wrap__cld.md`, snapshot `file:explicit:9550d11f1cbb65526b8cb11b`). The commit to the research repo is declared.

## Recommendation
Both steps are worth doing, but I'd reshape both. Two live bugs need fixing first.

**1. Enforcement: a shell guard in the recipe, not `sase tool ensure-not-agent`.**
- **Why not a `sase` subcommand:** the override exists for when `sase` is broken, and a guard written in `sase` breaks in exactly that case. It would also add ~0.3 s to every human and CI run.
- **What instead:** a ~20-line shell script, `tools/require_tool_run`, run as the first dependency of `check` and `check-full`. It only reads environment variables, so it doesn't need `sase` to work. I prototyped it: it refuses a raw agent `just check` before setup runs, and takes about 1 ms.
- **The rule:** an agent may run the recipe only inside `sase tool run` for that tool, or with a reason given. The override is `SASE_TOOL_BYPASS='<why>'`, and the reason is printed so it shows up in transcripts.
- **It can't use `SASE_TOOL_RUN_ID`:** `sase tool run` clears that when its ledger write fails, so the guard would refuse the very command the agent just ran correctly. `sase tool run` needs a new marker it always sets (I propose `SASE_TOOL_NAME`).

**2. Monitor wrapping: on by default, with exclusions.** Ad-hoc `sase tool run -- ARGV` already exists, so running arbitrary commands doesn't need new work.
- **Don't wrap epic launches.** They are 22% of monitors, and wrapping them would break tool runs for every phase agent they start.
- **Don't wrap a command that is already `sase tool run …`,** or each run gets recorded twice.
- **If the command is exactly a catalog tool** (e.g. `just check`), run it as that named tool rather than as an anonymous command.
- **Only change the command actually executed,** never the recorded monitor command, or prepared host completion (`-f`) stops matching.
- **Record the agent that started the monitor.** Today 13 of 17 monitor-owned runs have no agent attached.

## Bugs that block this (reproduced and filed)
- **`sase-16b`:** when a monitor times out or is stopped, it force-kills `sase tool run` before `sase tool run` can kill its own child. The whole `just check` tree keeps running unowned and the run is recorded as `lost`. This happened 5 out of 5 times. The same thing happens when a provider's Bash timeout kills the process group, and there were 17 verify-monitor timeouts on athena last week.
- **`sase-16c`:** epic phase agents inherit the running epic-launch monitor's ID, so their `sase tool run check` loses compact output and saved logs. Four such runs by `sase-135.7` are in the ledger now.

## Critique of the plan
- **Evidence:** in the two days since E1's guidance landed, about 90% of heavy `just check` calls in the sase repo are already wrapped. Most remaining raw calls are in sase-core and other linked repos, which have no tool catalog, so a guard in the sase Justfile can't reach them.
- **Why build it anyway:** it's cheap, and later stages depend on full coverage. E7 admission in particular can't safely refuse work if some heavy runs never pass through it.
- **Decision record:** this reverses the "bypass is measured, not enforced" clause of `decisions:record-before-admit`, so it needs a new decision record.
- **Delivery:** one small epic of about four phases (fix the two bugs and add the marker, the guard, the kill fix, then monitor wrapping), placed before E2. With wrapping in place, E2's `-H` becomes simpler to build.

## Things to know
- **Bead ID mix-up:** my first bead was created as `sase-16a`, but another agent's push won a race and my bead became `sase-16b`. Before I noticed, I added a reference and a link to their unrelated `sase-16a`. I removed both. Because of a separate link-removal bug, the stray link still shows on `sase-16a`. I didn't hand-edit the bead store; I noted the bug on the in-progress artifact-link epic `sase-yy.8.6` and left an explanatory note on `sase-16a`.
- **Ledger rows:** my timing test added three ad-hoc `sase tool run -- true` rows to athena's real ToolRun ledger. All other experiments used a throwaway `SASE_HOME`.
- **Tests:** I changed no sase source code, so I didn't run `just check`.
