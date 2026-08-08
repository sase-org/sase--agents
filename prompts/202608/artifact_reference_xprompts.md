- **PLAN:**
  [202608/artifact_reference_xprompts.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_reference_xprompts.md)
- **AGENTS:**
  - [bbugyi200.athena.vw--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vw.md)

Can you help me start defining artifact references (ex: `@commit` or `@research`) as
xprompts?

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

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
