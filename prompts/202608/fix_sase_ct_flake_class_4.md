- **PLAN:**
  [202608/fix_sase_ct_flake_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-j7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j7.5/README.md)

#gh:gh_sase-org__sase %id(5, clan=sase-j7, bead=sase-j7.5) %model:@medium_worker %auto
%w:sase-j7.1,sase-j7.2,sase-j7.3,sase-j7.4 %w(bead=sase-j7.1) %w(bead=sase-j7.2)
%w(bead=sase-j7.3) %w(bead=sase-j7.4) #bd/work_phase_bead:sase-j7.5
