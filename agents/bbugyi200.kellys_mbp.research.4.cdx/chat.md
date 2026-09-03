# Chat History - ace-run (research.4.cdx)

- **TIMESTAMP:** 2026-09-03 16:50:33 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.4.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_163453.md`

## Prompt

%clan(research.4, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add the ability for users to add new projects
in bulk from the "Projects" tab on the "SASE Admin Center" panel.

- This will be useful, for example, when users are onboarding a new machine and want to
  enable the set of projects they are currently working on for that machine.
- We should provide excellent completion for the organizations/repos that the user is
  most likely to select.
- See how we do this for the `#gh` VCS xprompt workflow's argument for inspiration.
- We need to make sure to do this in a VCS-agnostic way so future VCS plugins are
  supported automatically.
- As a part of this change we should stop auto-enabling new projects that are created
  when an argument is passed to a VCS xprompt workflow that is associated with a new
  (i.e. currently unknown to this machine's sase) project.

Can you do some research with the goal of helping me decide the best way to implement
this? In particular, think very hard about what the best UX for this functionality looks
like. End your analysis with a recommended solution.]]) %id:research.4.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I would like to add the ability for users to add new projects
in bulk from the "Projects" tab on the "SASE Admin Center" panel.

- This will be useful, for example, when users are onboarding a new machine and want to
  enable the set of projects they are currently working on for that machine.
- We should provide excellent completion for the organizations/repos that the user is
  most likely to select.
- See how we do this for the `#gh` VCS xprompt workflow's argument for inspiration.
- We need to make sure to do this in a VCS-agnostic way so future VCS plugins are
  supported automatically.
- As a part of this change we should stop auto-enabling new projects that are created
  when an argument is passed to a VCS xprompt workflow that is associated with a new
  (i.e. currently unknown to this machine's sase) project.

Can you do some research with the goal of helping me decide the best way to implement
this? In particular, think very hard about what the best UX for this functionality looks
like. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to trace the existing Projects-tab and `#gh` completion flows, then map the underlying project/VCS abstractions before comparing UX options. I’ll use the SASE memory/project/artifact guidance because this touches xprompts and a research output under `sase/repos/research`.

There is already a September research package named `projects_tab_init_ux`, so I’m checking it as prior art rather than duplicating its conclusions blindly. I’m also separating the destination sidecar from the main implementation repository so the final report can state exactly which pieces belong in Rust core, the Python adapter, and ACE.

The existing completion stack already has the right raw ingredients: providers advertise workflows, local namespace suggestions, and remote repository candidates; core adds caching, stale fallback, filtering, and “recently pushed first” ranking. The key design question is therefore whether bulk onboarding should reuse that two-stage contract directly or introduce a new provider API—and how to keep selection, network loading, and project creation transactional.

I’ve mapped the existing Projects UI, the provider-backed `#gh` completion pipeline, and the launch lifecycle. The key design constraint is now clear: simply creating unknown projects as disabled would make the ensuing launch fail after doing clone/setup work, so the recommendation needs to separate project enrollment from launch resolution cleanly. I’m turning that into the decision report now.

The strongest UX is a provider-driven “selection basket,” not a paste box and not a giant global repository list: choose a source/namespace, mark repositories across filters and namespaces, review once, then add with per-item progress. I’m also specifying a small remote namespace-discovery extension, because today’s `#gh:` root completion only knows locally configured orgs—too weak for a pristine machine unless `github_orgs` happens to be synced.

The report is written. Its central recommendation is to block unknown VCS launch refs before any clone or project-file mutation, while preserving today’s separate behavior for explicitly launching a known disabled project. That avoids changing the backward-compatible “missing state means enabled” rule and gives enrollment one clear, user-confirmed home. I’m doing the final repository and document checks now.

Research completed and saved to [bulk_project_onboarding_ux.md](</Users/bbugyi/Library/Application Support/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202609/bulk_project_onboarding_ux.md>).

The recommendation is a provider-neutral, multi-select “Add Projects” modal backed by the existing VCS completion infrastructure, plus a pre-resolution guard that rejects unknown project refs before cloning or creating project state. The report covers UX, ranking, provider APIs, lifecycle behavior, failure recovery, rollout order, and testing.

Validation: Markdown whitespace checks passed.
