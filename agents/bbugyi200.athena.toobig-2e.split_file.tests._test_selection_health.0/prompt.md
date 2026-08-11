#gh:sase-org/sase
%id(split_file.tests._test_selection_health.0, clan=toobig-2e)
%wait:toobig-2e.split_file.tests._global_state_leak_detector.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/_test_selection_health.py