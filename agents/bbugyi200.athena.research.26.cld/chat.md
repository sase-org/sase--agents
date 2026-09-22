# Chat History - ace-run (research.26.cld)

- **TIMESTAMP:** 2026-09-21 19:23:35 EDT
- **MODEL:** claude/opus
- **AGENT:** research.26.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_185249.md`

## Prompt

%id(cld, clan=research.26)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.26.mus`, `research.26.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure what the
best solution for multi-agent collaboration is when it comes to sase agents. Can you do
some research with the goal of helping me decide the best way to implement this? End
your analysis with a recommended solution. Review the multi_cli_orchestration_vs_sase.md
and family_channel_delivery.md files in the research sidecar repo for context and
inspiration before peforming your own research. 
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

I'm reading the two context reports from the research sidecar before starting my own investigation.

Skimming the prior collaboration-architecture report now, then I'll start the code and web research in parallel.

Both sweeps are back. I'll now spot-check the load-bearing claims myself: SASE's wait/fork/mentor code paths, how SASE invokes the Claude CLI, and Claude Code's cross-session messaging docs.

I'm verifying a notable finding: SASE's headless Claude agents already expose Claude Code's cross-session messaging tools, which is an unmanaged side channel. Checking with a read-only listing.

Writing is next; first a quick check of two SASE facts I'll cite (the monitor-based agent wait pattern and mentor config).

Research is complete; writing the report now.

Now registering the report as a durable artifact.

Registration succeeded. Now the final declaration.

I've written the report and registered it as an artifact (`file:explicit:d966eccbf716422a9a0729ec`, label `research:202609/multi_agent_collaboration_design__cld.md`). The host will commit it to the research repo.

**Report:** `sase/repos/research/202609/multi_agent_collaboration_design__cld.md`

**Main findings:**
- **"Multi-agent collaboration" is really six problems.**
  - SASE already handles two of them well: independent fan-out followed by synthesis (like this swarm), and parallel work ordered by dependencies (epics).
  - SASE's weak spot is three loops where no answer comes back:
    - A child launched with `/sase_run` doesn't send its answer to the agent that asked for it. Getting it today takes three turns plus a monitor shell.
    - Mentor reviews never reach the agent that wrote the code, and you can't choose the model, so "Codex reviews Claude's work" can't be set up.
    - A human can't send a correction to a running sequence of agents.
- **Outside research points the same way.** Cognition, Anthropic, Cursor and Google all found the same rule: keep code changes to one agent at a time, and let extra agents add judgment (review, synthesis) rather than more edits. Messages should go through a durable mailbox that the host delivers, and agents should never poll. Live group chat among agents did badly: they agree too early, flood the system by polling, collude, and burn a lot of tokens.
- **New since the family-channel report:** Claude Code (through hooks and cross-session messaging) and Codex (through the app-server's `turn/steer`) can now deliver a message to an agent between its tool calls. That makes mid-turn delivery something SASE can offer as an optional per-provider feature, though it still shouldn't be promised.
- **There is an unrecorded side channel today.** Every SASE Claude agent runs with permissions bypassed and can use Claude's `ListAgents`/`SendMessage` tools. From this session, `ListAgents` showed three other live SASE Claude sessions. By default, these bypass-mode sessions accept each other's messages mid-turn, and nothing is recorded in SASE. Only one such call appears in about 4.8k runs since 2026-08-15. Closing it takes one settings flag plus a tool deny.

**Recommended solution:** SASE should carry information between single-turn agents itself, rather than let agents talk to each other directly. Build it in three tiers, each only when there's evidence it's needed:
1. **Now, with no new infrastructure:**
   - Let a requester resume when its delegated child *finishes*, with the child's result attached.
   - Give mentors a model field and a "reviewer uses a different provider than the author" policy, and send accepted findings back to the author's family.
   - Include reply bodies and every clan member in what `%wait` hands over.
   - Turn off Claude's cross-session inbox for SASE agents.
   - Optionally, warn at plan time when two epic phases that run at the same time will touch the same files.
2. **Next:** the narrow durable family inbox from `family_channel_delivery`, with two changes. The host can post replies and reviews into it, and an unanswered request or correction can make the host launch one successor when the turn ends.
3. **Only if metrics show the need:** mid-turn delivery through provider hooks, wakeups when a channel gets a new post, and warnings between epic phases routed to the land agent.

Don't build group chat, agent polling, A2A, LLM supervisors, file locks, or a message bead type.

**Caveats:**
- I didn't file a task bead for the side channel, so the three researchers don't file duplicates; the lead should file it with `/sase_new_task`.
- A few external claims are from secondary sources or unverified (the Codex subagent tool names, and whether Claude Code's background-tasks switch also covers workflows); the report marks them.
- I didn't read the other researchers' reports.
