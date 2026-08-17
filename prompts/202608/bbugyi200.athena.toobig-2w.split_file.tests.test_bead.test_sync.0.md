- **AGENTS:**
  - [bbugyi200.athena.toobig-2w.split_file.tests.test_bead.test_sync.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-2w.split_file.tests.test_bead.test_sync.0/README.md)

#gh:sase-org/sase %id(split_file.tests.test_bead.test_sync.0, clan=toobig-2w)
%wait:toobig-2w.split_file.tests.monitor.test_monitor_store_reconcile.0 %wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_bead/test_sync.py
