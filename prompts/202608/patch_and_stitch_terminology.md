- **PLAN:**
  [202608/patch_and_stitch_terminology.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_and_stitch_terminology.md)
- **AGENTS:**
  - [bbugyi200.athena.vu--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vu.md)

I want to rename ChangeSpec to Patch and want to add a new term, "stitch", to describe a
lightweight, commit-like object. Can you help me update ALL references (be thorough)
without changing (or breaking) any existing behavior?

- Every PR should be associated with a Patch (we need to eventually sync externally
  created PRs by creating local Patches for them automatically, but that is out-of-scope
  for now), but not every Patch is necessarily associated with a PR.
- Similarly, every commit should be considered / associated with a stitch, but not every
  stitch is associated with a commit (for example, proposals on Patches--which use a
  number and letter in their ID--do not have commits associated with them).
- Make sure to update the sase/memory/glossary.md file accordingly. Make sure you keep
  this file's contents concise, and remember that every token in context either helps or
  hurts us.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
