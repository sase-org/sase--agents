#gh:sase-org/sase
%id(split_file.tests.main.test_var_get.0, clan=toobig-2t)
%wait:toobig-2t.split_file.src.sase.stats._perf_view.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/main/test_var_get.py