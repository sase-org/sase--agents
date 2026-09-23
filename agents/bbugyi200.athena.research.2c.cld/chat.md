# Chat History - ace-run (research.2c.cld)

- **TIMESTAMP:** 2026-09-23 13:34:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2c.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260923_131242.md`

## Prompt

%id(cld, clan=research.2c)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.2c.mus`, `research.2c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I keep hearing about this Hermes agent
that is apparently a lot like OpenClaw and, maybe, a lot like this project. Can you do
some research with the goal of comparing and contrasting the Hermes project with this
project? End your analysis by giving sase a rating on how well it competes functionally
(don't consider popularity/adoption) with Hermes. 
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

I've opened the Hermes Agent repo locally and am now reading its docs and code, which I'll then compare against sase's.

I'm sending four read-only agents in parallel to go through the Hermes docs and the sase docs. Meanwhile I'll read sase's core docs myself.

Before writing, I'm spot-checking the claims that matter most for the rating against the sources.

I have enough evidence. I'm checking two last facts (Hermes's headless one-shot mode, and a few sase remote/sudo details), then writing the report.

Writing the report now.

The report is written and the weighted total checks out (510.5 / 100 = 5.1). Next I'm registering the report as an artifact.

Registration worked. Last step is the SASE final declaration.

I wrote the report and registered it as an artifact. The host will commit it to the research repo.

**Report:** `sase/repos/research/202609/sase_vs_hermes_agent_functional_comparison__cld.md`
**Artifact:** label `research:202609/sase_vs_hermes_agent_functional_comparison__cld.md`, id `explicit:011559d4daf123e7a6140ad1`

**Key findings**
- **They are different kinds of product.**
  - Hermes (Nous Research, latest release v2026.9.21) is a personal agent that runs its own model loop. It learns on its own (writes its own memory and skills), talks to you on about 28 chat platforms, and has a desktop app, voice, a browser tool and sandboxed execution.
  - sase is a control layer over other companies' coding CLIs (Claude Code, Codex, Grok, etc.): isolated workspaces, epics, commits made by sase rather than the agent, approval gates, and audit trails.
  - So "Hermes is like OpenClaw" is accurate. "Hermes is like sase" is only true for Hermes's Kanban board and its "engineering pipelines" use.
- **Inside that overlap, sase is stronger for supervised coding with many agents.**
  - Hermes's own docs say running external CLIs like Claude Code or Codex as Kanban workers is "not yet a paved path". In Hermes the worker agent runs git and opens PRs itself; nothing like sase's host-side commit step exists.
  - sase's plan → epic → phases → land-agent flow is deeper than Hermes's flat task graph.
- **Hermes is still ahead in a few coding areas:** a built-in review step per task, a gate that checks a PR's required GitHub checks, `/goal` loops that run shell checks before declaring done, undo/rollback of an agent's edits, and real sandboxes.
- **Complementary angle:** Hermes can run headless (`hermes chat -q --oneshot --format stream-json`), so it could be added as an 8th sase provider. That would give sase Hermes's model reach under sase's own controls.

**Rating: 5/10 overall** (weighted total 5.1, where 10 means sase matches or beats Hermes on that dimension).
- About 8.5/10 for supervised software engineering with many agents from different vendors.
- About 1.5/10 as a general personal assistant.

**Caveats**
- I did not run Hermes. Its side comes from its docs and code at the September 23 commit, and some of those docs contradict each other (I list where).
- The weights behind the 5/10 are my judgment calls; the full scorecard is in the report.
- I used the April 2026 sase-vs-Hermes report for context only. Hermes shipped a lot after it (for example goal loops, the desktop app and Bot Mode), so I re-checked everything rather than reusing its conclusions.

Sources:
- [Hermes Agent: Nous Research](https://hermes-agent.nousresearch.com/)
- [OpenClaw vs Hermes Agent: Composio](https://composio.dev/content/openclaw-vs-hermes-agent)
- [Hermes Agent vs OpenClaw: Pickaxe](https://pickaxe.co/post/hermes-agent-vs-openclaw)
- [Hermes Agent vs OpenClaw, May 2026: Lushbinary](https://lushbinary.com/blog/hermes-agent-vs-openclaw-updated-comparison-may-2026/)
- [Hermes Bot Mode: MarkTechPost](https://www.marktechpost.com/2026/08/17/nous-research-hermes-bot-mode/)
- [Hermes Agent updates: Releasebot](https://releasebot.io/updates/nousresearch/hermes-agent)
