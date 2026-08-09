#gh:sase-org/sase
%id(split_file.src.sase.dev_update.prebuild.0, clan=toobig-27)
%wait:toobig-27.split_file.src.sase.dev_update.execute.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/dev_update/prebuild.py