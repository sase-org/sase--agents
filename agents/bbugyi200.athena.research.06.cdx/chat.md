# Chat History - ace-run (research.06.cdx)

- **TIMESTAMP:** 2026-08-10 18:25:40 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.06.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260810_175914.md`

## Prompt

%clan(research.06, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I'm trying to figure out a way to emulate an unprivileged (i.e. can't just commit to master) Github user so I can fork sase and attempt to contribute externally. This would make it way easier to test SASE's collaboration features, which are mostly theoretical at this point. Can you do some research with the goal of helping me figure out the best way to do this? End your analysis with a recommended solution.]]) %id:research.06.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I'm trying to figure out a way to emulate an unprivileged (i.e. can't just commit to master) Github user so I can fork sase and attempt to contribute externally. This would make it way easier to test SASE's collaboration features, which are mostly theoretical at this point. Can you do some research with the goal of helping me figure out the best way to do this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll investigate both sides of this: GitHub’s current identity/permission options and how SASE’s GitHub collaboration flow actually authenticates and handles forks. I’ll use primary GitHub documentation for the external facts, then write a recommendation-focused report in the requested directory and run the repository’s required checks.

The core checkout points to `sase-github` as the provider responsible for GitHub issue/PR workflows, so I’m using the `sase_repo` skill before inspecting that linked repository. That will let me verify whether the best GitHub-side setup is compatible with SASE’s real authentication and submission paths.

One important implementation constraint has emerged: SASE currently does `git push -u origin <branch>` and then runs `gh pr create` without explicit `--repo`, `--base`, or `--head`. That means a realistic setup has to get both the Git remote topology and the active `gh` identity right; merely limiting a token or protecting `master` would not exercise the actual fork-contribution path.

The fork topology exposes a concrete SASE gap worth recording: numbered workspaces clone only the primary checkout’s `origin`, while `sase-github` later runs bare `gh pr create`. They do not preserve/add the fork’s `upstream` remote or set GitHub CLI’s default repository, so an external-contributor clone can push to the fork but may create/query the PR against the fork itself. Per this repository’s task-tracking instructions, I’m using `sase_new_task` to check for an existing issue before recording that follow-up.

`sase_new_task` requires audited reads of the bead lifecycle and sizing notes before triage, so I’m also applying the `sase_memory_read` procedure now. This pauses the duplicate check only long enough to load those required policies.

The research now points to a two-plane setup: a genuinely external machine account for the code fork, plus narrowly scoped write access only to the SASE collaboration sidecars when you want to test cross-owner agent history. I’m writing that recommendation with an isolation recipe, a test matrix, and the current fork-workflow caveat; the final section will be the recommended solution as requested.

The report is drafted. Because it is the primary evidence for the discovered fork-workflow task, `sase_new_task` requires me to register it as a durable artifact before filing; I’m using `sase_artifact_file` for that linkage, then I’ll finish duplicate triage and repository verification.

The report is now registered as artifact `file:explicit:8724370e8f115791d2cd99c0`, and duplicate/epic triage found no existing owner for the fork gap. I recorded ready task `sase-ja` with that evidence. I’m doing the final document review now, then I’ll run `just install` and the required `just check`.

The required install is still compiling the linked Rust core; it has reached the `sase_core` crate and is progressing normally. The report itself is unchanged apart from the final clarification that `SASE_HOME` isolates state and machine selection, while the second identity overlay still lives under `~/.config/sase`.

The build is now on the Python binding crate. No failure has surfaced; this workspace simply needed a cold Rust rebuild. Once it completes, `just check` should be the only remaining step.

`just check` has passed all formatting, lint, Symvision, SASE validation, and committed-plan gates. It is now in the scoped test phase; no report issues were found.

Research completed: [github_external_contributor_emulation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/github_external_contributor_emulation.md)

Recommended approach: use an automation-only GitHub machine account with:

- Its own `sase` fork and no upstream code permissions.
- Isolated SSH, `gh`, Git, SASE state, and owner identity.
- Optional write access only to shared SASE sidecars, beginning with `sase--agents`.
- A `master` ruleset requiring PRs as defense in depth.

I also found that SASE is not yet reliably fork-aware across numbered workspaces and PR operations. I recorded this as ready task `sase-ja`, backed by artifact `file:explicit:14f29b2a26c4820c086039e9`.

Verification passed: `just check` and a direct Prettier check of the research file. No GitHub accounts, permissions, forks, or rulesets were changed.

The research report was created by this session, so I’m applying the required `sase_git_commit` workflow now. I’ll commit only that markdown file in the research sidecar, then confirm the repository is clean.

The commit scope is exactly the new research report, with a documentation-only commit message. I’m committing that file now; the wrapper will handle its normal sync and push workflow.

The commit succeeded. SASE reported two pre-existing quarantined agent-hood publication requests; that does not affect the research commit, and retrying them would be outside this finalizer’s scope. I’m checking the research repository’s branch and cleanliness now.

Committed the completed research report:

[github_external_contributor_emulation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/github_external_contributor_emulation.md)

Commit: `e9248ec` (`docs: research external contributor emulation`)

Recommended solution: an isolated automation-only GitHub machine account with its own fork, credentials, and SASE profile, plus narrowly scoped access to collaboration sidecars. The research repository is clean and synchronized with `origin/main`.
