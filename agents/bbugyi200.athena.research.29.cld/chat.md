# Chat History - ace-run (research.29.cld)

- **TIMESTAMP:** 2026-09-22 12:52:34 EDT
- **MODEL:** claude/opus
- **AGENT:** research.29.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_122509.md`

## Prompt

%id(cld, clan=research.29)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.29.mus`, `research.29.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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

Reviewing yesterday's research (a consolidated report does exist from Sep 21), next I'll audit agent runs from the last ~2 days myself to verify its claims and look for new failures.

Auditing the run artifacts for Sep 21–22 now; building a per-run classification of how each agent's turn ended.

Writing an audit script over the run artifacts; first checking how monitors map back to the agents that started them.

Dismissed agents lose done.json, so I'm merging in the dismissed-bundle archive to recover outcomes for every run.

Checking whether SASE's per-run workflow log captures Muse's full tool inputs (the artifacts don't).

Now scanning every Muse session this month for that pattern (background-yielded command → model ends turn), to see how often it happens and what happens to the background process.

Clear split emerging. Now checking the Muse "waiting…" endings where the process exited cleanly: was anything actually still running when the model quit?

Now reading the governing decision records so my recommendation fits (or explicitly amends) them.

Now tallying Sep 20–22 outcomes per provider for the report.

Confirming exactly when the teardown watchdog fires and what Muse's stdout stream exposes about pending background work, since the fix hinges on both.

Quantifying the capacity cost of Muse's in-process waits (held runner slot + workspace), since that's the trade-off against a monitor handoff.

Verifying the agy side independently (low volume now, but it's the other harness that kills background work).

agy upgraded to 1.2.8 overnight, and its `run_command` schema example now shows `"Blocking":true,"WaitMsBeforeAsync":0` — worth checking, since the earlier research concluded agy exposed no blocking option.

The host already sees this: SASE's own `tool_calls.jsonl` captures Muse's `background_running` state and guidance text from the stdout stream (119 occurrences). Checking whether completions are visible there too, then I'll write the report.

Verifying two headline numbers before writing up.

Verifying the skill source paths I'll cite, then writing the report.

Report written. Registering it as a durable artifact snapshot.

Registration succeeded (`file:explicit:879bf00a26a9ded64d4a7a1a`). Submitting the finalizer declaration before I reply.

Report written and registered; declaration accepted.

**Report:** `research:202609/headless_wait_contract_and_provider_teardown__cld.md` → `file:explicit:879bf00a26a9ded64d4a7a1a`

## What I found

Your hypothesis describes the symptom exactly, but the cause is inverted for the provider producing it today. Since Sep 20 the fleet is Claude + Muse (Grok/Codex haven't run since Sep 19), and every recent case is Muse. **Muse agents are not confused about headless mode** — `muse exec` really does stay alive after the model ends its turn, wakes it when a background command finishes, and repeats until done. I verified 31 sessions where that worked; one waited 1h30m across three overdue reminders and closed its bead.

What kills them is SASE:

1. **The host reaps a legitimately waiting provider (7 runs in 3 days).** The Sep 20 teardown watchdog (`68d9e0f65`) kills the provider 120 s after a declaration is accepted, checking only liveness. Meanwhile `/sase_final` *instructs* agents to declare before an "I will wait" response. The agent obeys both, gets killed, its `just check` dies with it — and the run is reported **SUCCESS** ("The completed reply is unaffected"; it wasn't). Two were killed mid-work in a woken turn. Your own hand-close notes are the receipt: *"The agent completed its work but didn't close the bead because it didn't finish verification"* (×5), plus `sase-142.5.2`, `sase-142.5.3`, `sase-14t.3` still stranded `in_progress`.
2. **A Muse delivery race (4 runs).** When the result lands mid-turn, Muse logs `deferred_token_held`, drains it into the current turn, the model misses it and says "still running" — then Muse exits because nothing is pending. Detectable with certainty: a clean `muse exec` exit plus a wait-claim always means stranded.
3. Small stuff: agy's structural detector is still allowlisted to 1.0.10 while 1.2.8 is installed (`sase-15o`, still ready); monitor handoffs are down to 21 in three days. Claude: **zero** native background uses in 217 runs.

**Root cause:** SASE has no model of per-provider wait semantics. It asserts one universal rule — `decisions:single-turn-agents` claims native background primitives "silently no-op here" — encodes it in prompts *and* host mechanisms, and that premise is false for one of its two active providers.

**Recommendation:** make the wait contract explicit per provider and derive both guidance and host policy from it. P0 today: make the watchdog background-aware (the signal is already on the stdout stream SASE parses), stop telling agents to declare before waiting (enforce it in `sase final submit`), and turn a stranded wait into a continuation instead of a declaration-only recovery turn. P2: a provider-neutral rule that "reply claims a wait + bead open + no mechanical handoff" is `incomplete`, not `completed`. More "you are headless" prompt text would have prevented none of these — every agent that died was following instructions.

I also list where I contradict yesterday's consolidated report (notably its "no Muse cases since Sep 15", and agy's supposed lack of a `Blocking` option). I did not file beads — three researchers filing the same ones would duplicate; the report lists four proposed follow-ups for the lead.
