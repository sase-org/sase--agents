- **AGENTS:**
  - [bbugyi200.athena.toobig-33.split_file.tests.test_vcs_xprompt_mru.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-33.split_file.tests.test_vcs_xprompt_mru.0/README.md)

#gh:sase-org/sase %id(split_file.tests.test_vcs_xprompt_mru.0, clan=toobig-33)
%wait:toobig-33.split_file.src.sase.agent.restart.0 %wait(runners=3) %auto
%wait(priority=20) #split_file:tests/test_vcs_xprompt_mru.py
