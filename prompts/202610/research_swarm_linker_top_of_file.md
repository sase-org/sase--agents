- **PLAN:**
  [202610/research_swarm_linker_top_of_file.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_linker_top_of_file.md)
- **AGENTS:**
  - [bbugyi200.athena.0v3--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v3.md)

Can you help me improve the instructions for the linker agent in the `#research_swarm`
xprompt swarm?

- If the image agent generated an image then the linker should be instructed to position
  that image directly above the "Bottom line" / "Overview" section at the top of the
  file.
- The agent should always be instructed to put the research query (i.e. a summarized
  version of the prompt input that was passed to the `#research_swarm` xprompt swarm) at
  the very top of the file (above the "Bottom line" / "Overview" section or above the
  image, if one was generated).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
