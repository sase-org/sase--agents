# Chat History - ace-run (research.22.cld)

- **TIMESTAMP:** 2026-09-21 13:58:46 EDT
- **MODEL:** claude/opus
- **AGENT:** research.22.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_132041.md`

## Prompt

%id(cld, clan=research.22)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 2-researcher swarm.
The other researcher, `research.22.mus`, is independently investigating the same request and will write its own self-named report ending in `__mus.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The multi_cli_orchestration_vs_sase.md file in the
research sidecar repo recommended that sase "Add a generic ACP provider plugin.". Can
you do some research with the goal of helping me decide the best way to implement this?
Also, critique this plan in general. Is this a good idea? Would you take a different
approach? Make any adjustments to the requirements that you think are justified but
clearly call these out. End your analysis with a recommended solution. 
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

Reading the source report is done. Next I'm mapping SASE's provider plugin architecture and researching the current ACP spec and its adapters.

Both web research passes are back. Now reading SASE's provider plugin contract first-hand.

I'm still reading the provider internals: interrupts, the completion watchdog, and tool-call normalisation.

Key finding so far: providers are one entry point mapped to one class with no constructor arguments. Now checking how provider identity flows through routing and model strings.

Next I'm checking whether any provider stream normalisation already lives in the Rust core. That tells me which side of the core boundary an ACP client belongs on.

Checking how many places outside the provider module hard-code provider names. That sets the real cost of adding N ACP-backed providers.

No existing ACP bead. Next I'm checking the ACP schema checkout directly to confirm the usage semantics, which are central to the critique.

acpx looks like a strong candidate for the transport layer. Checking SASE's dependencies and Python SDK fit next.

I have enough on SASE's internals. Now I'm spot-checking the peer-orchestrator evidence (Vibe Kanban, Multica, Goose) that the recommendation leans on.

Evidence gathering is done. I'm collecting exact line references, then writing the report.

Report written. Registering it as an artifact now.

Registration worked. Now the final declaration.

I wrote the report and registered it as an artifact (`file:explicit:dc72f830564ef5b0aa04a0a9`); the commit of it to the research repo has been declared.

**Report:** `sase/repos/research/202609/acp_provider_plugin_design__cld.md`
**Label:** `research:202609/acp_provider_plugin_design__cld.md`

## Verdict
Yes, build it, but in a different shape and with a narrower claim than the source report makes. Build a small ACP transport, then describe each agent with a short config profile. Each profile should become its own SASE provider named after the agent (`copilot`, `cursor`, …), not one `acp` provider that hides agents inside model strings. SASE keys pools, disables, usage limits and agent history by provider name, so that separation matters.

## Where the original recommendation is wrong or overstated
- **Usage:** the stable `usage_update` only reports how full the context window is, plus cumulative cost. It does not report input or output tokens; per-turn token counts are still marked unstable in the ACP schema. Multica, the most mature ACP client I found, reads Kimi's on-disk logs to get token usage.
- **Continuity:** `session/resume` works, but only within one agent, and only 11 of the 35 agents the registry tested actually support it. SASE's real continuity problem is moving work *between* providers (pools and drains), which ACP does not address.
- **agy:** it can't be replaced. The `agy` CLI has no ACP mode. Google's separate ACP server needs its own login, reports no usage, and Google's terms threaten suspension for third-party access.
- **Coverage:** only Qwen, OpenCode and Grok have first-party ACP. The report's "six of seven" count includes third-party adapters for Claude and Codex.
- **Missing from the recommendation:**
  - which provider name each ACP agent gets;
  - agents' skill loading, which `/sase_final` depends on (Cline doesn't load skills at all in ACP mode);
  - the permission hook;
  - pinned installs instead of fetching the latest package on every run;
  - model-name collisions (implicit model lookup is last-writer-wins, so a Cursor profile listing Claude models could take over `%model:opus`);
  - how fast the spec is changing.

## Requirement changes (listed as R1–R9 in the report)
- Transport plus profiles, with one provider per agent.
- Usage recorded as reported, partial or unknown, and never faked as zero.
- A conformance check that every profile must pass, including proving `/sase_final` is discoverable.
- A permission responder that approves by default but denies `git commit` or `git push` when it can see the command, which enforces host-owned completion for free.
- Interrupts done by cancelling and re-prompting inside the same session.
- Pinned installs through `sase agent-cli`.
- Version 1 covers the OpenCode and Grok pilots plus one new agent you actually have an account for.
- The transport lives in core SASE rather than an external plugin, because the built-in OpenCode and Grok providers would use it.

## Recommended solution
1. **Transport:** a hand-rolled, synchronous Python client of about 500 lines, extending the transport SASE already uses for its Grok billing probe. I'd skip the official Python SDK (it brings asyncio and pydantic), `acpx` as a subprocess (an extra Node layer with its own defaults), and a Rust client in `sase-core` (that crate has no async runtime, and provider transport is Python everywhere else).
2. **Pilots:** run OpenCode and Grok over ACP as A/B tests against their native drivers. OpenCode gains tool-call and reasoning capture; both gain interrupts that keep full context.
3. **New agents on demand:** Copilot CLI fits best, if you have a plan. Config-only custom agents come later.
4. **Keep native:** Claude, Codex, Muse and agy stay on their current drivers.

Peers do the same: Vibe Kanban and Multica use native protocols for Claude and Codex and ACP only for agents that ship it natively.

I'd also do the cheap native continuity fixes (Claude `--resume` and Codex `exec resume` on interrupt) first or in parallel. They help the providers you use every day more than this work does.

The report ends with three questions for you, mainly which extra agents you actually hold plans for.
