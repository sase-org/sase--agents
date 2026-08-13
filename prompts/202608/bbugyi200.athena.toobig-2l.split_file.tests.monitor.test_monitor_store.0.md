- **AGENTS:**
  - [bbugyi200.athena.toobig-2l.split_file.tests.monitor.test_monitor_store.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-2l.split_file.tests.monitor.test_monitor_store.0/README.md)

#gh:sase-org/sase %id(split_file.tests.monitor.test_monitor_store.0, clan=toobig-2l)
%wait:toobig-2l.split_file.tests.monitor.test_monitor_start.0 %wait(runners=3) %auto
%wait(priority=20) #split_file:tests/monitor/test_monitor_store.py
