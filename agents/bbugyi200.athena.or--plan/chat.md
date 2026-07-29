# Chat History - ace-run (or--plan)

- **TIMESTAMP:** 2026-07-29 16:44:34 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** or--plan

**Plan:** /home/bryan/.sase/plans/202607/artifact_ref_completion_target_project_workspace.md


## Prompt

#gh:gh_sase-org__sase No completion triggers when I type `@res` in the prompt input widget
(see ~/tmp/screenshots/20260729_161932.png). I expected `@research:` to be
offered in the prompt input widget completion menu since `@research` is
configured as a sidecar repo for this project (see the sase-av epic bead for
context). Can you help me fix this?

- FWIW, this completion seems to be working for `@plans` artifacts in the prompt
  input widget.
- This is probably because I said to ignore the parts of the research that
  mentioned the `sase--research` repo since that is a custom user-defined (by
  me) sidecar repo.
- But that doesn't mean that it shouldn't trigger artifact completion. We should
  trigger this completion and support artifact resources from all custom sidecar
  repos.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/artifact_ref_completion_target_project_workspace.md`

> # Artifact-Reference Completion: Resolve the Catalog from the Target Project's Workspace
> ## Problem
> Typing `@res` in the `sase ace` prompt input widget offers no completion, even though `research` is a configured
> document-sidecar role for the prompt's target project (the prompt begins with a `#gh:<project>` VCS workflow tag).
> `@plans` completion works in the same prompt. The docs already promise the correct behavior — `docs/ace.md` (the
> "Artifact-reference completion" bullet, near line 3058) says kind completion filters "the four builtin kinds plus
> document roles configured for the prompt's target project" — but the implementation only delivers it for prompt bars
> whose session context belongs to that project.
> The same defect also degrades artifact-reference highlighting: a well-formed `@research:x.md` reference in a home-mode
> prompt bar paints with the `artifact_ref.unknown` style because the warmed known-kind set is missing the custom role.

*See full plan file for details.*

