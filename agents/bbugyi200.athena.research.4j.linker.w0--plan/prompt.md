#gh:gh_sase-org__sase I've been wondering if we should change the way that agent clans (on the "Agents"
tab) visually represent waves in an epic. Can you help me implement this?

- Namely, we don't. Also, I don't think that the concept of waves is really supported
  for agent clans in general (only epic agent clans).
- I want to fix that by showing the waves that exist in every agent clan (even research
  clans and custom, user-defined clans) in some visually appealing way in the TUI.
- See the ~/tmp/screenshots/20261015_124557.png screenshot for an example of how agent
  clans look today.
- Review the clan_waves_in_agents_tab.md file in the research sidecar repo for context
  and inspiration before planning. I agree with all of the requirements recommended in
  that research file (but keep in mind that you are responsible for planning and
  splitting up this work appropriately).
- #beau

#plan %m:@xlarge %w:research.4j.linker