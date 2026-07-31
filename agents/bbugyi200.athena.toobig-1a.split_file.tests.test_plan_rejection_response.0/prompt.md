#gh:sase-org/sase
%id(split_file.tests.test_plan_rejection_response.0, clan=toobig-1a)
%wait:toobig-1a.split_file.tests.test_plan_command_handler.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_plan_rejection_response.py