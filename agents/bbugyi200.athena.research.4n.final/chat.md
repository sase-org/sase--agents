# Chat History - ace-run (research.4n.final)

- **TIMESTAMP:** 2026-10-16 11:57:33 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4n.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_110522.md`

## Prompt

%clan(research.4n, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
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
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.4n.final %m:@xlarge
%wait:research.4n.cdx %wait:research.4n.cld %wait:research.4n.grk %wait:research.4n.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.4n.cdx`, `research.4n.cld`, `research.4n.grk`, `research.4n.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.4n.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4n.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

Research repo is open and all four reports are present. Now I'll read each one through `sase artifact read`.

Checked the core claim code and the finalizer policy. Now I'm checking the phase-worker prompt and how the finalizer closes beads.

Confirmed that phase and task workers close their own bead mid-turn, before the host commits their work. Now I'll check cld's evidence against the real bead histories.

The original runs' artifacts appear to have been garbage-collected. I'll try the agents sidecar's session pages to learn why they failed.

The original sase-17x.13.1 run committed to master two minutes after it closed its bead, so that work had landed. Checking the other self-closed cases the same way.

sase-xe.6 is the exception: its bead closed but nothing landed until the next morning, so that close really was premature. Now checking cld's three "closed while queued" cases.

Nearly done verifying. One last check: where could the runner tell the relaunched agent its bead is already closed?

Verification is done. Now I'll move the four reports into the new `closed_bead_agent_relaunch/` folder, then write the final report.

Files moved. Before writing, one detail to check: what status `sase bead open` leaves the bead in, since the relaunched agent's escape hatch depends on it.

`sase bead open` leaves the bead `open`, not `in_progress`. A reopened bead therefore only finalizes cleanly if the agent closes it itself with `sase bead close`. Now writing the consolidated report.

Report written. Before registering it, I'm checking a few claims and paths it cites.

The cited paths and the validation rule check out. Registering the consolidated report.

Layout is complete and the main workspace is clean. Submitting the final declaration.

My recommendation is to allow `%id(..., bead=<closed>)` launches, but leave the bead closed rather than reopening it. The launch attaches to the closed bead, and the host writes a timestamped `CLOSED-BEAD LAUNCH:` note on it as the audit trail. The consolidated report is written and registered as `research:202610/closed_bead_agent_relaunch/closed_bead_agent_relaunch__final.md` (`file:explicit:9c0aa03f9427d0a0a9ce1bd8`). The research repo commit has been declared and will land once this turn ends.

**What I checked myself.** The four researchers split 2–2, so I re-checked the 11 real failures cld found, using bead histories and landing commits on master:
- **The closes were usually correct.** In 5 of the 6 relaunches I could check, the original run's work had landed on master about 2 minutes after the agent closed its bead (or needed no code at all). Reopening would have marked finished work `in_progress`. Only sase-xe.6 was a premature close.
- **cld misread who closed the beads.** Before 2026-09-25, a close event recorded the bead's creator as the actor. The "closed by the land agent" cases were really the agents closing their own beads.
- **cld cited a precedent that doesn't hold.** It said `EpicWorkPreclaimed` already reopens at launch. It actually rejects closed beads (`claims.rs:352`).
- **gem's `%wait` argument doesn't hold.** Dependent agents were already released by the original close, and reopening doesn't make them wait again.

**Changes to your requirements:**
1. **Leave the bead closed.** "Fine" means the launch proceeds with status, resolution, assignee and parent beads untouched. Reopening stays a deliberate `sase bead open`.
2. **Narrower scope.** Only allow it when the bead was already closed when the launch was submitted. 3 of the 11 real failures were beads closed while the launch sat queued: a phase you had just superseded, one another agent finished, and one you closed by hand. Those launches should still be refused, with a clearer error. The two "keep closed" reports missed this.
3. **Write the note in sase-core.** It goes in the existing launch-claim mutation, authored by the launching agent, one note per launch. This uses the existing note event, so there's no wire-format change.
4. **Tell the agent.** Prepend a short notice that its bead is already closed, since every prompt today promises an `in_progress` bead.
5. **Left out of v1:** a feature flag, a confirmation dialog, a `reopen=true` keyword, and any new reopen cause.

**Recommended solution:** Add an optional launch-submission time to `run_claim_launch` in sase-core. If the bead was closed before submission, attach and write the note in the same commit. If it closed after submission, refuse with a `closed_while_queued` error. Wire it through the runner's single claim point so `,x`, `sase agent restart`, retries and typed `%id` all behave the same. Record the outcome in `agent_meta` and add the agent notice. Roll it out as a small two-phase epic: sase-core first, then sase.

**Separate follow-up:** most of these relaunches exist because the phase and task prompts tell agents to run `sase bead close` before the host commits their work. Any later failure then leaves a closed bead, and sometimes the work never landed (sase-xe.6). Closing through the finalizer after the commit would fix that, and is worth its own task. The existing bead sase-1jf covers one common way these original runs fail.

Three choices are left to you in the report: whether auto-restarts may attach to canceled or superseded beads, whether a launch whose bead closed while queued should count as a failure or a neutral stand-down, and the note's wording.

The four reports now sit next to the final one in `202610/closed_bead_agent_relaunch/`, renamed `closed_bead_agent_relaunch__<suffix>.md`.
