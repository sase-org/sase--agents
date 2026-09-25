#gh:gh_sase-org__sase Can you help me continuously monitor the sase agents that are running on this
machine and ensure that each one of them completes its goal / assigned work?

- Create a new sase bead that will be used as a message board for the sequence of agents
  that we will launch. I don't currently have an appropriate sase bead type for this
  (this new bead you create will serve as a proof of concept / evidence of whether or
  not a dedicated message board bead type might be useful) so we will use / abuse a
  memory task bead for this by creating a new one with an excellent initial set of
  fields (e.g. title, description, etc...). The agents we spawn in a sequence should be
  instructed to leave notes on this bead to communicate with each other.
- Leave an initial note on this bead that helps flesh out the details that subsequent
  agents will require so you save them a bit of effort.
- All subsequent agents should use the same model as you (this is the default behavior
  for sase monitors).
- Agents should NOT use the /sase_run skill or ask the user for permission before
  launching agents.
- Finally, run the following steps in a loop until there are no remaining running sase
  agents, waiting sase agents, or failed sase agents that haven't been addressed by
  retries. Use your /sase_monitor skill to continuously wait (using the `sleep` command)
  for 1 hour at a time and then run a successor agent that completes each of the
  following steps in sequence (for the first sase monitor ONLY, you should use
  `sleep 60` instead of `sleep 3600` so we don't need to wait an hour before performing
  the first check-in on this machine's sase agents):
  1. Check all running agents to make sure none of them are stalled. If any of them are
     stalled, fix the underlying issue if necessary/appropriate, commit the fix using
     our /sase_git_commit skill, and then relaunch the agent (the `sase agent restart`
     command should work for this I think) if its work was left uncompleted/uncommitted.
  2. If any new sase agents have failed, investigate why they failed. If there is
     something that needs to be fixed before we can relaunch the agent, then we should
     fix the issue and then commit the fix using our /sase_git_commit skill. We should
     then launch a new sase agent with an identical prompt but should explicitly name
     the agent (using the `%id` directive), so the failed agent's name is used as the
     new agent's hood.
  3. Check if our termination condition is met or not and, if not, run another sase
     monitor as described above.
  4. If the termination condition is met, then leave a concise analysis of what work had
     to be performed to ensure all of the sase agents running on this machine completed
     their work successfully and justification for why you believe the termination
     condition is definitely met. This analysis should be left as a normal agent
     response (i.e. the last agent's reply) and also left as a note on the memory bead.

%m:@xlarge