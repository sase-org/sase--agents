#gh:gh_sase-org__sase The `sase bead work` command just failed (see the command output below for context). Can you help me diagnose the root cause of this issue, fix it, and make the `sase bead work` command more resilient to this type of failure in the future? #plan 
```
❯ sase bead work ns.6.6.6 -Y
Epic sase-ns.6.6.6 is already ready; retrying remaining non-closed phases.
Epic sase-ns.6.6.6 — Task backlog top five - clear the two red verification gates and the three reproducible test hazards behind them: 1 phase agent(s) in 1 wave(s) plus 1 land agent (sase-ns.6.6.6.land).
  Clan: sase-ns.6.6.6 · Tribe: @epic
  Wave 0: sase-ns.6.6.6.1 → sase-ns.6.6.6.1
  Land waits on: sase-ns.6.6.6.1
Error: agent owner 'sase-ns.6.6.6.1--1' is not associated with expected bead sase-ns.6.6.6.1; observed bead association(s): none
```