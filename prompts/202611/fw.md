- **AGENTS:**
  - [bbugyi200.apollo.fw](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.fw.md)
- **ARTIFACTS:**
  - [bob_cli_macos_props_release_unblock.md](https://github.com/sase-org/sase--plans/blob/5639e34e24cd8a425f48d922fa1617d7f39cdbf5/202611/bob_cli_macos_props_release_unblock.md)

%model:@small #gh:gh_sase-org__sase
[@plan:202611/bob_cli_macos_props_release_unblock.md][1]

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false Reviewer decisions for this plan (final · reviewer via ACE):

- lock_probe = portable (planner default: portable). Implement the "lock_probe =
  portable" branch; ignore "lock_probe = linux_only". Context: "How should the lock-wait
  tests detect that the child opened vault.lock on macOS?". Implement only the branches
  selected above. %macros_enabled:true

[1]:
  https://github.com/sase-org/sase--plans/blob/5639e34e24cd8a425f48d922fa1617d7f39cdbf5/202611/bob_cli_macos_props_release_unblock.md
