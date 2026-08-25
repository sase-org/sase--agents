#gh:gh_sase-org__sase Can you help me fix the artifact link defects detected by / make the artifact
link improvements recommended by the artifact_link_derivation.md file in the research
sidecar repo?

- After you've completed this work, my plan is to add a rich integration with artifact
  links to every tab in the TUI (even chops can link to the agent artifacts they were
  responsible for launching!). This is out of scope for your work, but you may want to
  keep this functionality in mind.
- Answers to the open questions in the research file (see the "Open questions for the
  owner" section) can be found below:
  1. A plan implements a beads requirements.
  2. Sure.
  3. I've just finished implementing the new "Agents" sub-tab on the "Artifacts" tab to
     prepare to make artifact links more useful (see the sase-tj epic bead for context).
  4. Filtered for the first pass, as recommended.
  5. Maybe… Try to make sure that the graph is completely up-to-date, but keep in mind
     that links connecting to agents should only be published when the agent has made
     commits (and thus has also been published).

#plan #m_opus %w:sase-tj.land