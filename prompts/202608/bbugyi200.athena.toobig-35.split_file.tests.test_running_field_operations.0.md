- **AGENTS:**
  - [bbugyi200.athena.toobig-35.split_file.tests.test_running_field_operations.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-35.split_file.tests.test_running_field_operations.0/README.md)

#gh:sase-org/sase %id(split_file.tests.test_running_field_operations.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.test_run_agent_runner_lifecycle.0 %wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_running_field_operations.py
