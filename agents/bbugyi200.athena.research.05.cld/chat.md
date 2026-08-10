# Chat History - ace-run (research.05.cld)

- **TIMESTAMP:** 2026-08-10 15:01:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.05.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260810_144802.md`

## Prompt

%id(cld, clan=research.05) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to start creating a corresponding bead for every
external bug (e.g. GitHub issue--but this should use our plugin system I think) created
for sase projects that are enabled on the given machine (I'm assuming we will use one or
more chops for this, but I am open to suggestions).

- I also want to do the same thing for Patches (i.e. create a new patch for each PR on
  enabled projects that was not created by a sase agent).
- I then want to merge the "Beads" and "Bugs" sub-tabs on the "Artifacts" tab in an
  elegant way that displays only beads but makes it very clear which beads are
  associated with bugs (and provides useful operations for editing/viewing those bugs).
- Again, we should do something similar for patches: Rename the "PRs" sub-tab of the
  "Artifacts" tab to "Patches" and start making it clear which Patches have PRs that
  were created externally associated with them. Keep in mind that, in the case of
  patches, sase agents do something create PRs and associate them with patches (so the
  existnce of a corresponding PR does not mean that the Patch was triggered by an
  external PR).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current architecture.

Now I have a complete picture. Writing the research report.

Written to `sase/repos/research/202608/external_bug_and_pr_mirroring.md`.

## What I found

Most of this is wiring on top of seams that already exist — with one real design decision that your own earlier epic already identified and deferred.

**Already built:** the issue-tracker provider seam (`vcs_list_issues/get/create/update/get_issue_url` in `_hookspec.py`, implemented over `gh` in `sase-github`, capability-probed structurally by `supports_issues()`), the pure `bug_links.py` cross-linker with bug-id normalization, the `bug:<project>#<n>` artifact-ref kind, and `bead_task_triage` as a proven template for a project-fanning store-writing chop.

**Missing:** any PR-listing hook. That's the only genuinely new provider surface, and it's a direct transcription of the issue seam from `e5d299582`.

## The one real decision

A task bead **cannot** carry a bug id today — `Issue.validate()` and the sase-core SQLite `CHECK` constraints both restrict `changespec_bug_id` to plan beads *and* require a companion `changespec_name`. I considered relaxing that (rejected: weakens a genuine invariant), stashing the link in `refs` (rejected as identity: no uniqueness, can't distinguish "mirrors" from "cites"), and a machine-local index (rejected: bead stores sync across machines).

Recommendation is the `external_ref` core field that `plans:202607/artifacts_tab.md` names verbatim as "the designed follow-up once bidirectional write-back is wanted." The additive-column migration has direct precedent in `schema.rs` (`needs_refs_migration`).

## Two other calls worth flagging

- **Mirrored beads should be `open` tasks, not `ready`** — a chop can't honestly pick a `--size`, and `ready` would raise a `TaskTriage` gate per incoming issue and flood the inbox on pass one.
- **The biggest hazard isn't the sync, it's what AXE does afterward.** `hook_checks`, `mentor_checks`, `workflow_checks`, and `pr_submitted_checks` all scan Patches and start real work. An adopted Patch has no branch, workspace, or stitches. Excluding `ORIGIN: external` has to land *in the same phase* as the PR mirror, or the first pass launches hook and mentor agents against PRs nobody asked us to touch.

Also: "external" must be **stored**, not inferred — your constraint that SASE agents create PRs too means a `PR:` field proves nothing.

The report ends with a six-phase epic (1–2 parallel; 3←1, 4←2, 5←3, 6←4) and four open questions for you — mirror scope, backfill watermark, upstream-close behavior, and whether to adopt third-party PRs or only your own.

I made that file — the research report is my work from this session. Committing it now.

Committed.

- `2ba1c85 docs(research): analyze external bug and PR mirroring into beads and Patches` in the `research` repo, staging only `202608/external_bug_and_pr_mirroring.md`.
- `git status --short --branch` reports `## main...origin/main` with no dirty files and no ahead/behind marker — clean and pushed.

The two entries in the finalizer list ("linked repo research" and "SDD sidecar repo research") resolve to the same checkout path, so this single commit covers both.

One warning from the commit, unrelated to the file: the project has 2 quarantined agent-hood publication requests, so the agent link written into this commit may not resolve until you run `sase agent sync --retry-quarantined`. The commit itself succeeded regardless.
