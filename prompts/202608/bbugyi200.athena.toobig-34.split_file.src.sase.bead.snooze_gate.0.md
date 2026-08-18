- **AGENTS:**
  - [bbugyi200.athena.toobig-34.split_file.src.sase.bead.snooze_gate.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-34.split_file.src.sase.bead.snooze_gate.0/README.md)

#gh:sase-org/sase %id(split_file.src.sase.bead.snooze_gate.0, clan=toobig-34)
%wait:toobig-34.split_file.src.sase.agent.restart.0 %wait(runners=3) %auto
%wait(priority=20) #split_file:src/sase/bead/snooze_gate.py
