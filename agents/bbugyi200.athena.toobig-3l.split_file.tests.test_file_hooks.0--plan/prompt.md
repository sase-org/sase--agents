#gh:sase-org/sase
%id(split_file.tests.test_file_hooks.0, clan=toobig-3l)
%model:@medium
%wait:toobig-3l.split_file.tests.test_file_hook_engine.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_file_hooks.py