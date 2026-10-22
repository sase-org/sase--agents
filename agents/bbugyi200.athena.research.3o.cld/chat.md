# Chat History - ace-run (research.3o.cld)

- **TIMESTAMP:** 2026-10-05 13:19:21 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3o.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_122744.md`

## Prompt

%id(cld, clan=research.3o)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3o.cdx`, `research.3o.grk`, `research.3o.mus`, `research.3o.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md
  file in the research sidecar repo for context before performing your own research. I
  agree with all of the recommendations made in that research file I think (see below
  bullets).
- One thing I'm not sure the previous research addresses is how we will ensure that when
  another developer clones the sase repo and runs `claude` (or any other LLM provider
  that we support) that this interactive instance of claude has a reasonably good
  CLAUDE.md (or some equivalent to work with). I was thinking maybe we could instruct
  agents (where though?) to run the appropriate `sase / `uvx run sase` command to
  generate this file if it doesn't exist?
- Also, it is not clear to me how a specific provider's subagents are given agent
  instructions that are equivalent to (or better/fixed) what they get today with our
  current agent instruction files.

Can you do some research with the goal of helping me decide the best way to address each
of these issues? End your analysis with a recommended solution. 
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

Read the prior consolidated report. Next I'm checking the current repo state, how each provider's CLI starts up and spawns subagents, and real subagent transcripts.

Still gathering evidence: checking provider CLI flags for hooks and subagent instruction channels.

Collected provider facts from three helper agents. Now testing empirically what Claude subagents in this session actually receive.

Found that some Claude subagents submitted the parent's final declaration. Checking whether their parents told them to.

Grok's root agent saw the `--rules` marker and its subagent did not. Now confirming that from Grok's own session files.

Tests are done. Removing the throwaway test directories and sessions I created, then writing the report.

Before writing, measuring which memory edits caused the 112 AGENTS.md commits in the last 60 days. That tells me how much churn a small committed stub would keep.

Data collection is done. Grabbing a few exact line references, then writing the report.

Report written and registered; the snapshot matches the final file. Now submitting the final declaration.

I wrote the report and registered it as an artifact (`file:explicit:d20008ae3d1ff1cfe772ea6a`, label `research:202610/instruction_bootstrap_and_subagent_delivery__cld.md`). The host commits the research repo after this turn.

**Report:** `sase/repos/research/202610/instruction_bootstrap_and_subagent_delivery__cld.md`

**Question 1: a developer runs `claude` in a fresh clone.** Your idea works, with changes. The instruction belongs in the committed root `AGENTS.md`, because that is the only file every supported CLI reads in a fresh clone. Claude reaches it through a two-line `CLAUDE.md` that imports it.
- **What to commit:** a small, generated `AGENTS.md` written for people outside SASE, which CI checks. Its first section is the bootstrap step: "full instructions are in `.sase/instructions/…`; if missing or stale, run `just agent-instructions` (or, with the user's consent, `uvx sase instructions sync`), then read the file."
- **Changes to your idea:** "missing" should also mean "stale", the agent must read the file after generating it, and it should never install anything silently.
- **Making it automatic:**
  - Claude: the committed `CLAUDE.md` imports the generated file. I tested this: an import of a gitignored file loads, and a missing one is skipped silently.
  - Codex: it reads a gitignored `AGENTS.override.md` in place of `AGENTS.md`.
  - Freshness: `just install` regenerates the files, and an optional Claude startup hook can refresh them.
- **Today's committed `CLAUDE.md` doesn't really serve outside developers.** It tells them to use `/sase_final` and other skills they don't have.

**Question 2: subagents.** The prior plan has a gap here. Instruction files pass down to subagents, but the explicit channels (system-prompt flags, Grok's `--rules`, prompt prefixes) mostly don't. I confirmed that with live Claude and Grok runs. Delivering instructions through flags instead of files would leave subagents with nothing unless each provider also gets a subagent channel. What subagents get today is already causing problems (Claude transcripts, last 30 days):
- **General-purpose subagents receive the full root instructions.** 13 of 200 invoked `/sase_final`, and at least 2 submitted accepted final declarations for their parent's turn. One had been spawned only to "Reply with exactly: ack2". The other had been told explicitly not to commit.
- **Explore subagents receive no project instructions at all.** 11% of them read `sase/memory/*.md` directly, against 1.5% of general-purpose subagents.

**Recommendation:** every provider adapter delivers two separate sets of instructions, one for the root agent and one for subagents.
- **Claude:** `--append-subagent-system-prompt-file` plus `claudeMdExcludes`. I confirmed both reach Explore and general-purpose subagents.
- **Root-only actions are blocked mechanically.** Claude's hook input includes `agent_id` only for subagent tool calls (tested), so a hook can deny `sase final` from subagents.
- **Grok and Muse:** their subagent channels are still open and need small experiments.

**Corrections to the prior report:**
- Codex can suppress the project `AGENTS.md` with `-c project_doc_max_bytes=0`. A helper agent tested this; it is undocumented.
- The planned Phase 0 Grok `--rules` fix restores the root agent only, not its subagents.
- The "Instruction double-load" section of `docs/agent_providers.md` is out of date.

The Claude subagent fix doesn't depend on the larger redesign, so I'd ship it first.

The tests were short `claude -p` and `grok -p` runs, so they cost a few cents of API usage. I deleted their temporary directories and session files afterwards.
