# Chat History - ace-run (research.02.cdx)

- **TIMESTAMP:** 2026-08-08 10:45:25 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.02.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260808_103139.md`

## Prompt

%clan(research.02, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution.]]) %id:research.02.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the current xprompt, generated-skill, memory, artifact, and rendering paths, then compare extensibility options and write a decision-oriented report ending in one recommended design. I’m using the SASE memory, ChangeSpec, repo, and artifact-file skills because this spans xprompt rules, the `sase-hf` bead, a linked research repo, and durable artifact mechanics.

The current rules establish a useful split already: xprompts own user-facing expansion, while artifact infrastructure owns canonical resolution, staging, consumption tracking, and retention. I’m now checking the `sase-hf` migration intent and the exact code boundaries so the recommendation preserves that split rather than duplicating resolver behavior in templates.

The implementation history confirms the closest precedent: skills and memories are special xprompt source types with reserved namespaces and explicit catalog metadata, but they do not replace the underlying skill/memory domain logic. Artifact references need the same “special source” treatment, with a key difference: each definition must wrap a resolver-owned artifact value and render only after resolution.

A second design constraint emerged from the launch pipeline: raw `@kind:payload` text is what durable prompt archives later link, while the resolved text sent to the model is separate. That makes presentation safely customizable, provided canonical identity, resolution, staging, and tracking remain host-owned—and provided template output cannot re-enter command substitution, directives, or unrestricted Jinja evaluation.

I’ve finished the option analysis. The strongest design is a hybrid: package/project/home Markdown definitions control presentation and catalog metadata, while the Rust resolver continues to own grammar, canonicalization, capabilities, linking, staging, and lifecycle. I’m writing the report now with a concrete schema, precedence rules, safety boundaries, rollout strategy, and alternatives considered.

The report is drafted and the content checks out; its only current issue is repository Markdown formatting. I’m applying the repo’s formatter, then I’ll verify the final file and confirm the research repo contains only this new deliverable.

Created the research report:

[202608/xprompt_backed_artifact_references.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/xprompt_backed_artifact_references.md>)

Canonical reference: `research:202608/xprompt_backed_artifact_references.md`

It recommends resolver-owned, xprompt-rendered artifact references: customizable Markdown renderers under `sase/artifact_refs/`, while canonical resolution, linking, staging, consumption tracking, and retention remain host-owned. Formatting and artifact resolution were verified.

The research file is already complete; this finalizer pass only needs to commit that deliverable. I’m using the SASE git-commit skill because it is the required commit path for the linked research repository.

The finalizer’s file is the only uncommitted change, and it contains the completed decision report with the recommended hybrid design. I’m committing exactly that file as a documentation change.

The commit workflow is still completing its built-in synchronization and push checks. I’m blocking on it now and will verify the repository is clean before finishing.

Committed and pushed the research report:

- [xprompt_backed_artifact_references.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/xprompt_backed_artifact_references.md>)
- Commit: `2d7b53d docs: research xprompt-backed artifact references`
- Repository is clean and synchronized with `origin/main`.
