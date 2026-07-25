#gh:gh_sase-org__sase #fork:dv This fixed the bug, but now that I look at it, it doesn't look
like the agent that caused this bug even completed the feature I assigned it,
right (see #sshot)? Agents/agent families within an agent clan should always be
sorted by status (regardless of what grouping strategy is currently being used
by the agents tab):

1. Failed agents
2. Stopped agents
3. Running agents
4. Waiting agents
5. Completed agents

Can you help me fix this? #plan #m_fable