#gh:sase-org/sase
%id(split_file.tests.test_axe_chop_bead_task_triage.0, clan=toobig-1v)
%wait:toobig-1v.split_file.src.sase.bead.task_gate.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/test_axe_chop_bead_task_triage.py