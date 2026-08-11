- **AGENTS:**
  - [bbugyi200.athena.toobig-2e.split_file.tests._global_state_leak_detector.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-2e.split_file.tests._global_state_leak_detector.0/README.md)

#gh:sase-org/sase %id(split_file.tests._global_state_leak_detector.0, clan=toobig-2e)
%wait:toobig-2e.split_file.src.sase.axe.run_agent_exec_plan_accept.0 %wait(runners=3)
%auto %wait(priority=20) #split_file:tests/_global_state_leak_detector.py
