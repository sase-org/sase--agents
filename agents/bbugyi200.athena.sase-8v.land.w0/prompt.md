#gh:gh_sase-org__sase %w:sase-8v.land Can you help me add a new "Chats" sub-tab to the
"Artifacts" tab in the TUI?

- This tab should show all sase chats. These chats are stored locally in the
  ~/.sase/chats/ directory, but we should include remote chats from other
  machines as well since they should be synced in so the corresponding chat
  files should be available somewhere (I'm not sure where).
- Add an option to revive an agent from this panel, which should jump to the
  agents tab and then trigger the same agent revival that would have occurred if
  the user revived the agent using the `R` keymap on the agents tab.
- Make sure it is very clear visually which chats are available only locally,
  which are originally sourced from this machine but are also available in an
  agents sidecar repo, and which were originally sourced from a remote machine
  and were pulled in to this machine's sase agent data when syncing the agents
  sidecar repo.
- #beau

#plan #m_opus