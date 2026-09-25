#gh:sase-org/sase
%id(split_file.src.sase.finalizers.controller.0, clan=toobig-3h)
%wait:toobig-3h.split_file.src.sase.finalizers.commit.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/finalizers/controller.py