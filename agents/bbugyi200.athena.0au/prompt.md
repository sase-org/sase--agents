#gh:gh_sase-org__sase We recently added support for showing the status of dependencies for waiting
agent nodes in the agents tab (find the relevant plan files). Can you now help me start
grouping the bead and agent indicators together?

- Remove the separator that currently separates the bead indicators from the agent
  indicators.
- Also, let's start grouping the bead indicators with the corresponding agent indicator,
  if any.
- For example, assume an agent is waiting on one running agent, one done agent, one
  in-progress bead, and one closed bead. Then the agent node for that agent should show
  its running agent indicator next to the in-progress bead indicator (the counts for
  each should still be next to the corresponding icon/indicator) and the done agent
  indicator should be next to the closed bead indicator.

#plan