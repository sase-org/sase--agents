# Chat History - ace-run (research.4n.cld)

- **TIMESTAMP:** 2026-10-16 11:30:40 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4n.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_110522.md`

## Prompt

%id(cld, clan=research.4n)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.4n.cdx`, `research.4n.grk`, `research.4n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to start making it fine for an agent to be launched using the `%id`
directive's `bead=<bead>` input even when `<bead>` is already closed.

- Currently, the sase agent just fails when this is the case which is annoying since I
  often restart sase agents using the `,x` keymap on the "Agents" tab after, for
  example, an error occurs that causes the agent to fail for some reason (sometimes the
  agent or the finalizer has already closed the bead at this point).
- We should make sure to add some kind of recognizable, timestamped note or annotation
  of some sort to the bead so there is a clear audit trail when we do this though.

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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm tracing where `%id(bead=...)` launches check bead status, so I can find exactly where closed beads get rejected.

Found the launch claim path (Python calls the Rust `claim_for_agent_launch`); now locating the closed-bead rejection inside sase-core.

Confirmed the rejection lives in sase-core's `run_claim_launch` (a hard `kind: "closed"` error). Now mapping the `,x` keymap and restart flow on the Python side.

Tracing the runner's claim sequence (wait-claim at bootstrap, then promotion at launch) to see every point a closed bead can fail.

Reading the `sase_beads` reference memory, since this touches the bead status lifecycle.

Checking how past bead wire additions (snooze status, reopen causes) handled cross-machine compatibility, since a new reopen cause is a wire change.

Checking which macros/templates generate `bead=` and what they tell agents about bead status.

Checking whether a bead or prior research already tracks this closed-bead launch failure.

Reading the `sase_flags` memory, since changing user-reaching launch behavior may call for a feature flag.

Confirmed an unknown bead event operation hard-fails older cores ("run `sase update`"), which shapes the wire design. Checking the Python binding/facade signature next.

Verifying one detail for the "leave it closed" alternative: what happens to a close note when re-closing an already-closed bead.

Let me measure how often this failure has actually happened, from agent run logs.

Searching agent run artifacts for real occurrences of the closed-bead claim failure (bounded by a timeout).

Found 11 real failures (Jul–Oct): 3 land agents (epic beads) and 8 phase agents. Checking bead histories to see if each close predated the relaunch, which tests my proposed rule.

That's strong evidence: `sase-131.4` was force-closed as **superseded** by the user ~1.5 min *after* its queued phase agent was submitted, so the refusal was correct. Classifying all 11 cases.

No ancestor was closed in any of the 8 legitimate relaunches, so an ancestor guard would have cost nothing on real data. Checking whether those relaunches carried the `!` force-reuse marker.

Strong empirical picture now. Checking where `%id(bead=)` is documented so the report can point at the docs that would need updating.

I have what I need. Grabbing exact line numbers for the code references in the report.

Writing the report now. First confirming my target filename doesn't already exist.

Writing the report.

Report written. Registering it as a durable artifact snapshot.

Artifact registered. Now submitting the turn's final declaration.

Allowing a launch on a closed bead is a good idea, but "always allow it" would have been wrong in 3 of the 11 real failures I found. I recommend reopening the bead only when it was closed before the launch was submitted. The full analysis is in `research/202610/closed_bead_launch_reopen_with_audit__cld.md`.

**Where it fails.** A single check in sase-core (`run_claim_launch`, `crates/sase_core/src/bead/mutation/claims.rs:108`) refuses to assign a closed bead to a launching agent. It runs just before the model starts, after the workspace is already set up, so the agent fails and leaves an error report.

**What actually happened.** Your agent run reports from 2026-07-26 to 2026-10-03 contain 11 of these failures. I compared each bead's close time with its launch time:
- **8 match your scenario.** The bead was closed before the relaunch was submitted, by the agent itself or by its epic's land agent, 7 minutes to 10 hours earlier.
- **3 were correct refusals.** The bead was closed while the agent sat queued:
  - you superseded it 86 seconds after launch;
  - a different agent finished the work 17 hours later;
  - someone closed it by hand while a land agent waited on it.

**Changes I'd make to your requirements:**
1. **Reopen, don't run around the bead.** "Fine" should mean the bead is reopened and set to in-progress for the new agent, in one step. Running an agent while its bead stays closed breaks the phase prompt's promise that the bead is already in progress.
2. **Only reopen closes the launcher could have seen.** Reopen only if the bead was closed at or before the launch was submitted. Closes that happen while a launch is queued still win. A deliberate relaunch afterwards then counts as the confirmation.
3. **Refuse if a closed parent epic would also have to reopen.** Nothing would close that epic again. This didn't happen in any of the 8 real cases.
4. **Two layers of audit trail, written in the same change as the reopen:**
   - an entry in the bead's existing close history (new cause `agent_launch`, recording which agent reopened it). This already shows up as the "Previously Closed" section and the ↺ badge.
   - a note with a fixed, searchable prefix, `LAUNCH REOPEN:`, containing the timestamps and the earlier close's details.
5. **Check before spawning.** Show a warning at submit time ("this launch will reopen sase-1ex.9, closed 1h46m ago"), and refuse immediately in the cases that would fail, instead of after workspace setup.

**Recommended implementation:**
- **In sase-core:** the claim mutation does the reopen, the close-history entry and the note together.
- **Compatibility:** record the new reopen cause as an optional extra field on the existing `issue_updated` event, not as a new event type. The beads store is shared across athena, apollo and the mac, and an un-updated core fails outright on an unknown event type (`jsonl.rs:925`), but ignores an unknown field.
- **In the sase runner:** pass the launch's submission time when claiming. Do not reopen during the waiting phase: if that wait were killed, the bead would drop back to "open" and the original close would be lost.
- **Prompt:** add one sentence to the phase and task prompts telling a relaunched agent to check whether the earlier run's work already landed.

**Two things I'd also consider.** Phase agents close their own bead in the middle of the turn, before the commit happens. Closing it only after the commit lands would prevent many of these failures in the first place. And in both original runs I spot-checked, the work was already done, so retrying only the failed finishing step would often be cheaper than a full relaunch.

**Decisions for you:**
- **Ancestors:** refuse (my recommendation) or reopen them like `sase bead open` does.
- **Healer auto-restart:** same rule, or only reopen beads closed as `done`. The second covers the case where you cancel a bead between an agent's death and the healer restarting it.
- **Someone else closed the bead:** warning only, or ask for confirmation. This was 2 of the 8 real cases.
- **Note prefix:** keep `LAUNCH REOPEN:` or pick other wording.

The report is registered as artifact `explicit:7a75985e51ef445d82e31318` with label `research:202610/closed_bead_launch_reopen_with_audit__cld.md`. The final declaration was accepted, and the research repo will be committed when this turn ends.
