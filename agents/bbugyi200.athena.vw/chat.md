# Chat History - ace-run (vw--plan)

- **TIMESTAMP:** 2026-08-08 13:32:21 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** vw--plan

**Plan:** /home/bryan/.sase/plans/202608/artifact_reference_xprompts.md


## Prompt

#gh:gh_sase-org__sase Can you help me start defining artifact references (ex: `@commit` or
`@research`) as xprompts?

- See the artifact_reference_rendering.md file in the research sidecar repo for context
  and inspiration.
- We should define these xprompts in a sase/refs/ directory, NOT a sase/artifact_refs/
  directory.
- These xprompts should be invocable by using the `#ref/` prefix.
- Make sure that appropriate xprompts are defined automatically for sidecar repos and
  that this xprompt can be customized via sidecar repo sase config fields.
- Make it so sidecar repos use `the <file_path> file in the <sidecar> sidecar repo` (for
  example,
  `@research:202608/artifact_reference_rendering/artifact_reference_rendering.md` should
  render to
  `the 202608/artifact_reference_rendering/artifact_reference_rendering.md file in the research sidecar repo`)
  as their xprompt expansion text by default.
- Make sure that sidecar repo configurations can also define filters so they control
  which file paths are valid artifacts (this should also control argument completion for
  that artifact reference). Sidecar repos should default to filtering for markdown files
  only.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/artifact_reference_xprompts.md`

> # Artifact reference xprompts
> ## Goal
> Treat each supported artifact-reference kind as a contextual xprompt named `ref/<kind>`.
> Users can continue to write the compact artifact form `@<kind>:<payload>`, or invoke the
> same definition explicitly as `#ref/<kind>:<payload>` (including the existing
> parenthesized and named-argument xprompt forms). Both spellings must share one resolver,
> one renderer, one consumption record, and one completion inventory.
> Reference definitions live under `sase/refs/`, never `sase/artifact_refs/`. Enabled
> sidecar repositories automatically contribute the appropriate reference xprompt. A
> path-backed sidecar defaults to accepting Markdown files and rendering a reference as:

*See full plan file for details.*

