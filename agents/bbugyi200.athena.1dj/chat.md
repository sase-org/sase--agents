# Chat History - ace-run (1dj)

- **TIMESTAMP:** 2026-11-17 11:49:00 EST
- **MODEL:** claude/claude-haiku-5-5
- **AGENT:** 1dj

## Prompt

#gh:gh_sase-org__sase Can you give me a quick breakdown of all of the cool functionalities that sase's
routines have? What are they good for and what makes them unique compared to other agent
harnesses? 
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
fully complete. %m:claude-haiku-5-5

## Response

I'll start by locating the routine code and checking that the research directory exists.

The glossary calls routines "Lumberjack" and the research repo already has a lumberjack note. I'll read the glossary entry, the existing research on it, and the research repo's conventions.

Routines are configured under `axe.routines` in the default config and implemented in `src/sase/axe/`. Next I'll read the docs, the default routine config, and the scheduler module layout.

The default config defines lanes of jobs with triggers, timeouts, and descriptions. The reference docs should explain the model, so I'll read the main scheduler pages next.

The jobs page is too large to read in one go, so I'll pull its section headings and then read the parts that matter most: triggers, guards, dedupe, fan-out, and launch proposals.

Next I'll read the default routine catalog, the housekeeping routines, and the axe overview, plus the blog posts that make the case for this design.

The AXE blog post and the orchestration post's sections on lumberjacks and competitors should show how the project frames routines against other harnesses. I'll read those.

The docs give me the design and the project's own framing. Before writing, I want to confirm a few specifics in code: trigger and guard kinds, restart backoff, the runner pool, and the dry-run path. I'll also confirm the research repo path using the sanctioned command instead of reading its files directly.

The research repo path matches the one you specified. I also want to check two things: the routine count, since the docs say nine but the config looks like it has more, and whether the repo already has comparison research on Gas Town and Gas City that I can cite.

The default config defines ten routines, while the docs say nine, so the page is stale. The plan-search call returned nothing, so I'll look for the existing Gas Town and Gas City research by filename and check the artifact-read usage.

The repo has a consolidated Gas Town comparison and a Gas City comparison. I'll read their final reports through the audited `sase artifact read` path, capped so they stay focused.

The existing Gas City report gives me a grounded comparison point: Gas City calls its equivalent "orders," with cron, event, and webhook triggers. I need to check whether SASE really lacks cron triggers before I claim that, along with the trigger and guard lists.

Confirmed: the trigger providers are `always`, `git.commits_since`, and `fs`, and no cron trigger exists in the scheduler config. I'll read the "schedule recurring work" guide so my examples match how a user actually adds a routine.

I have what I need. Before drafting, I'll confirm the target filename is free so I don't overwrite an existing report.

The report is written. Re-reading it against my sources, I found several statements that go further than the evidence, so I'll correct those: the TUI key list, the shared-runner wording, the Master Gate attribution, and the `refresh_docs` job name.

The report is written and corrected. Next I'll register it as a durable artifact, using the absolute path and the repo-relative label.

The artifact registered with exit 0. The SASE policy requires the `sase_final` skill as the last action before ending this turn, so I'll invoke it now.

Submission is required. The only dirty repository is `sdd:research`, which holds the one new report, and no bead is assigned. I'll submit a `commit` decision built from the manifest template, with a Conventional Commit message and the requested co-author trailer.

The routines research is written, registered as `research:202611/sase_routines_feature_breakdown.md`, and the research repo commit is declared and will land when the turn ends.

**Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/sase/repos/research/202611/sase_routines_feature_breakdown.md`
**Artifact:** `explicit:eafc2afe7f7976406bd28b6c` (registration exited 0). I did not pass `--move`.

**What routines are:** a routine is a supervised scheduler lane (`axe.routines.<name>`) that runs its jobs on a fixed interval. Jobs are external scripts. A script checks state and returns a JSON result that can propose agent launches. The runner, not the script, launches them, after triggers, guards, dedupe, and capacity limits are applied. Most ticks spend no model tokens.

**Capabilities covered in the report:**
- Structured launch proposals, with `wait_on` chains and clans.
- Triggers: `always`, `fs` (stat-based change detection), and `git.commits_since`, with checkpoint policies.
- Guards that inhibit a job while related agents or clans are running.
- Per-project fan-out with independent state, and dedupe that releases keys on failed launches.
- Dry runs, manual runs, and maintenance mode.
- Bounded restart backoff, crash-loop notifications, and agents launched into their own scopes so a scheduler restart doesn't kill them.
- Run history, the Services tab, and validated job reports that open as notifications.
- Lifecycle work: fail-closed `%wait` resolution, hook and mentor advancement, and bead triage gates.

**What sets it apart:** the sensor/actuator split (cheap deterministic scripts, metered agent launches), a single launch chokepoint, policy kept as config, and routines that manage work already in flight, not only new scheduled work.

**Where it falls short:** there are no cron, time-of-day, webhook, or event triggers, and jobs can't launch workflows directly. Gas City's "orders" cover those cases.

**Choices I made:**
- Read "sase's routines" as the scheduler's `axe.routines` lanes, which the glossary calls Routines (Lumberjack).
- Verified the config, trigger set, guard kinds, and restart backoff in code. The orchestrator-level claims, including systemd scope detach, are from the docs.
- Took the Gas Town and Gas City comparisons from the existing October 2026 research reports. I did not re-check those products.
- I did not verify Codex's or Claude Code's current features. The report says so.

**Things to know:**
- The default-routines docs say nine routines; the config defines ten. I left the docs alone and noted it in the report.
- The research repo commit is pending. The host creates it after this turn ends, so `git log` won't show it yet.
