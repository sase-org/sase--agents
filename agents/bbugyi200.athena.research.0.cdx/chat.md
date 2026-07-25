# Chat History - ace-run

- **TIMESTAMP:** 2026-07-07 22:24:21 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** research.0.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260707_221544.md`

## Prompt

%name:research.@.cdx %model:@research %g:research #gh:gh_sase-org__sase We currently store all plans, prompts, research markdown files, and sase beads directly in this repo in the sdd/ directory. This results in a very large number of git commits that are not related to the code. This clutters the git history. I would like to start using a separate GitHub repo for these files per project. We should search for this repo in the same GitHub organization in a repo named either `sdd` or `<project>-sdd`, where `<project>` is the name of the main repo (`sase` in the case of this repo). Each VCS type should be able to opt in to this behavior. BareGit repos should continue to use the old behavior but the GitHub VCS should opt in. Can you do some research to help me understand the best way to implement this? End your analysis with a recommended approach. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.


## Response

I’ll inspect how `sdd/` paths and VCS backends are currently wired, then check the GitHub linked repo through the SASE workspace mechanism before writing the research note.

The first broad search confirmed the scale problem, so I’m narrowing to path construction, project lifecycle, bead storage, and VCS/provider abstractions. I’ll avoid touching canonical memory files and only create the requested research note.

I found SDD-specific modules under `src/sase/sdd/` and bead storage logic under `src/sase/bead/`. Next I’m opening the linked `sase-github` workspace as instructed so I can see where GitHub-specific repository lookup belongs.

The GitHub linked workspace is available now. I’m reading the local SDD write/commit paths first, then the VCS hook contracts and the GitHub plugin implementation to identify the smallest extension point.

The current core shape is clear: SDD location is computed from `workspace_dir`, workspace number, and a boolean `sdd.version_controlled`, while commits are local git operations against whatever directory is returned. I’m checking call sites now to see whether this can be generalized without changing all plan/bead writers.

Plan approval archives the pending plan immediately on the host side before the runner sees the response; that means SDD repo resolution has to be available outside agent launch too, not just inside workspace setup. I’m reading that archive path and the runner’s plan commit path next.

A few more call sites matter: accepted plans write both prompt snapshots and plan files, then optionally commit or initialize beads. I’m checking those details plus the current provider hook specs so the recommendation can preserve existing behavior for bare git.

The existing VCS hook spec has no SDD-specific operation yet, so this likely wants a new provider hook or a small SDD storage resolver service that delegates to a hook. I’m checking how plugin dispatch and workspace provider hooks are registered before recommending that shape.

The dispatch layer already separates VCS operations and workspace discovery. A provider-owned SDD resolution hook fits better in the VCS side because the user specifically wants each VCS type to opt in, while workspace hooks can still help clone or open the companion repo.

I have the core side now. I’m switching to the GitHub plugin code to confirm how it resolves `owner/repo`, stores project metadata, and whether it already exposes APIs for repo lookup and cloning.

The GitHub plugin already has both `sase_vcs` and `sase_workspace` entry points, with workspace resolution able to clone `owner/repo` and create project records. I’m reading the relevant functions in full now, especially `resolve_gh_ref`, clone URL selection, and repo completion.

One read used a bad path; I’m re-reading the missing `resolve_gh_ref` section. After that I’ll synthesize the implementation options and write the markdown file.

The companion repo lookup can reuse the plugin’s existing `owner/repo` resolver after deriving candidate refs. I’m checking config defaults and docs for `sdd.version_controlled` so the research note can call out migration and compatibility implications.

`docs/sdd.md` confirms local mode already exists to avoid main-repo history churn, but the new requirement is different: GitHub projects should use a shared companion repo, not local-only `.sase/sdd`. I’m reading the SDD link resolver next because plan search and validation are tied to it.

I also found the bead fast path, which bypasses some higher-level Python helpers. The recommendation needs to route that path through the same SDD root resolver, otherwise bead edits would keep going to the code repo.

I’m checking commit workflow handling for bead state because companion SDD changes should not be committed into the code PR, but still need their own commit/push behavior.

Commit dispatch currently stages `sdd/beads/` and `_plan_path` from the code checkout. A companion repo design should move SDD commit/sync into the SDD storage service and leave code commit dispatch focused on code changes plus references.

I’ve got enough code context for the research. I’m drafting the note with concrete file/function references, implementation options, risks, and a recommended approach.

One subtlety: if the code checkout no longer has `sdd/`, follow-up agents still need a stable way to read plan files. The research will recommend preserving `sdd/...` as a logical SDD reference resolved through the storage service, instead of leaking companion checkout absolute paths into beads and commit metadata.

I’m going to create `sdd/research/202607/github_companion_sdd_repo.md`. The note will keep the recommendation at the end as requested.

The research note is written. I’m doing a quick verification pass on the new file and git status; this change is only under `sdd/research`, so the repo instructions do not require `just check`.

Created the research note here:

[sdd/research/202607/github_companion_sdd_repo.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sdd/research/202607/github_companion_sdd_repo.md:1)

It covers the current SDD/bead write paths, the GitHub plugin extension points, implementation options, migration notes, and ends with the recommended approach: add a core `SddStore` resolver plus an optional VCS hook, with `sase-github` resolving `<project>-sdd` before `sdd`, while `bare_git` keeps the existing behavior.

I did not run `just check` because the only change is a new markdown file under `sdd/research/`, which is listed as an exception in the repo instructions.

I made that research file, so I’m handling the finalizer by using the SASE commit workflow for just that markdown file.

I’ve recorded the commit skill usage. Next I’m verifying the exact uncommitted state and diff so the commit only includes the research note.

The only uncommitted path is the new research markdown file. Since it is untracked, plain `git diff` has no body, so I’m reading the file once and then committing that single path.

The file is a documentation-only research note, so I’m using a `docs:` commit message and staging only that file with `-f`.

The commit message file is ready. I’m running the SASE commit wrapper now; it will commit first and then handle any push/rebase bookkeeping for this workflow.

The commit workflow is still running, currently in its precommit/dispatch phase. I’ll wait for it to finish before reporting the result.

The SASE commit wrapper completed successfully. I’m checking the branch state now to confirm the working tree is clean and nothing remains ahead.

Committed the research note with the SASE commit workflow:

`docs: research GitHub companion SDD repositories`

The working tree is clean afterward. I did not run `just check` because the only project change was under `sdd/research/`, which the repo instructions exempt.
