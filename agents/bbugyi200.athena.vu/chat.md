# Chat History - ace-run (vu--plan)

- **TIMESTAMP:** 2026-08-08 13:05:25 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** vu--plan

**Plan:** /home/bryan/.sase/plans/202608/patch_and_stitch_terminology.md


## Prompt

#gh:gh_sase-org__sase I want to rename ChangeSpec to Patch and want to add a new term, "stitch", to
describe a lightweight, commit-like object. Can you help me update ALL references (be
thorough) without changing (or breaking) any existing behavior?

- Every PR should be associated with a Patch (we need to eventually sync externally
  created PRs by creating local Patches for them automatically, but that is out-of-scope
  for now), but not every Patch is necessarily associated with a PR.
- Similarly, every commit should be considered / associated with a stitch, but not every
  stitch is associated with a commit (for example, proposals on Patches--which use a
  number and letter in their ID--do not have commits associated with them).
- Make sure to update the sase/memory/glossary.md file accordingly. Make sure you keep
  this file's contents concise, and remember that every token in context either helps or
  hurts us.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/patch_and_stitch_terminology.md`

> # Patch and Stitch Terminology Migration
> ## Outcome and semantic contract
> Make these the canonical definitions in code, UI, documentation, and agent context:
> - A **Patch** is SASE's local unit of change. Every PR created or managed by SASE is
>   associated with exactly one Patch, but a Patch may exist without a PR, represented by
>   an absent `PR:` field / `pr_url`. Automatically importing externally created PRs by
>   creating local Patches is intentionally out of scope.
> - A **stitch** is the lightweight, ordered change record currently represented by a
>   `CommitEntry` in a Patch's `COMMITS:` section. Every VCS commit made through the
>   tracked workflow has an associated numeric stitch. A stitch need not have a commit:

*See full plan file for details.*

