#gh:gh_sase-org__sase I receive way too many task bead notifications. Can you help me add a new sase
config field that allows the user to configure the minimum number of +1s a task bead
requires before it is eligible for a bead task sase gate?

- Let's make this config field have a default value of 1 (i.e. task beads don't get a
  sase gate until they have at least one +1).
- Dismiss all of my current sase notifications that correspond with task bead gates
  where the task does not meet this requirement (i.e. does not have any +1s).
- We will also need to handle stale/old task beads at some point periodically if we do
  this. Otherwise task beads will just build up forever.
  - To support this we will add two new sase config fields (group all of the config
    fields added for this feature together somehow) to configure the number of days, say
    `<D>`, at which point a task bead is considered stale (i.e. eligible for cleanup)
    and the number of stale beads, say `<B>`, required before we send a task cleanup
    sase gate.
  - We should then add a chop that only acts when there are `<B>` beads that have not
    crossed the +1 threshold and were created `<D>` or more days ago.
  - If these requirements are met, the chop will send a custom sase gate with a single
    option to close the selected stale beads (each bead should be able to be
    selected/unselected by the user in this gate).
  - These two new config fields should have default values: `<D>` should default to 7
    and `<B>` should default to 10.

#plan