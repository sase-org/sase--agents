# Chat History - ace-run (ex)

- **TIMESTAMP:** 2026-11-18 10:15:08 EST
- **MODEL:** claude/opus
- **AGENT:** ex

## Prompt

#gh:gh_sase-org__sase I ran two epic chains last night (one on the bob-cli project and one on this
project). Each epic worked the 5 next most important task beads for that project. Can
you do an audit of what work was done related to these two epic chains? Was any work
done that maybe shouldn't have been done? Make sure your report is concise, easy to
understand, and contains great visuals. 
Write this research to a new markdown file under the /home/bryan/projects/github/sase-org/sase/sase/repos/research/202611/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge %q(w=0.3)

## Response

Found the sase chain's first epic (`sase-1tc`, "Backlog epic 1"). Now reading it and tracing what came after it.

Located both chains' homes. Now pulling the bob-cli side: its beads and overnight commits.

bob-cli ran a 4-epic chain (T1→T4, T4 still running); sase's chain is on its first epic. Reading each bob-cli epic now.

The chains actually ran on athena, not this machine. Checking synced transcripts for those agents.

Commits carry `SASE_AGENT`/`SASE_MODEL` trailers, so I can attribute every commit. Extracting them for both repos.

Reading the T2–T4 plan bodies to see what each lander chose and whether you got an opt-out decision.

Got full bead JSON for sase. Dumping bob-cli's too, then I'll compute who closed what since the chains started.

Both bootstrap agents batch-closed beads before starting (sase: 35, bob-cli: 28). Pulling their close evidence to spot-check those closures.

Bootstrap closures hold up (cited commits exist and match). Now building the per-epic phase timeline for both chains, with timezones normalized.

The chain's cmdsub phase introduced `GeneratedTextGuard`, and a separate agent (`1dr`) later fixed guard markers leaking. Checking whether that was a chain regression.

Checking whether a chain phase (n7.1) introduced the `cargo fmt` failure a later phase flagged.

Enough evidence gathered. Computing final per-chain tallies (commits, lines, agent runs) for the visuals.

Now loading the Mermaid skill before drawing the report's figures.

Now generating the Unicode timeline and effort charts for the report.

Now drafting and rendering the two Mermaid figures.

Figures render cleanly (fit ≥76%). One fact check before writing: who authored the marker-leak fix plan.

Confirmed (`1do` authored the fix plan). Writing the report now.

Report written. Fact-checking a few claims before registering: budget/skip changes in chain diffs, and the typed-admission file size.

Re-rendering the figures straight from the report file to confirm they still parse and fit after the label edit.

Both figures render and fit. Registering the report as a durable artifact.

I wrote the audit to `/home/bryan/projects/github/sase-org/sase/sase/repos/research/202611/overnight_backlog_epic_chains_audit.md` and registered it as artifact `file:explicit:75607fe5d0fd3b77d6647352` with label `research:202611/overnight_backlog_epic_chains_audit.md`. Both chains actually ran on athena from about 11:15 EST yesterday, and both are still running as of about 10:00 today.

**The bob-cli chain went well; the sase chain is stalled.**

| | sase | bob-cli |
|---|---|---|
| Epics | 1, still running | 4 (T1–T3 closed, T4 running) |
| Chosen task beads closed | **0 of 5** (2 are fixed but still open) | **15 of 20** |
| Lines added by chain commits | about 13.6k | about 8.2k |

**Work that maybe shouldn't have been done:**
1. 🔴 **The sase cmdsub phase broke things in production.** Commit `efc66a420b` stopped `#research_swarm` from launching its image and linker agents (research.58 and .59 got 6 agents instead of 8). It also let a local helper macro's output run as a host `$(cmd)`, the same kind of hole the phase was meant to close. Three agents outside the chain (`1dn`, `1do`, `1dr`) plus the epic's lander had to repair it. It's fixed now.
2. 🔴 **The sase chop-launch phase grew far too big.** It started from one past incident (59 of 61 launches lost) and became a 5-phase child epic, about 9.1k lines so far. One phase claimed the bug was fixed using a test that faked production data. The lander then found 11 defects in code that had already landed on master, including a possible double-dispatch race. A 4-phase repair epic is running, and the beads.db corruption fix (phase 4) is stuck behind it. This is the one I'd most question.
3. 🟠 **One bob-cli feature took 72% of that chain's code.** The scan-lock work (`bob-cli-mo`) was about 5.9k lines over 7.5 hours and needed two rescue rounds. You approved it through a plan decision, but it was by far the costliest pick in a bug-fixing chain.
4. 🟡 **Smaller items:**
   - One bob-cli phase found its task already fixed by another epic.
   - Several performance tests now measure CPU time instead of wall-clock time. That stops the flakes, but those tests won't catch slowdowns from blocking or waiting.
   - Two fixed sase tasks still show as `ready`, because only the outer lander closes them.

**Pattern:** all 3 phases sized "large" needed a rescue after claiming they were done, while all 14 small or medium phases landed cleanly. sase phases 4 and 5 are also sized large.

**What checked out:**
- The 63 beads the two chains closed in their up-front triage cite real fixing commits; 51 of 57 verified, and I found no wrongful closures.
- bob-cli T2 and T3 fixed 8 real bugs that wrote wrong data, each in 415 lines or fewer.
- T4's choice to fix the macOS CI failures (red on master since about 11-14) is high value.
- I found no chain commit that skipped tests or raised a test budget.

**Decisions for you:**
- **Chop-launch repair:** let the repair epic finish, or cap it and run the beads.db phase next.
- **bob-cli chain length:** it is set to keep going until every open task is closed. At 231 open, that's about 46 more epics, each approved without asking you unless it picks a feature.

The report includes a timeline, an effort-per-task chart, two diagrams and a commit appendix.
