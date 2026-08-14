#gh:sase-org/sase
%id(split_file.tests.ace.tui.test_memory_reads_loader.0, clan=toobig-2m)
%wait:toobig-2m.split_file.src.sase.monitor.start.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/ace/tui/test_memory_reads_loader.py