#gh:sase-org/sase
%id(split_file.tests.test_commit_workflow_checkpointing.0, clan=toobig-0t)
%wait:toobig-0t.split_file.tests.agents_sync.test_git_sync.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_commit_workflow_checkpointing.py