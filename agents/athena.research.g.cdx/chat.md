# Chat History - ace-run

- **TIMESTAMP:** 2026-07-17 09:53:29 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.g.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260717_094120.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research %family(research.@.final, role=researcher) #gh:gh_sase-org__sase Can you do some research on best-practices for top-level README.md files in GitHub projects with the goal of helping me improve this project's README.md file? End your analysis with a list of recommended changes I should make to this project's README.md file. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll assess the current README against authoritative GitHub and documentation-writing guidance, then write a project-specific report with prioritized recommendations. I’m using the `sase_artifact` skill because the requested research file is an explicit run artifact; I’ll follow its registration workflow after creating the Markdown file.

The current README already has a strong “landing page” structure: clear value proposition, visual proof, a four-command quick start, links to deeper docs, contributor setup, and licensing. I’m now checking where it diverges from guidance on scannability, onboarding, accessibility, trust signals, and keeping README content distinct from full documentation.

One concrete issue stands out: this README is also published verbatim to PyPI, so GitHub-valid relative links and images are broken on the package page. I also measured the media: the three GIFs loop indefinitely for 20–32 seconds each, and the README’s four visual assets total about 6.7 MiB.

The requested destination is the project’s research sidecar, so I’m now using the `sase_repo` skill to resolve and write to that linked repository through the required workspace-safe path.

The report is drafted and ends with a prioritized 12-item change list, as requested. I’m doing the final evidence pass now: checking the PyPI failure directly, Markdown formatting, and the sidecar diff before registering the artifact.

Research complete: [GitHub README best-practices report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202607/github_top_level_readme_best_practices.md).

The highest-priority findings are:

- Relative README links and images break when published to PyPI.
- Three indefinitely looping GIFs create accessibility and performance issues.
- Quick start should precede the demo gallery.
- Platform support, alpha status, CI health, support, and contribution routes should be clearer.

The report ends with 12 prioritized README changes. It was formatted with Prettier and its cited links were checked.

Artifact ID: `explicit:e020069a7e218120820958be`  
Stored artifact: [registered copy](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260717094120/github_top_level_readme_best_practices.artifact-934d3857260e.md)

The research file is mine, so I’ll complete the finalizer by committing that single file in the research sidecar. I’m using the `sase_git_commit` skill because this environment requires its guarded commit workflow, then I’ll verify the sidecar is clean.

The diff contains only the requested research report, and the file is untracked as expected. I’ve confirmed there are no unrelated sidecar changes; I’m committing it as a documentation-only change.

Committed and pushed the research report:

- Commit: `782fbfb docs: research top-level README best practices`
- File: [github_top_level_readme_best_practices.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202607/github_top_level_readme_best_practices.md)
- Research sidecar is clean and synchronized with `origin/main`.
