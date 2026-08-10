- **PLAN:**
  [202608/external_artifact_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)
- **AGENTS:**
  - [bbugyi200.athena.xp--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.xp.md)

Can you help me ensure (continuously) that every issue in an external tracker
(associated with a sase project) has a corresponding bead, and every PR not created by
SASE has a corresponding Patch, for every enabled project on a machine?

- Also, let's merge the "Bugs" sub-tab of the "Artifacts" tab into the "Beads" sub-tab
  and rename the "PRs" sub-tab to "Patches".
- The new sub-tabs of the "Artifacts" tab should be (in this order):
  - Stitches
  - Patches
  - Beads
  - Files
- Make sure you do an excellent job of integrating external issues/PRs into
  beads/Patches. For example, make sure that it is very clear (in a visually appealing
  way), when an issue/PR is associated with a bead/Patch.
- See the external_artifact_ingestion.md file in the research sidecar repo for context
  and inspiration.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
