#gh:sase-org/sase
%id(split_file.src.sase.xprompt.workflow_loader.0, clan=toobig-23)
%wait:toobig-23.split_file.src.sase.artifact_ref_prompt.0
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/xprompt/workflow_loader.py