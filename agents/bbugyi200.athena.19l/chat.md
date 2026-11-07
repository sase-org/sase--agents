# Chat History - ace-run (19l)

- **TIMESTAMP:** 2026-11-07 09:33:36 EST
- **MODEL:** claude/opus
- **AGENT:** 19l

## Prompt

#gh:gh_sase-org__sase Why are these artifact backfill errors occurring? See the
~/.sase/axe/error_digests/digest_20261107_084222.txt file for context. Make sure your
report is concise, easy to understand, and contains excellent visuals. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.
%m:@xlarge

## Response

I have enough evidence. Next I'm loading the diagram guidance, then writing the report.

Writing the report now; the drain-cost diagram renders cleanly at 79.9% page fit.

Report written. Now registering it as a durable snapshot.

Registration succeeded. Finishing the turn through the SASE finalizer.

The backfill keeps timing out because one step in it, the "outbox drain", does work that grows every day and can't be stopped early. In the 07:42 run it was still draining the **sase** project when axe killed it at the 300 s limit. Since 2026-10-29 this has happened 21 times, and every one was killed in the same place.

**Why it's slow.** For each queued outbox row, the drain checks whether that agent run earned "release evidence" (proof it made a qualifying commit). It does this by re-reading and re-parsing the entire evidence file once per row (`src/sase/sdd/artifact_link_release_evidence.py:98-105`).
- For sase that is 12,889 rows × 4,172 evidence lines, about **108 s** measured.
- **None of those rows match.** Neither do bob-cli's 5,923.
- Reading the evidence file once into a lookup set does the same check in **25 ms**.
- The drain also rebuilds the whole agent catalog for each project. That took 4–44 s in my timings.

**Why the 240 s budget doesn't help.** The drain checks the job's deadline only once, before these loops (`_artifact_link_outbox_drain.py:124`). Every successful run today still took 240–262 s, which leaves only about 40–60 s before the kill. At 07:42, bob-cli's drain took 154 s instead of its usual ~30 s. That pushed sase's drain to start at about 216 s, under the 240 s check, and nothing could stop it before 300 s. The exact reason bob-cli was slow is likely a cold catalog rebuild or CPU contention, but I couldn't prove it because the logs don't time steps inside the drain.

**It will get worse.** Almost all rows are records of read-only agents reading files. Those agents never commit, so their rows never get evidence and are only dropped 90 days after the agent finishes. The oldest row is 58.8 days old, so nothing can be dropped before 2026-12-08. The sase queue grows about 340 rows a day. I project it will exceed the whole budget on its own within about 30 days, and runs will time out much more often well before that. Even "successful" runs already skip sase's reconcile/repair step for lack of time (3 of the last 5).

**Fixes, highest leverage first:**
1. Read the evidence file once per drain and check rows against an in-memory set. This saves about 125 s per run, roughly half of today's runtime.
2. Skip the catalog rebuild when no row is old enough to drop, and build it at most once per run.
3. Check the deadline inside the drain loops, so a slow run stops early and logs it instead of being killed.
4. Move dead rows out of the active queue instead of keeping them for 90 days.
5. A minor bug: the once-a-day recheck of parked rows never saves its timestamp, so those rows are rechecked every hour (`_artifact_link_outbox_drain.py:499`).

The report has a timeline chart, a Mermaid diagram of the drain, cost and growth tables, and the method.
- **Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202611/artifact_link_backfill_timeouts.md`
- **Registered snapshot:** succeeded as `file:explicit:9fc1c8a515d8f73991fd1bba`, labelled `research:202611/artifact_link_backfill_timeouts.md`.
- The research repo commit happens automatically after this turn ends.
