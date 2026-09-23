# Chat History - ace-run (research.29.final)

- **TIMESTAMP:** 2026-09-22 13:22:11 EDT
- **MODEL:** claude/opus
- **AGENT:** research.29.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_122509.md`

## Prompt

%clan(research.29, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? Note that I had some agents do some research on this issue yesterday but I
don't think the research swarm finished (feel free to review those research files for
inspiration, but make sure to verify any claims you intend to use in your own research).
End your analysis with a recommended solution.]]) %id:research.29.final %m:@xlarge
%wait:research.29.cld %wait:research.29.mus %wait:research.29.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? Note that I had some agents do some research on this issue yesterday but I
don't think the research swarm finished (feel free to review those research files for
inspiration, but make sure to verify any claims you intend to use in your own research).
End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.29.cld`, `research.29.mus`, `research.29.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Reading the three researcher reports now, then I'll verify their claims against run logs and code.

Confirmed the watchdog and all 8 stall artifacts (all Muse). Now checking what those agents said when killed and whether Muse really wakes models post-turn.

Verifying the disputed claim that Muse wakes the model after a turn ends, using its session logs.

Still tracing the Muse session log: checking its turn starts, ends, and inbox wakes on a timeline.

Writing a scan script across all Sep 15–22 runs to check the findings for every provider at once.

Found a 9th watchdog kill (`sase-16e.5`, ~12:14 today) that happened after the cld researcher wrote. Checking it and the two other Muse wait-endings that had no declaration.

Monitor handoffs are now rare (23 in 3 days), but several failed in 0 seconds. Checking why.

Confirmed that a declaration is only required when the tree is dirty. Now reading the declaration-recovery prompt.

Confirmed that `lint_and_test` tells agents to switch to a monitor partway through a run. Now counting Muse cancel-and-restart handoffs across the three days.

`sase-163` already covers Claude's leftover async tools. Its critique note says `claude -p` stays alive for background subagents and workflows for up to 10 minutes. Checking that in the local binary.

I've verified enough to consolidate. Moving the three reports into a new directory, then writing the consolidated report.

Reports moved. One quick check before writing: whether `muse exec` can take an appended system prompt, which decides how a Muse-specific directive would be delivered.

Writing the consolidated report now.

Report written. Checking a few cited line numbers and tightening two statements.

Report is final. The watchdog bug is actively losing work (9 firings in 3 days), so I'm filing it as a task bead per project norms.

No in-progress epic caused the watchdog (it landed as a standalone fix, `68d9e0f65`), and no existing task duplicates it. `sase-12s` is related but not a duplicate. Creating the bug bead.

Filed `sase-16i` (ready). Updating the report to reference it and the existing related bead `sase-12s`.

Layout is final. Submitting the SASE final declaration.

The agents dying now are not confused about headless mode. They are Muse agents doing what their harness tells them: end the turn and wait. SASE itself is what misreads that, and kills or restarts them.

Since Sep 20 the fleet has been almost entirely Claude and Muse (agy 8 runs, Codex 1, Grok 0). Muse 1.3.0, installed Sep 17, keeps its process alive after the model stops talking, wakes the model when a background command finishes, and reminds it every 30 minutes while the command runs. I replayed a session where an agent waited 1h30m this way and then closed its bead. But SASE's rules assume no agent can ever wait, and three of them break Muse waits:

| Failure (Sep 20–22) | What happens | Count |
| --- | --- | --- |
| **A. Watchdog kill** | `/sase_final` tells agents to declare before an "I will wait" reply. The Sep 20 watchdog (`68d9e0f65`) kills the provider 120 s after any declaration, without checking for pending work. The check dies, the bead stays open, and the run shows SUCCESS. | 8 of 9 firings, all Muse. The latest was `sase-16e.5` today. |
| **B. "Long command, some monitor, then dead"** | Muse's 30-minute reminder wakes the model. It reads `/sase_monitor` ("hand off whenever it is taking a long time"), cancels the running check, and calls `sase monitor start`, which kills the agent. The next agent re-runs the check from zero. | 26 cancellations in 21 runs; 15 of those runs read `/sase_monitor` first |
| **C. Muse delivery race** | The command finishes mid-turn and the result is delivered into that same turn. The model ignores it (one case had `exit_code: 0`) and says it is waiting. Muse exits cleanly and no wake ever comes. | 4 |
| **D. agy** | agy backgrounds anything over 10 s and kills those tasks when it exits. SASE's agy guard is effectively off (`sase-15o`). | 2 |
| **E. Claude** | Clean since the Sep 15 fix: no background-tool use from Sep 15 to 22. | 0 |

**Root cause.** SASE treats "the model stopped talking" as "the provider is done". Nothing mechanical records "this run still has work in flight", so each layer guesses:
- the skills tell agents to declare before waiting and to switch to a monitor partway through a run;
- the watchdog treats a declaration as the end of the turn;
- the success check treats "the process exited" as "the task is done".

The watchdog's own motivating incident was also a Muse run. It looks like the same wait, misread as a leaked pipe, though I couldn't find that session's log to confirm.

## Where the reports disagreed
- **cld's central claim holds up.** I confirmed it and found a 9th watchdog firing that happened after cld wrote.
- **mus and gem described Muse as polling with no guard.** That was true before 1.3.0 and is out of date now.
- **gem said `sase-165.6.f0--code` looked hung.** It was actually waiting for a wake, and it finished: it produced the current HEAD commit `d3002aba1`.
- **Yesterday's report did finish.** Its findings are right for Sep 14–19, before the fleet changed.

## Recommended solution
The host, not the model, should track whether a run still has work in flight, and every policy should read that one fact.

1. **Today:** fix the conflicting instructions (these are memory/skill edits, so they go through `/sase_memory_write`).
   - `/sase_final` and core memory should say a declaration means "my work is done", not "my turn is ending".
   - `lint_and_test` and `/sase_monitor` should say to choose inline or monitor up front, and never cancel a running check to restart it under a monitor.
   - Optionally, set `SASE_PROVIDER_TEARDOWN_GRACE_SECONDS` to 2–3 h as a bridge until the watchdog fix lands.
2. **This week:**
   - Make the watchdog skip providers that still have background work pending.
   - Add a Muse guard for the delivery race: a clean exit plus "I'm waiting" means the wait is stranded, so nudge the agent with the result.
   - Let the recovery turn finish the task instead of only collecting a declaration.
   - Give Muse a short prompt prefix that matches its harness.
   - Land `sase-163` (it removes Claude's leftover background tools).
3. **Next:**
   - Declare a wait contract per provider and generate the guidance from it.
   - Classify "bead still open, reply says waiting, no handoff" as incomplete for every provider (widen the existing `sase-12s`).
   - Write a new decision record to replace `decisions:single-turn-agents`. The rule to keep is one run = one provider process; how many model turns happen inside it varies by provider.
4. **Then:** make handoff lossless through the `sase tool` roadmap's E2 work. The roadmap deferred joining an already-running check for lack of evidence; the 26 cancellations above are that evidence.

More "you are headless" prompt text would not have prevented A or B: those agents were following explicit instructions.

I filed the watchdog bug as `sase-16i` (medium, marked ready). The Muse delivery-race guard and the skill/memory changes are proposed in the report but not filed.

Files are in `sase/repos/research/202609/provider_wait_contract_early_exits/` (the host commits them from the final declaration):
- provider_wait_contract_early_exits.md — the consolidated report
- provider_wait_contract_early_exits__cld.md
- provider_wait_contract_early_exits__mus.md
- provider_wait_contract_early_exits__gem.md
