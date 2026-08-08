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

#plan