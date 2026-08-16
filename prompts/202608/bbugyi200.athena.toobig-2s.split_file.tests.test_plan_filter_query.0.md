- **AGENTS:**
  - [bbugyi200.athena.toobig-2s.split_file.tests.test_plan_filter_query.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-2s.split_file.tests.test_plan_filter_query.0/README.md)

#gh:sase-org/sase %id(split_file.tests.test_plan_filter_query.0, clan=toobig-2s)
%wait:toobig-2s.split_file.src.sase.llm_provider.registry.0 %wait(runners=3) %auto
%wait(priority=20) #split_file:tests/test_plan_filter_query.py
