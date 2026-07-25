# Chat History - ace-run

- **TIMESTAMP:** 2026-07-11 11:52:27 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.7.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260711_114618.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I've been thinking about getting rid of the concept of stand-alone xprompts (preficed with `#!` when invoked). I think the idea behind these was that there is no xprompt part inside of a stand-alone xprompt, so there's no way to embed a stand-alone xprompt inside of a prompt that has other text. I don't think that constraint really holds since we can always prepend the text that came before a stand-alone xprompt invocation and append the text that came after to the first agent in that xprompt workflow, right?

Can you do some research to help me confirm or deny these claims? End your analysis with a final recommendation on whether or not I should get rid of the concept of stand-alone xprompt workflows (i.e. get rid of the `` syntax and always use just `#` for xprompts). Once you've concluded your research, express your answer by setting some SASE variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I’m using the `sase_memory_read` skill because this directly concerns xprompt semantics, then `sase_var` to express the conclusion in the requested run variables. I’ll trace parsing, expansion, workflow launch, tests, and docs, and write the evidence-backed recommendation into the requested research directory.

The project memory confirms the intended split: `#name` expands inline through a `prompt_part`, while `#!name` launches a standalone YAML workflow. I’m now checking whether that distinction is merely syntactic or whether launch-time behavior—step ordering, dependencies, directives, fan-out, environment, and non-agent steps—makes the proposed prefix/suffix rewrite unsafe.

A key historical fact is that this exact distinction was deliberately added on April 30 after prior research: the old `#` form for no-`prompt_part` workflows still works only as a compatibility path and warns. Your proposed composition is therefore testable against both the pre-change flattening behavior and the newer inline-safety rules. So far, it holds for a narrow class—one selected standalone workflow whose first executable LLM step is unambiguous—but not yet for the workflow model in general.

The resolved catalog makes the counterexample concrete: 9 standalone workflows are currently visible, and 6 have no direct agent step at all. Two others (`sync` and `fix_just`) have conditional/repeated or multiple agent steps, so “the first agent” is not a stable semantic insertion point. I’m capturing that inventory, the compatibility behavior, and the narrower viable alternative—single-prefix dispatch while retaining non-embeddability—in the report.

The report is written. Its conclusion is to keep `#!`: the marker distinguishes pipeline execution from prompt substitution, and the proposed splice would require inventing behavior for agentless, skipped, repeated, parallel, and multi-agent workflows. I’m doing a focused verification of the existing flattening, inline-safety, catalog-kind, and completion tests before setting the final SASE variables.

Verification passed: 83 focused tests covering workflow flattening, inline rejection, catalog classification, and completion behavior. The report also passes whitespace checks. The `sase_var` skill now causes the requested final action: I’m recording the recommendation, claim assessment, and report path as run variables.

Recommendation: keep standalone xprompt workflows and the `#!` syntax.

The proposed first-agent splicing rule fails generally: 6 of 9 current standalone workflows have no direct agent step, while others conditionally skip, repeat, or select among multiple agents. An internal agent is not equivalent to an explicit `prompt_part` boundary.

Research: [standalone_xprompt_workflow_reconsideration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.sase/sdd/research/202607/standalone_xprompt_workflow_reconsideration.md)

Set SASE variables:

- `recommendation=keep_standalone_xprompt_workflows_and_bang_syntax`
- `remove_standalone_xprompt_workflows=no`
- `remove_bang_syntax=no`
- `claim_assessment=core_first_agent_splicing_claim_denied`
- `research_path=.../standalone_xprompt_workflow_reconsideration.md`

Verification: 83 focused tests passed.
