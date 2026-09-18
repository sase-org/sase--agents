# Chat History - ace-run (research.5.cld)

- **TIMESTAMP:** 2026-09-18 07:59:22 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260918_073408.md`

## Prompt

%id(cld, clan=research.5) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.5.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I've yet to go a single night on this machine or on the
athena machine where all of my sase agents (including all agents for all launched epics)
continued moving along smoothly through the night. One always fails or doesn't close a
bead (so the dependent phase agents for that epic don't start) or there is some other
issue.

Can you do some research on the sase agents that ran last night on these machines, with
the goal of helping me prevent these types of failures and epic stalls in the future?
End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

I'm collecting last night's agent runs on apollo, and next I'll get SSH access to athena.

I'm writing a script to summarize every agent run from last night on both machines.

Now the summarizer script:

I'm pulling notifications and bead state on both machines to see which runs failed or left beads open.

Found one clear stall on apollo: a phase agent finished but deliberately left its bead open. Now checking athena's notifications.

Root cause of the athena failure: the follow-up agent was launched with an invalid model (`codex/gpt-5`). I'm checking how often that happened.

The failing agent had passed an invalid `--model codex/gpt-5` to `sase monitor start` on its own. Next I'm checking the bead status of every overnight phase agent.

The user was up at 3:16 AM unsticking `sase-11y.2.1` by hand. I'm now checking how land agents are supposed to close ancestor epics.

Confirmed a code gap: closing a follow-up epic auto-closes a parent *phase*, but never a parent *epic*. Now checking what the land-agent prompt tells agents to do.

Next I'm checking why athena's land agent skipped closing its parent epic, even though the prompt tells it to.

The skill doc itself lists `codex/gpt-5` as an example `--model` value, which is probably where the agent got it. Now checking why athena's land-agent monitor handoff disappeared.

Found a second pattern: land agents that "hand off" to a monitor that never actually starts. Checking whether `sase-11l.5.1.land--1` hit the same thing.

Two of roughly 30 overnight monitor starts on athena left no monitor record at all. I'm reading the monitor start code to see how that can happen.

I found 29 epics that are still in progress even though every child is closed, so nothing will ever close them. Checking whether an existing epic already covers the lost-handoff problem.

Athena's 8 runner slots are full this morning, which is why a few agents are still queued. Next I'm checking which overnight phase agents submitted `bead_action: keep`.

Scanning the last week of notifications on both machines to confirm these are recurring patterns and not one-offs.

Checking historically how often a phase agent finishes successfully but leaves its bead open.

The same class shows up on earlier nights: `sase-11h.4`, `sase-11i.6.4`, and `sase-11o.2` finished but left their beads open, and their land agents have been waiting since Sep 15–16. Checking why.

Apollo starts monitors in 2.5–5 s, athena in 23–68 s, so the race only realistically hits athena. Grabbing athena's load and CPU numbers for context.

I have enough evidence. Checking the research directory for filename collisions before writing the report.

There's an earlier research report on nested landing loops. Reading it through the audited artifact path.

I've got enough evidence to write the report now.

Before registering, I'm checking a few specific claims in the report against the code and data.

Fixing four things: the class name, the alert count, the overnight failure count, and the number of follow-up epics.

The report is formatted. Now I'm registering it as a durable artifact.

Registered. Now the required final declaration.

The report is written to `sase/repos/research/202609/overnight_epic_stalls_2026_09_17__b.md` and registered as `file:explicit:1eb45f0014c7519cc6731e74` (label `research:202609/overnight_epic_stalls_2026_09_17__b.md`). The commit declaration was accepted.

**What ran overnight (18:00 → 07:00 EDT).** athena started 157 agent runs (42 of them monitors) and apollo started 30. Only two runs failed outright, both on athena (03:10 and 06:18). Most of the damage came from runs that were reported as successful but left an epic stuck. Five epic chains stalled or needed you to fix them by hand, which you did at 03:16, 05:42 and 06:18–06:21. Three older epics (`sase-11h`, `sase-11i.6`, `sase-11o`) have been silently stuck since Sep 15–16.

**Four mechanisms caused every stall:**

1. **A phase finishes but leaves its bead open, and nobody is told.** The agent can't meet a criterion outside its control (an unpublished `sase-core-rs` release on PyPI, or a red host-wide check), so it adds a follow-up note, keeps the bead open and reports success. `wait_checks` only alerts when a dependency *failed*, so the phases waiting on that bead wait forever. That's what happened to `sase-zr.7.1.1.5.4.1` on apollo at 23:53: a 6-hour silent stall.
2. **Monitor handoffs get lost on athena.**
   - `sase monitor start` takes 23–68 s there, against 2.5–5 s on apollo. Codex hands control back to the model while it's still starting. The skill says "don't wait", so the model ends its turn and codex's exit kills the half-started command.
   - No monitor is ever created, and the run is still reported as successful.
   - This lost the parent-epic landing for `sase-11y.2.1` (you fixed it at 03:16) and for `sase-11l.5.1` (you closed it at 06:18).
   - The existing protection for gates and sudo (from `sase-11t`) doesn't cover monitor starts. The codex integrity check only fires when the final message is empty, and here it wasn't.
3. **A loud failure that nothing recovered from.**
   - An agent passed `--model codex/gpt-5`, copied from an example in the `sase_monitor` skill doc. That model is rejected on your ChatGPT-account codex.
   - The follow-up failed at 03:10 and the "can never self-resolve" alert went out at 03:12, but nothing acted on it. `sase-124.8.4.3` is still stuck.
4. **Land agents keep spawning nested child epics.**
   - Eight new ones were created last night. In September there have been 56 so far, against 73 top-level epics.
   - When a child epic closes, it auto-closes a parent *phase* but never a parent *epic*. Closing the parent is left to the model.
   - 29 epics are still in progress even though every child is closed, so nothing will ever close them.

Red checks on master, overload on athena (full slots, `just check-full` runs of 30–153 min with two timeouts) and six self-updates on athena during the night made all of this more likely.

**Recommendation.** Have sase itself check whether each epic is still moving, instead of trusting what the agent reports:

- **No silent success.** When a run ends with its assigned bead still open, record it as `completed_blocked` and send one high-priority "epic stalled" alert with relaunch / close anyway / cancel options.
- **Protect monitor starts.** `sase monitor start` should record what it's about to do before anything else. If the handoff never completes, the runner should replay it or fail the run loudly.
- **Bad models.** Reject an invalid `--model` while the starting agent is still alive, retry failed follow-ups with the inherited model, and fix the example in the skill doc.
- **A watchdog job every ~10 minutes.** Every open bead in a launched epic must have a live owner. If not, it relaunches or escalates once. This also covers the parent-epic close gap and gives you a triage list for the 29 stuck epics.
- **Stop creating stalls in the first place.** Require your approval for nested epics two or more levels deep, add a proper "blocked" state for beads, limit concurrent `just check-full` runs, and pause self-updates while epics are running.

The report shows that these fixes would have caught every stall from last night within minutes. It also lists the commands to recover the currently stuck epics.

I didn't file task beads, because researcher A is working the same data. Section 8 of the report lists eight candidates for the lead to file without duplicates.
