#gh:sase-org/sase
%id(split_file.tests.test_suite_gate.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.test_running_field_operations.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_suite_gate.py