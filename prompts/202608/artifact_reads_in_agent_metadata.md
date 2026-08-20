- **PLAN:**
  [202608/artifact_reads_in_agent_metadata.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_reads_in_agent_metadata.md)
- **AGENTS:**
  - [bbugyi200.athena.08m--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08m.md)

We recently addded the `sase artifact read` command. Can you help me make it so, when
sase agents use this, we show which files were read in a new `Reads:` sub-sub-section
under the `SASE CONTEXT` section's `ARTIFACTS` sub-section in the agent metadata panel?

I want you to lead the design on this one. Make sure you design this feature so it is
intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
