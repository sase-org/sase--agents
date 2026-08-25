#gh:gh_sase-org__sase I was working on improving artifact links when it was brought to my attention
(see the artifact_link_derivation.md file in the research sidecar repo for context) that
the "Agents" sub-tab of the "Artifacts" tab is a major missing piece that prevents us
from fully benefiting from artifact links.

- My plan is therefore to:
  1. Implement the "Agents" sub-tab.
  2. Make the improvements / fix the defects related to artifact links which are
     referenced in the artifact_link_derivation.md file in the research sidecar repo.
  3. Add a rich integration with artifact links to every tab in the TUI (even chops can
     link to the agent artifacts they were responsible for launching!).
- The "Agents" sub-tab should support excellent filtering via a query language that
  integrates well with the shared query infrastructure already used by the artifacts
  tab. I'm not sure how much work has already been done here but we want to make sure
  this new agent query language is exceptionally useful.
- We should still support the custom agent revival panel on the main "Agents" tab
  (triggered via the `R` keymap I think), but we should also support reviving agents
  from this new "Agents" sub-tab (since it should, ideally, be much easier to query
  from). We might deprecate the custom agent revival panel in favor of the "Agents"
  sub-tab at some point, but I'm not sure yet.
- We should keep the 2nd (artifact link improvements / fixes) and 3rd (TUI integration)
  steps in mind while implementing the new "Agents" sub-tab but they will initially be
  out of scope.
- Review the agent_catalog_pane.md file in the research sidecar repo for context and
  inspiration before planning. Some notes related to this research are listed below:
  - Implement the `sase agent search` command in v1.
  - You MAY use a feature flag if necessary (i.e. to prevent the user from seeing parts
    of an unfinished product) but it MUST be removed before this epic lands.
- #beau

#plan #m_opus