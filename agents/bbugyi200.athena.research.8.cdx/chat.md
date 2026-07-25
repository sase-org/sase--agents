# Chat History - ace-run

- **TIMESTAMP:** 2026-07-11 19:01:53 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.8.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260711_185728.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase This codebase contains a lot of backward compatibility logic that no longer serves any use because there are no projects that still need that logic. We need agents to always introduce backward compatibility logic because we don't want once this project becomes popular but we need a process or policy to govern how/when we should deprecate this logic. And most importantly we need a way to track and ensure that this logic always gets removed. Can you do some research to help me think about the different ways that we could implement this? End your analysis with a recommended solution. Once you're done writing your research file express your answer by setting a few sase variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I’ll research both the codebase’s existing compatibility patterns and established deprecation/removal mechanisms, then write a decision-oriented note ending with one recommended policy. I’ll use the `sase_var` skill at the end because you explicitly asked for named SASE outputs.

The initial scan confirms this is not hypothetical: compatibility paths are spread across config aliases, persisted-data migrations, CLI spellings, import façades, runtime payload formats, and tests. I’m narrowing the proposal around mechanisms that can cover all of those without treating every shim as the same kind of promise.

The strongest prior art converges on three ideas: define the protected contract, announce a concrete removal target, and make expiry machine-enforced. The important SASE-specific wrinkle is release velocity—eight minor versions landed in roughly three weeks—so “keep for N releases” alone would produce surprisingly short compatibility windows.

The research note is complete and passes a whitespace/diff check. The `sase_var` skill now has me publishing compact outputs for downstream agents: the report path, completion status, and the recommended mechanism.

Research completed: [backward_compatibility_sunset_policy_research.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.sase/sdd/research/202607/backward_compatibility_sunset_policy_research.md)

Recommended: an expiring compatibility ledger connected to source/test markers, pre-created removal beads, and CI-enforced calendar plus release deadlines.

Set SASE variables:

- `status`
- `research_path`
- `recommendation`
- `default_windows`
