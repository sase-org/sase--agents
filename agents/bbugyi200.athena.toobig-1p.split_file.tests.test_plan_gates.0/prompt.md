#gh:sase-org/sase
%id(split_file.tests.test_plan_gates.0, clan=toobig-1p)
%wait:toobig-1p.split_file.tests.agents_sync.test_rendering.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_plan_gates.py