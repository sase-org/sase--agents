# Chat History - ace-run (09r--plan)

- **TIMESTAMP:** 2026-08-21 12:08:45 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 09r--plan

**Plan:** /home/bryan/.sase/plans/202608/simple_artifact_ref_expansion.md


## Prompt

#gh:gh_sase-org__sase Can you help me migrate the artifact ref expansion for all artifact ref types to a simple reference like the `@research` ref does?

- Also, no more `@` prefixes for file path references.
- For example, `@plan:202608/foobar.md` should now resolve to `the 202608/foobar.md file in the plans sidecar repo`.
- Make sure you review and simplify the ref expansion for all known artifact ref types.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %w(runners=100)

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/simple_artifact_ref_expansion.md`

> # Simplify every artifact-reference prompt expansion
> ## Problem
> Artifact references have one authoring grammar but several unrelated prompt-expansion
> implementations. Document providers render an `expansion_format`; `stitch` and `patch`
> render inside their resolvers; and `chat`, `file`, `bead`, and `agent` fall through a
> legacy renderer that emits `@<absolute-path>`. The result is inconsistent and leaks
> workspace-local checkout paths into prompts. It also causes the following ordinary
> file-reference pass to reinterpret generated `@path` tokens, requiring staging
> suppression state between the two preprocessors.
> `@research` is the desired model. It expands to portable prose such as

*See full plan file for details.*

