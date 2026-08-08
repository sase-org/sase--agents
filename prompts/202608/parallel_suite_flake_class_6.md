- **PLAN:**
  [202608/parallel_suite_flake_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-h8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.8/README.md)

#gh:gh_sase-org__sase %id(8, clan=sase-h8, bead=sase-h8.8) %model:@medium_phase_worker
%auto %w:sase-h8.4,sase-h8.5,sase-h8.6,sase-h8.7 %w(bead=sase-h8.4) %w(bead=sase-h8.5)
%w(bead=sase-h8.6) %w(bead=sase-h8.7) #bd/work_phase_bead:sase-h8.8
