#gh:gh_sase-org__sase I would like to add a `for_epic=<true|false>` keyword input to the `%wait`
directive. Can you help me implement this?

- This input would default to `true` when a sase agent name is provided as an argument
  alongside it (we should throw an error and/or show diagnostic warnings if a user
  attempts to use this input without an agent name) and will trigger a new behavior.
- Namely, when `for_epic=true`, the sase agent that is launched from that prompt should
  wait for the agent specified by the `%wait` directive AND should also wait for any
  epic bead that this agent may or may not create.
- In order to make this work reliably, we will probably need to make sure that
  artifact/bead links are established consistently from the sase agent that creates an
  epic bead to that epic bead. I think we already have the infrastructure set up for
  this.
- We will also want to make it very clear to the user in the TUI somehow when an agent
  has stopped waiting for the agent it specified via the `%wait` directive and is now
  waiting for the epic bead that agent created instead.
- The goal of this feature is to allow users to launch sase agents earlier than they can
  now in some cases. Sometimes, for example, I need to wait for an agent to create an
  epic before I can launch a prompt (so I can pass that epic bead ID to the `%wait`
  directive's `bead` input). This feature makes it so I do not need to do that anymore.
- Review the wait_follows_agent_into_epic.md file in sidecar repo for context and inspiration before
  planning. I agree with all of the recommendations made in that research file.
- #beau

#plan %m:@xlarge %auto %w:research.3v.linker