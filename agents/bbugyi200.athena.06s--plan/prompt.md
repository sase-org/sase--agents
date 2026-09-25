#gh:gh_sase-org__sase There seem to be a large number of sase workspaces that are claimed even though
we only have 9 agents running ATM (you will be the 10th). See the command output below
for context. Can you help me figure out why these were left claimed, fix the underlying
issues, release the workspaces, and then delete any ephemeral workspaces that are not
currently claimed (in the ~/.local/state/sase/workspaces/sase-org/sase/ directory)? #plan %m:@xlarge
```
❯ sase workspace list
Project: sase  policy=xdg-state
Root: /home/bryan/.local/state/sase/workspaces/sase-org/sase

   #  CLAIMED BY               ROLE    EXISTS  PIN LAST USED  STALE PATH
   0  -                        primary yes     yes 51d ago    -     /home/bryan/projects/github/sase-org/sase
  10  ace(run)-260815_193021   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
  11  ace(run)-260815_194706   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
  12  ace(run)-260907_181127   claim   yes     -   4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
  13  ace(run)-260822_142305   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
  14  ace(run)-260822_132646   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
  15  ace(run)-260828_015614   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15
  16  ace(run)-260822_173908   claim   yes     yes 15d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
  17  ace(run)-260823_154709   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17
  18  ace(run)-260819_172701   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
  19  ace(run)-260907_093335   claim   yes     yes 6h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
  20  ace(run)-260906_155539   claim   yes     yes 7h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20
  21  ace(run)-260819_161506   claim   yes     yes 18d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21
  22  ace(run)-260824_191559   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
  23  ace-gate                 claim   yes     -   42m ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
  24  ace(run)-260907_025606   claim   yes     yes 4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24
  25  ace(run)-260825_115340   claim   yes     yes 10d ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
  26  ace(run)-260907_141831   claim   yes     yes 4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_26
  27  ace(run)-260907_033130   claim   yes     yes 4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27
  28  ace(run)-260907_033113   claim   yes     yes 4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28
  29  ace(run)-260907_130308   claim   yes     -   24m ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29
  30  ace(run)-260907_172341   claim   yes     -   4m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30
  31  ace-monitor              claim   yes     -   5m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31
  32  ace(run)-260907_170541   claim   yes     yes 5m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32
  33  ace(run)-260907_011604   claim   yes     yes 8h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33
  34  ace(run)-260907_151610   claim   yes     yes now        -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34
  35  ace(run)-260907_172922   claim   yes     -   5m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_35
  36  ace(run)-260907_173600   claim   yes     -   49m ago    -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36
  37  ace(run)-260907_170840   claim   yes     -   6m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37
  38  ace-monitor              claim   yes     -   5m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38
  39  -                        claim   yes     -   1m ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39
  40  -                        claim   yes     -   2h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40
  41  -                        claim   yes     -   2h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41
  42  -                        claim   yes     -   2h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42
  43  -                        claim   yes     -   2h ago     -     /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_43
```