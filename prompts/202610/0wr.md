- **AGENTS:**
  - [bbugyi200.athena.0wr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0wr/README.md)

#gh:gh_sase-org__sase I would like to migrate all existing agent instruction files to
use sase's memory files dynamically to contruct instructions for each sase agent right
before launching that agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md
  file in the research sidecar repo for context before performing your own research. I
  agree with all of the recommendations made in that research file I think (see next
  bullet).
- It is still not clear to me exactly how each provider gets the same (or better/fixed)
  instructions that it does today once we've implemented the recommendations from this
  prior research.

Can you create a concise report of your own with visual illustrations to makes this
clearer? Also, how will we track what memory was pre-loaded / injected for each sase
agent and how will users see this in the TUI? Think hard about what the best UX for this
functionality would be. #research %m:@xlarge
