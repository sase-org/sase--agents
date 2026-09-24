# Chat History - ace-run (research.2f.cld)

- **TIMESTAMP:** 2026-09-24 09:12:23 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2f.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_085243.md`

## Prompt

%id(cld, clan=research.2f)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.2f.mus`, `research.2f.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been renaming a lot of sase concepts
to use terms that are more standard across the AI / tech industry lately. For example, I
renamed "axe" to "scheduler", "lumberjacks" to "routines", "chops" to "jobs", "ace" to
"tui", and am now in the process of (see the sase-17m epic bead and the `0qi` sase agent
for context) renaming "agent families" to "agent sessions" and "sase shells" to "sase
turns".

Can you do some research with the goal of critiquing these renames and searching for any
other concepts that you think should be renamed? Make sure that you have strong
justification if you recommend a new rename. End your analysis with a brief critique of
the renames that have already been implemented or will be implemented soon and a list of
new recommended renames that you think I should perform (if any). 
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

I'm gathering context on the rename in progress (agent `0qi` and the sase-17m epic) before surveying SASE's other concept names.

Now reading the full glossary to see how each SASE concept is currently defined.

Reading the prior naming research (the scheduler/TUI naming reports first) through audited artifact reads.

Next I'll survey the CLI surface and code to find the other idiosyncratic names.

Reviewing the current state of the scheduler/routine/job rename in code and config, then I'll check the remaining candidate terms (pipe, mentors, hooks, LLM Calls, memory webs, stitch).

Checking the "LLM Calls" panel, memory-web/strand terms, and the clan/hood/tribe concepts in code next.

Checking the prior xprompt-naming research and the clan/hood/tribe usage before drafting.

Verifying industry precedents (Codex/OpenAI/Claude/LangGraph terminology) with a few web searches.

Confirmed the key external definitions. Now checking leftover `ace`/`axe` surfaces and the turn-related CLI options before writing.

I have enough evidence; one last scope check on the `pipe` surface, then I'll write the report.

Writing the report now.

Report written. Registering it as a durable artifact.

Registration succeeded. Submitting the final declaration.

I wrote the report and registered it as a durable artifact (`explicit:db74b53210da26c7af67c458`, label `research:202609/sase_concept_renames_critique__cld.md`). Its commit to the research repo has been declared and accepted.

**Report:** `sase/repos/research/202609/sase_concept_renames_critique__cld.md`

## Critique of the six renames

None of them should be reverted.

- **sase shell → sase turn: the best of the six.** "Shell" collides with the Unix shell all over a CLI tool. "Turn" is already the word your decision records use ("a SASE agent run is exactly one provider turn"), and Codex defines a turn the same way. Gate and monitor turns fit if you think of chat roles: an agent turn is the assistant, a monitor turn is a tool result, a gate turn is the human.
- **chop → job: excellent.** It's the standard term; call one execution a "job run".
- **ACE → TUI: good.** Leftovers: the config root is still `ace:`, and docs say "sase's TUI" 836 times.
- **AXE → scheduler: good but unfinished.** `routine`, `job` and `maintenance` still only exist under `sase axe`. The `axe:` config root and 158 "AXE" mentions in docs remain.
- **lumberjack → routine: defensible, the weakest.** It collides with Claude Code routines, which correspond to a SASE *job* that launches an agent, not a SASE routine. The shipped config still describes routines as "lanes". I'd keep it and write "scheduler routine" in agent-facing text rather than rename again.
- **agent family → agent session: good, with caveats.** Your code already uses "session" for live TUI instances, which is a user-visible clash. The glossary needs to say an agent session can span several provider sessions. The family/clan/tribe ladder is now broken; I found nothing better for clan or tribe, so keep them but stop presenting them as a ladder.

## Three corrections for the sase-17m epic and `0qi`'s plan

1. **Avoid a double migration.** The session epic is already writing new stored keys with "shell" in them (`agent_session_shell`, `_kind`, `_id`, `_state`). sase-17m.8 hasn't landed yet and will bump schemas and the fleet protocol. Put the `turn` spellings into sase-17m.8 so there is one bump instead of two.
2. **Split the two meanings of "shell".** The proc store's `shell_name`/`shell_kind` fields (including `shell_kind="service"` on service daemons) and `sase proc list --shell` belong to named procs. They should get proc names, not become "turns".
3. **Pick one name for the command member.** Use "monitor turn" and retire "proc shell". Separately, Claude's `num_turns` counts tool-use round trips, so never show it as "turns" in SASE.

## Recommended new renames

1. **`sase pipe` → `sase handoff`.** A Unix pipe is concurrent streaming; this command is a serial handoff. "Handoff" is the OpenAI Agents SDK term and already appears about 628 times in your code, docs and tests. The change is cheap (about 12 files and one config key).
2. **"LLM Calls" → "Tool Calls".** The panel lists tool calls, not model calls: its data file is `tool_calls.jsonl` and its empty state says "No tool calls recorded". The name is only six days old.
3. **"TUI session" → "TUI instance".** This covers `sase proc list --session` and the session chip. Without it, "session" has two user-visible meanings once agent sessions ship.

Optional, only if you're already editing those areas: hood → namespace, mentor → review agent.

Sources:
- [Codex App Server](https://developers.openai.com/codex/app-server) · [app-server README](https://github.com/openai/codex/blob/main/codex-rs/app-server/README.md)
- [OpenAI Agents SDK – Running agents](https://openai.github.io/openai-agents-python/running_agents/) · [Handoffs](https://openai.github.io/openai-agents-python/handoffs/) · [Human-in-the-loop](https://openai.github.io/openai-agents-js/guides/human-in-the-loop/)
- [Claude Agent SDK – Sessions](https://code.claude.com/docs/en/agent-sdk/sessions) · [Agent loop](https://code.claude.com/docs/en/agent-sdk/agent-loop) · [Claude Code routines](https://code.claude.com/docs/en/routines) · [Agent teams](https://code.claude.com/docs/en/agent-teams)
- [LangGraph interrupts](https://docs.langchain.com/oss/python/langgraph/interrupts) · [OpenTelemetry GenAI observability](https://opentelemetry.io/blog/2026/genai-observability/)
