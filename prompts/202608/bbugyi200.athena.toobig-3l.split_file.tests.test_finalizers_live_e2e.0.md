- **AGENTS:**
  - [bbugyi200.athena.toobig-3l.split_file.tests.test_finalizers_live_e2e.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-3l.split_file.tests.test_finalizers_live_e2e.0/README.md)

#gh:sase-org/sase %id(split_file.tests.test_finalizers_live_e2e.0, clan=toobig-3l)
%model:@medium %wait:toobig-3l.split_file.tests.test_finalizers_commit_reconciliation.0
%wait(runners=3) %auto %wait(priority=20) #split_file:tests/test_finalizers_live_e2e.py
