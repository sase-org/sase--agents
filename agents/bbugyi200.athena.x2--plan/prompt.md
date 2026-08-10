#gh:gh_sase-org__sase We don't currently seem to respect the `%wait` directive's `runners` kwarg when
displaying the queued sase agents in the agent metadata panel's `QUEUE` section. All
sase agents with a lower configured number of max `runners` (i.e. the maximum number of
agents allowed to be running before that agent is allowed to launch) should be queued
after agents with a higher `runners` configuration (the default is 10 if agent's don't
use the `%wait` directive's `runners` kwarg). See ~/tmp/screenshots/20260810_093341.png
for an example of the issue I'm describing. Can you help me fix this?

#plan #m_opus