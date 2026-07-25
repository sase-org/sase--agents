# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 13:52:18 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.d.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_134144.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I want to unify agent families so users can more
easily conceptualize them as just a different way of grouping agents on the
agents tab. Can you do some research to help me understand what conceptual
barriers I'm going to need to design around / implement solutions for in order
to make this happen? Keep in mind that part of the goal is to migrate as much
functionality from xprompt workflows (YAML files) as possible to xprompt swarms
(markdown files), which I would ideally like to be able to use to define
workflows that are just as robust as those that we currently define using YAML
xprompt workflows. For example:

- I know that I will need to allow agents in the same family to run in parallel.
  I plan on adding support for a new `wait=<bool>` keyword argument to the
  `%name` directive for this.
- I know that Python and Bash xprompt workflow steps will need to be allowed to
  be root agent rows in order to support, for example, defining an xprompt swarm
  that requires a command to be run that updates the software you are working on
  (e.g. sase) before one or more agents (e.g. to verify the work) can run.
  Moreover, this is just needed to make them definable in xprompt swarms I
  think, which would be preferable to xprompt workflows.

What are some of the requirements I have not thought of? Are there any design
decisions that you would absolutely need from me before working implementing
something like this? End your analysis with a set of <=7 of the highest-value
questions you can think to ask to help push this initiative forward. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to trace the current family, swarm, and YAML-workflow models through the code and tests, then map the semantic gaps between them. I’ll use the SASE memory-read skill for the required xprompt context and the repo skill to access the research sidecar safely; the final artifact will emphasize implementation requirements, migration hazards, and no more than seven decision questions.

The xprompt memory is now the governing reference for how directives, swarms, and workflows are intended to behave. I’m also resolving the research sidecar through SASE before touching the requested output path; I’ll keep source inspection in this workspace read-only and make only the requested research-file addition.

A key early finding is that “family” is currently much more than a visual grouping: it is simultaneously a naming convention, lifecycle state machine, dependency target, metadata aggregation scope, and action scope. I’m separating those contracts from the Agents-tab presentation so the report can distinguish “must preserve” semantics from historical implementation coupling.

There is prior research in the sidecar on dynamic families and standalone xprompts, so I’m incorporating it instead of rediscovering old decisions. The current initiative is broader: it needs a common execution/grouping model that can represent plain fan-out, DAG dependencies, lifecycle-driven expansion, non-agent commands, and human gates without making every grouped row pretend to be a plan-chain family.

The `wait=false` idea exposes a deeper contract than launch ordering: a running family child currently inherits the parent’s exact workspace only because it is implicitly queued until that parent finishes. Parallel family members therefore need an explicit workspace-isolation policy; otherwise two rows in one visual family can concurrently edit the same checkout. I’m treating workspace visibility/ownership as a first-class design decision, not a small directive-parser change.

The research now points to a clean architectural boundary: make “family” an explicit run-group record, make execution dependencies separate graph edges, and treat the plan chain as an optional lifecycle controller on that group. That separation is what allows parallel children, command roots, static swarms, and dynamic plan/question handoffs to coexist without continuing to overload `parent_timestamp`, `workflow_name`, and `--`-delimited names.

The draft is written. I’ve kept the final decision set to seven questions and made one strong recommendation throughout: use one common run-graph runtime for YAML and Markdown, then migrate definitions by semantic class. I’m doing a final consistency pass now—especially checking that the report distinguishes UI grouping from lifecycle behavior and that no current capability is accidentally described as swarm parity.

Created the research report:

[unifying_agent_families_with_xprompt_swarms.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202607/unifying_agent_families_with_xprompt_swarms.md)

Core conclusion: grouping, dependencies, display hierarchy, workspace ownership, and lifecycle control must become separate concepts. Full Markdown parity will likely require YAML and swarms to compile into a shared durable run-graph runtime.

The report ends with exactly seven high-value design questions. No source files were changed.

The finalizer identified the research file I created, so I’m applying the required SASE commit workflow to that sidecar now. Afterward I’ll verify the research repository is clean.

The diff is limited to the requested new report. I’m committing it as documentation with an explicit file scope so the temporary commit-message file and any unrelated sidecar changes cannot be staged.

Committed the research report through the required SASE workflow and verified the sidecar repository is clean and synchronized.

[View the report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202607/unifying_agent_families_with_xprompt_swarms.md)
