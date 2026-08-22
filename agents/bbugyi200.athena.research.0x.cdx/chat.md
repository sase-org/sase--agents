# Chat History - ace-run (research.0x.cdx)

- **TIMESTAMP:** 2026-08-22 16:46:45 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0x.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260822_162922.md`

## Prompt

%clan(research.0x, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to implement a new `%if` directive that allows
me to specify (in the prompt) that agents should only only launch if a particular
condition, specified by a new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context and make sure this
  research either aligns with that research or that you reconcile any differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.0x.cdx
%model:@research_a 
#gh:gh_sase-org__sase I would like to implement a new `%if` directive that allows
me to specify (in the prompt) that agents should only only launch if a particular
condition, specified by a new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context and make sure this
  research either aligns with that research or that you reconcile any differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to trace the existing directive/parser and launch pipeline, review the standalone launch-unit research in the sidecar, and reconcile both into a concrete design recommendation. I’m using the SASE repository, memory-read, and artifact guidance because this crosses xprompt semantics and a research-sidecar boundary; I’ll write the result to the requested August 2026 research directory.

The existing launch-unit research is in the same August sidecar collection and is directly relevant: it treats agent and proc launches as variants of one normalized launch unit. I’m now checking where conditional evaluation belongs relative to swarm expansion, directive extraction, dependency validation, and process launch, because that placement determines whether skipped branches can leave broken `%wait` edges.

A key distinction is emerging: `%if` is not just metadata parsing. Its body is executable launch-time code, so planning must remain pure, previews must expose the condition, and execution must happen only after launch authorization. A false result should be a first-class “skipped” outcome; a parse/runtime error should abort rather than silently masquerade as false.

The main design tension is now clear: `%if` should gate a fully expanded launch unit, while the fenced condition body must stay opaque to prompt expansion. I’m reconciling that with the proc proposal by making both features share one structured code value and interpreter contract, without turning conditions into persistent procs.

The report draft now has a concrete semantics table and launch ordering. I’ve chosen “false is a first-class skip; every other nonzero outcome is an error,” because treating all nonzero exits as false would silently hide shell/Python mistakes—especially harmful in a swarm preflight.

The recommendation now explicitly covers swarm fanout and waits: conditions are evaluated per final expanded unit, but all predicates finish before any shell starts. A skipped predecessor remains a terminal logical unit, so bare `%wait` bindings stay stable rather than silently shifting to another agent.

The report is complete and verified as a research-only sidecar change; its final artifact hash matches the source, and it is explicitly linked as deriving from the standalone-proc research. I’m now running the required SASE final declaration; this won’t alter the report.

Research completed: [conditional_launch_if_directive.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202608/conditional_launch_if_directive/conditional_launch_if_directive.md).

Recommended design:

- `%if::` consumes one fenced Bash or Python `CodeValue`.
- Conditions attach to fully expanded typed launch units.
- Evaluate all conditions after approval but before allocating workspaces, names, artifacts, or processes.
- Exit `0` launches, `1` records a skip, and any other failure aborts the batch.
- Share parsing and execution-safety primitives with `%proc`, without representing conditions as persistent procs.
- Preserve logical unit identities so skipped units interact predictably with `%wait`.

The report reconciles the standalone-proc research, examines current SASE internals and external precedents, and includes rollout and testing recommendations.
