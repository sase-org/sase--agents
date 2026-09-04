- **AGENTS:**
  - [bbugyi200.kellys_mbp.research.7.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.research.7.cld/README.md)

%id(cld, clan=research.7) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've
been thinking a lot about how sase should support collaboration by allowing multiple
different users on multiple different machines (multiple users on the same machine
should also be supported) to work on the same codebase at the same time using a PR
workflow.

- We already have some support for syncing multiple machines from the same user but I'm
  worried the support that we do have is very expensive and not very useful.
- In particular, the way we sync all sase agents from all enabled projects to local disk
  currently does not seem to add much value, but when I designed this I was optimistic
  that the functionality would be useful for collaboration.
- I also have plans to soon allow a single TUI to manage all of a user's sase agents
  across all supported machines (see the tailnet_agent_fleet.md file in the research
  sidecar repo for context--note that this research direction is not yet approved, but
  I'm thinking about moving forward with this soon).

Can you do some research with the goal of designing the best architecture to support
collaboration with sase? You should also critique our current agent syncing solution and
recommend whether we should keep it/change it/remove it. Think hard about what
collaboration means (or should mean) when using sase to develop a project. End your
analysis with a recommended solution. #research
