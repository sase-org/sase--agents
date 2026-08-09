#gh:gh_sase-org__sase We recently changed the guidance given by the /sase_new_task xprompt skill to
instruct agents to use the `sase bead search` command to find related/duplicate task
beads. Can you help me make sure this skill also instructs agents to review every sase
task bead (using the `sase bead list` command--I think this command supports filtering
by create date; if not, you should add support) that has been created in the last week
before confirming there are no duplicate/related beads? Also, make sure that this skill
explicitly instructs agents to make notes about related beads if some are found that do
not quite qualify as duplicates but that the agent who works the new task bead should be
aware of (we might already do this, but I'm not sure).

#plan #m_opus