#gh:sase-org/sase
%id(split_file.tests.main.test_artifact_cli_references.0, clan=toobig-15)
%wait:toobig-15.split_file.tests.agents_sync.test_inventory.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/main/test_artifact_cli_references.py