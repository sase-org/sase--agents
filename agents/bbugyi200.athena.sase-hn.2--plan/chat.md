# Chat History - ace-run (sase-hn.2--plan)

- **TIMESTAMP:** 2026-08-08 13:46:36 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-hn.2--plan

**Plan:** /home/bryan/.sase/plans/202608/python_patch_storage.md


## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-hn, bead=sase-hn.2)
%model:@large_phase_worker
%auto
%w:sase-hn.1
%w(bead=sase-hn.1)
Can you complete the work for bead sase-hn.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-hn.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-hn.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/python_patch_storage.md`

> - **PARENT:**
>   [202608/patch_and_stitch_terminology.md](202608/patch_and_stitch_terminology.md)
> - **BEAD:** sase-hn.2
> # Complete `sase-hn.2`: canonical Python Patch domain and ProjectSpec storage
> ## Goal
> Make `sase.ace.patch` and the Python `Patch`/`Stitch` wire surface canonical while
> preserving the behavior and data contracts of the existing ChangeSpec implementation.
> Both canonical (`## Patch`, `STITCHES:`, `stitches`, `stitch_id`) and legacy
> (`## ChangeSpec`, `COMMITS:`, `commits`, `commit_entry_num`/`entry_id`) inputs must
> remain readable. Existing legacy Python imports and attributes must remain thin aliases

*See full plan file for details.*

