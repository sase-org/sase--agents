- **PLAN:**
  [202608/muse_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)
- **AGENTS:**
  - [bbugyi200.athena.ve--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.ve.md)

Can you use the research in the muse_code_harness_provider.md file in the research
sidecar repo to implement a new LLM provider that integrates Meta's Muse Code into sase?

- I've already installed Muse Code (explore its functionality via the `muse` command)
  onto this machine and it is properly authenticated but make sure to add proper support
  for updating and installing this agent CLI using sase.
- Make sure that this new agent CLI has full support across all of sase's agent CLI
  integration surfaces (where possible).
- As far as the model catalog goes, see #sshot:3, #sshot:2, and #sshot for the
  up-to-date Muse Spark model names/descriptions.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
