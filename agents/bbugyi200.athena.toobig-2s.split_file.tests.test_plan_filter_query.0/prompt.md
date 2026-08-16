#gh:sase-org/sase
%id(split_file.tests.test_plan_filter_query.0, clan=toobig-2s)
%wait:toobig-2s.split_file.src.sase.llm_provider.registry.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_plan_filter_query.py