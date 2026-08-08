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

#plan