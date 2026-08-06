#gh:sase-org/sase
%id(split_file.tests.test_done_agent_loader.0, clan=toobig-1o)
%wait:toobig-1o.split_file.tests.test_commit_artifacts.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_done_agent_loader.py