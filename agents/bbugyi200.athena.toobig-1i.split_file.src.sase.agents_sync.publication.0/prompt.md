#gh:sase-org/sase
%id(split_file.src.sase.agents_sync.publication.0, clan=toobig-1i)
%wait:toobig-1i.split_file.src.sase.agent.names._registry_scan.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/agents_sync/publication.py