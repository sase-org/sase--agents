# Chat History - ace-run (research.41.cld)

- **TIMESTAMP:** 2026-10-07 15:00:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.41.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_143606.md`

## Prompt

%id(cld, clan=research.41)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.41.cdx`, `research.41.grk`, `research.41.mus`, `research.41.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The `%auto` directive is the main way that we are able to tune permissions (the ones
that are used in practice at least since real sase agents don't have hard permissions
yet) for a sase agent, but this directive is not very configurable or intuitive to use.
I would like to fix this and make this directive much more powerful.

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
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm mapping how `%auto` works today: I've read the macros memory and the related decisions, and next I'll trace the implementation in code.

Next I'm tracing every place `%auto` is consumed: plans, gates, launches, and questions. I'll run a codebase sweep in parallel with reading the docs.

Next I'm reading the design history: the unify-auto commit, adapter-owned resolution, and the TUI toggle change.

I've confirmed the core mechanics. Now I'm checking a few suspected bugs (toggle-off and inheritance) before moving to external prior art.

Codebase mapping is done. I found three inconsistencies worth reporting. Next I'm surveying how other agent CLIs (Claude Code, Codex, Gemini, OpenCode) model permissions.

I have enough prior art. Now I'm checking the `%final` config-instance model, which looks like the closest internal precedent for a policy design.

I'm measuring how often `%auto` and its variants appear in the local prompt history, to ground the critique in real usage.

I've gathered everything I need. Now I'm writing the report: `202610/auto_directive_autonomy_profiles__cld.md`. No file with that name exists yet.

Report written. Next I'll confirm the research repo root and register the artifact.

Registration succeeded. Now I'll submit the SASE final declaration.

I wrote the report and registered it as an artifact. My overall take: making `%auto` more configurable is a good idea, but the power should live in named policies in config, not in a policy language typed into prompts.

**Report:** `sase/repos/research/202610/auto_directive_autonomy_profiles__cld.md`, registered as `research:202610/auto_directive_autonomy_profiles__cld.md` (`file:explicit:2075858ef6fd0a33ec58d050`). The host commits it to the research repo after this turn ends.

**What `%auto` does today:** it is effectively one on/off switch. It auto-resolves three gate kinds: tale plans, epic plans, and questions, where it picks the first option. Every other gate kind refuses it: launch, sudo, custom, HITL and the triage gates. The `tale`/`epic` arguments choose which plan option to take; they don't grant or withhold anything. Every provider CLI runs with its permission-bypass flag, so `%auto` really is the only permission control.

**Your usage since July (local prompt history and gate records):**
- 69.5% of prompts use `%auto`, rising from 61% in July to 80% in September.
- It is almost always bare `%auto`: about 12,100 uses, versus 702 of `%auto:tale` and none of `%auto:epic`.
- Bare `%auto` auto-approved **234 epic plans**, each of which launches a whole set of agents. You can't currently say "approve tales, but stop me for epics."

**Bugs to fix regardless of the redesign:**
1. Turning auto **off** in the TUI doesn't take effect for a running agent launched with bare `%auto`. The runner already set `SASE_AGENT_AUTO_APPROVE=1` and nothing clears it.
2. The docs say `%auto:epic` doesn't auto-answer questions, but the code does.
3. `%auto` carries over after a monitor hands back, but is dropped after a launch, custom or sudo gate hands back. `%auto:tale` is also lost when the coder takes over, while bare `%auto` is kept.
4. Questions are auto-answered with the first option, but nothing tells agents to list their recommended option first.
5. The `%auto` given to epic phase and land agents is hard-coded, and it has been changed in code three times.

**Critique:** the danger is letting prompts grant permissions. Agents write prompts too (launch requests, epic agent prompts, follow-ups). If a prompt could say `launch=allow`, an agent could launch a child with more authority than it has itself. Two other points:
- Auto-approving custom gates defeats their purpose. An agent creates one precisely to get a human decision.
- Agents are never told they're running under `%auto`, so they can't adjust their behaviour.

**Recommendation: "autonomy profiles."** This copies the existing `%final` pattern, where config defines the options and prompt text can only pick among them.
- **Profiles in config.** Each one says, per gate kind, whether to ask a human, deny, or auto-approve in a specific way (for example: approve as a tale, launch at most 2 helpers).
- **Bare `%auto` is unchanged.** It selects a default profile that behaves exactly like today, and `%auto:plan|tale|epic` become built-in profiles so old prompts keep working.
- **Directive forms:**
  - `%auto:<profile>` selects a profile.
  - `%auto(epic=ask)` overrides one gate kind inline.
- **Limits on inline overrides.** A prompt may loosen only plan, epic and question decisions. Anything riskier can be tightened in a prompt but only loosened by a config profile.
- **Children can't exceed their parent.** When a launch is auto-approved, the child's policy is capped at the requester's. A human-approved launch keeps what was requested.
- **One inheritance rule** for every agent that continues the same session.
- **An unattended option** (`on_ask: deny`), so a run never stops to wait for you.
- **Visible and auditable.** The policy is shown to the agent in a short block of its context and recorded on every auto-decision. A new `sase auto explain` command shows what a run is allowed to do.
- **Placement.** Policy logic lives in sase-core.
- **Later layer.** Real tool-level permissions come later and are built from the same profile.

The report lays this out in phases (P0 bug fixes, then profiles with no behaviour change, then deny/launch/unattended support), with the adjusted requirements marked ADDED, CHANGED or DROPPED. It ends with four open questions for you, the most important being whether bare `%auto` should keep auto-launching epics.
