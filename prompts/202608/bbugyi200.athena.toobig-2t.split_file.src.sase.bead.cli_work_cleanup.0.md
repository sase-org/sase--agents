- **AGENTS:**
  - [bbugyi200.athena.toobig-2t.split_file.src.sase.bead.cli_work_cleanup.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-2t.split_file.src.sase.bead.cli_work_cleanup.0/README.md)

#gh:sase-org/sase %id(split_file.src.sase.bead.cli_work_cleanup.0, clan=toobig-2t)
%wait:toobig-2t.split_file.src.sase.bead._stream_integrity.0 %wait(runners=3) %auto
%wait(priority=20) #split_file:src/sase/bead/cli_work_cleanup.py
