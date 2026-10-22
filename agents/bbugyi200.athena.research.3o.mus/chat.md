# Chat History - ace-run (research.3o.mus)

- **TIMESTAMP:** 2026-10-05 12:39:55 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3o.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_122744.md`

## Prompt

%id(mus, clan=research.3o)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3o.cdx`, `research.3o.cld`, `research.3o.grk`, `research.3o.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete.

Wrote independent report: `202610/dynamic_instructions_bootstrap_and_subagents__mus.md` (257 lines), registered as `research:202610/dynamic_instructions_bootstrap_and_subagents__mus.md` (artifact `file:explicit:9d025792c0cb5a7e21386646`). Final declaration submitted (research repo commit).

Top finding: keep the prior bundle+adapter plan unchanged; add a committed 10–15 line self-bootstrapping stub (`sase instructions sync` / `uvx sase instructions sync`, no `/sase_final`) plus doctor/init enforcement for fresh clones, and a facts-first `role: subagent` bundle delivered per-provider (Claude: re-verified subagent flag + `--agents`/`Task` inline; Codex: shadow-home + in-payload inline; Muse: delegation-payload inline; Grok: `--rules` + `--agents` JSON) with parent→child provenance and exactly-once conformance.
