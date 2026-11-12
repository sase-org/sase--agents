#gh:gh_sase-org__sase I'm unable to re-launch the failed agents for two epics (see the command output
below for context). Can you help me fix this by making the `sase bead work` command much
more resiliant to this type of error in the future (we should be able to auto-recover
from this type of issue)? Once that is done, you should re-launch the failed agents for
the two referenced epics.

#plan %m:claude-fable-5

```
❯ sase bead work sase-1sd bob-cli-kq -Y
Epic sase-1sd is already ready; retrying remaining non-closed phases.
Epic sase-1sd — Next seven: salvage the display-name fix, then unstrand the fleet (sase-zo, sase-1s2, sase-1re, sase-1o1, sase-1qm, sase-1qi, sase-1db): 7 phase agent(s) in 7 wave(s) plus 1 land agent (sase-1sd.land).
  Clan: sase-1sd · Tribe: @epic
  Wave 0: sase-1sd.1 → sase-1sd.1
  Wave 1: sase-1sd.2 → sase-1sd.2
  Wave 2: sase-1sd.3 → sase-1sd.3
  Wave 3: sase-1sd.4 → sase-1sd.4
  Wave 4: sase-1sd.5 → sase-1sd.5
  Wave 5: sase-1sd.6 → sase-1sd.6
  Wave 6: sase-1sd.7 → sase-1sd.7
  Land waits on: sase-1sd.1, sase-1sd.2, sase-1sd.3, sase-1sd.4, sase-1sd.5, sase-1sd.6, sase-1sd.7
slow_launch_stage operation=bead_work stage=owner_discovery elapsed_ms=50082.7 target=sase-1sd
slow_launch_stage operation=bead_work stage=registry_rebuild_reason elapsed_ms=66130.3 target=sase-1sd
slow_launch_stage operation=bead_work stage=registry_read elapsed_ms=70008.5 target=sase-1sd
slow_launch_stage operation=bead_work stage=initial_selection elapsed_ms=128926.1 target=sase-1sd

Existing agents for epic sase-1sd:
  BLOCKED  (blocked) sase-1sd.3 bead=sase-1sd.3  agent owner 'sase-1sd.3' is not associated with expected bead sase-1sd.3; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052956 via registry owner sase-1sd.3
  BLOCKED  (blocked) sase-1sd.4 bead=sase-1sd.4  agent owner 'sase-1sd.4' is not associated with expected bead sase-1sd.4; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052957 via registry owner sase-1sd.4
  BLOCKED  (blocked) sase-1sd.5 bead=sase-1sd.5  agent owner 'sase-1sd.5' is not associated with expected bead sase-1sd.5; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052958 via registry owner sase-1sd.5
  BLOCKED  (blocked) sase-1sd.6 bead=sase-1sd.6  agent owner 'sase-1sd.6' is not associated with expected bead sase-1sd.6; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052959 via registry owner sase-1sd.6
  BLOCKED  (blocked) sase-1sd.7 bead=sase-1sd.7  agent owner 'sase-1sd.7' is not associated with expected bead sase-1sd.7; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112053000 via registry owner sase-1sd.7
  BLOCKED  (blocked) sase-1sd.land bead=sase-1sd  agent owner 'sase-1sd.land' is not associated with expected bead sase-1sd; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112053001 via registry owner sase-1sd.land
  PRESERVE (RUNNING) sase-1sd.1 bead=sase-1sd.1  for bead sase-1sd.1 at /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052954
  KILL     (WAITING) sase-1sd.2 bead=sase-1sd.2  for bead sase-1sd.2 at /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052955
Error: agent owner 'sase-1sd.3' is not associated with expected bead sase-1sd.3; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052956 via registry owner sase-1sd.3
agent owner 'sase-1sd.4' is not associated with expected bead sase-1sd.4; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052957 via registry owner sase-1sd.4
agent owner 'sase-1sd.5' is not associated with expected bead sase-1sd.5; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052958 via registry owner sase-1sd.5
agent owner 'sase-1sd.6' is not associated with expected bead sase-1sd.6; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112052959 via registry owner sase-1sd.6
agent owner 'sase-1sd.7' is not associated with expected bead sase-1sd.7; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112053000 via registry owner sase-1sd.7
agent owner 'sase-1sd.land' is not associated with expected bead sase-1sd; observed bead association(s): none; artifact /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/12/20261112053001 via registry owner sase-1sd.land
Rerun with --dry-run to review the full cleanup preview. Dismiss the listed agent(s) in sase tui before retrying.
```