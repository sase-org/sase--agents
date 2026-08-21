#gh:gh_sase-org__sase Can you help me drastically simplify the `ci_watch` chop by removing all
functionality for launching agents and removing the custom sase gate that we use to get
launch approval from users?

- I want this shop to only be responsible for merging the release-please PR (when the
  appropriate GitHub Actions workflows/jobs are green).
- We should send an excellent sase notification either way (for each release PR that is
  submitted and/or each GitHub repo that has failing jobs--give excellent details about
  those failing jobs in this notification).
- As a part of this change, let's remove the `inhibit_if` config for this chop, which is
  configured in my chezmoi repo.
- After we make this change, the `ci_watch` chop should submit the PR (since all jobs
  are/were green I think).
- Verify this is the case by having the agent that implements your plan use a
  /sase_monitor to wait the appropriate amount of time and then having a new agent (that
  uses the codex/gpt-5.6-sol model--if this is possible with sase monitors) verify that
  the PR is submitted. If not, that new agent should use its /sase_plan skill to design
  the required fix.
- #beau

#plan