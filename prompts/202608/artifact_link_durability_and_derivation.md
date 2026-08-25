- **PLAN:**
  [202608/artifact_link_durability_and_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-tj.land.w3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md)

Can you help me fix the artifact link defects detected by / make the artifact link
improvements recommended by the artifact_link_derivation.md file in the research sidecar
repo?

- After you've completed this work, my plan is to add a rich integration with artifact
  links to every tab in the TUI (even chops can link to the agent artifacts they were
  responsible for launching!). This is out of scope for your work, but you may want to
  keep this functionality in mind.
- As a part of this work, you should also add support for the `relation:`, `linked:`,
  and `artifact:` query filters to the "Agents" sub-tab of the "Artifacts" tab (the
  agent_catalog_pane.md file in the research sidecar repo specifically recommended
  punting on this until we fix the artifact link defects you will address now).
- Answers to the open questions in the research file (see the "Open questions for the
  owner" section) can be found below:
  1. A plan implements a beads requirements.
  2. Sure.
  3. I've just finished implementing the new "Agents" sub-tab on the "Artifacts" tab to
     prepare to make artifact links more useful (see the sase-tj epic bead for context).
  4. Every read.
  5. Maybe… Try to make sure that the graph is completely up-to-date, but keep in mind
     that links connecting to agents should only be published when the agent has made
     commits (and thus has also been published).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
