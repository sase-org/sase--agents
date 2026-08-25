- **PLAN:**
  [202608/artifacts_agents_pane.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_agents_pane.md)
- **AGENTS:**
  - [bbugyi200.athena.0da--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0da.md)

I was working on improving artifact links when it was brought to my attention (see the
artifact_link_derivation.md file in the research sidecar repo for context) that the
"Agents" sub-tab of the "Artifacts" tab is a major missing piece that prevents us from
fully benefiting from artifact links.

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
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
