# Chat History - ace-run (research.4u.cld)

- **TIMESTAMP:** 2026-11-15 17:04:20 EST
- **MODEL:** claude/opus
- **AGENT:** research.4u.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261115_164459.md`

## Prompt

%id(cld, clan=research.4u)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4u.cdx`, `research.4u.grk`, `research.4u.mus`, `research.4u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It doesn't seem like agent hijacks are working correctly. See the
~/tmp/screenshots/20261115_164112.png screenshot, which was taken on the apollo machine,
for context. Agent hijacks should work on as many types of sase turns (in as many
states) as possible. I would like to fix this issue and make agent hijacks much more
resiliant / dependable in general.

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

Investigating the hijack eligibility code path now — the screenshot shows the toast "Selected agent is not eligible for hijacking" on a session row whose live turn is a monitor (`--mon-3 ▶`).

Still digging: I'm tracing how a session row's selected agent object gets built, and checking live state for `tailnet-t.10` on this host.

Loading the live agent rows with the installed sase interpreter to see what fields the session row carries.

I'll evaluate the backend (Rust) eligibility read-only for live agents — resolving the target and checking eligibility, without stopping anything.

No hijack record has ever been created on apollo (`~/.sase/agent_hijacks/` holds only a lock file). Checking the proc history for refused hijack attempts.

Reading the original Agent Hijack plan's scope and non-goals before writing the report.

Nearly done investigating; confirming the kill modal's "Hijack instead" option uses the same broken predicate, then writing the report.

Checking whether the missing provider/effort facts actually degrade recovery's Continue path.

Writing the report now.

Report written. Registering it as a durable artifact.

Hijack doesn't work on any agent right now, not just the one in your screenshot. I found five separate defects on the same path, and any one of them is enough to block every hijack. No hijack has ever succeeded on apollo: `~/.sase/agent_hijacks/` has no records, and the only hijack entry in the TUI toast log is the refusal from your screenshot.

**What went wrong, in the order a `,k` press hits it** (the first two were checked against live agents with read-only probes):
1. **The TUI rejects every real agent.** The eligibility check requires the row type `AgentType.RUNNING` (`_hijack_action.py:23`). Every prompt launch is wrapped as an anonymous `tmp_*` workflow, so real rows load as `WORKFLOW`. 0 of the 7 running agents passed. The same check also hides the `,k` hint and the kill dialog's "h Hijack instead" option.
2. **The backend also refuses everything.** The runner stamps `runner_capabilities: ["hijack"]` into `agent_meta.json`, but a later rebuild of that file keeps only an allow-list of keys (`run_agent_directive_metadata_preserved.py:31`), and the stamp isn't on it. Every agent, including ones started minutes before, is refused as "launched before hijack support". `launch_scratch_key` already had this same bug and was patched with a re-stamp.
3. **The session row points at the wrong turn.** On `tailnet-t.10` it represents `tailnet-t.10--plan` (already done, with a dead pid), not the live turn. `sase agent hijack <session>` can resolve to a monitor and treat it as an ordinary agent turn.
4. **Recovery would fail even after a successful stop.** The hijack code reads `agent_llm_provider` and `agent_effort`, but runners write `llm_provider` and `reasoning_effort`. The saved model becomes a bare `gpt-6-luna`, which the Rust check rejects, so **Continue** and **Escalate** would fail.
5. **The refusal reason is hidden.** The toast is generic, and the TUI never asks the Rust eligibility function; it applies its own narrower rules.

On top of that, your screenshot caught `tailnet-t.10` mid-handoff: turn `--5` was still committing its work and monitor `--mon-3` was running. Hijack refuses both of those states by design. The tests missed all of this because each one hand-builds the exact input that is broken in production.

**Critique and changes to your requirements** (all flagged in the report):
- **Fix the basic path before adding turn types.** The hijack code is about 11k lines and has never completed one real hijack, so adding monitors and gates now would mostly add untested code. First goal: `,k` on an ordinary running agent works and Continue succeeds, guarded by a test that runs a real agent launch.
- **Hijack the agent, not a row.** The backend should work out which turn is live at the moment it acts. In your case the live turn changed three times in about four minutes.
- **Replace "as many states as possible" with "every state has a defined outcome".** Each state is either hijacked now, hijacked at the next safe point, redirected (for example a queued agent to `,x` kill & edit), or refused with a specific reason. Some steps shouldn't be cut off halfway, like a commit or push in progress.
- **Deferred:** gate turns, home mode, and hijacking remote agents directly instead of copying the command.

**Recommended solution:**
1. **Make the current design work.** Fix the five defects above, show the real refusal reason, add `sase agent hijack --explain`, and add the real-launch test. This is about one medium phase.
2. **Add a pending hijack.** If the live turn can't be stopped safely, record the hijack and apply it at the next handoff. Every handoff I traced (monitor start and completion, gate and turn follow-ups, successor delivery) moves the workspace claim under the existing claim lock. Storing the pending hijack on the claim would make it apply exactly once, with no new lock.
3. **Monitor hijack.** Stop the command, don't launch the `--next` follow-up, keep the workspace, and let you continue with instructions. Today, stopping a monitor leaves the session stuck. This phase covers your screenshot case directly.

The report also has a table of every turn type and state, the options I rejected, and the probe scripts I used.

**Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202611/agent_hijack_reliability__cld.md`

It's registered as artifact `file:explicit:92bf8904fc0771a933b6290d` with label `research:202611/agent_hijack_reliability__cld.md`. The commit to the research repo is declared and the host makes it after this turn ends.
