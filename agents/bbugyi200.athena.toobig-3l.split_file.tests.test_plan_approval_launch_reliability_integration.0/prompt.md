#gh:sase-org/sase
%id(split_file.tests.test_plan_approval_launch_reliability_integration.0, clan=toobig-3l)
%model:@medium
%wait:toobig-3l.split_file.tests.test_finalizers_protocol_harness.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_plan_approval_launch_reliability_integration.py