#gh:sase-org/sase
%id(split_file.src.sase.finalizers.executor.0, clan=toobig-3g)
%wait:toobig-3g.split_file.src.sase.finalizers.controller.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/finalizers/executor.py