- **AGENTS:**
  - [bbugyi200.athena.1eq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eq.md)
- **ARTIFACTS:**
  - [housekeeping_retention_scan_speedup.md](https://github.com/sase-org/sase--plans/blob/020afe580993f45297ce9024f0822bdd93469244/202611/housekeeping_retention_scan_speedup.md)

%model:@medium #gh:gh_sase-org__sase
[@plan:202611/housekeeping_retention_scan_speedup.md][1]

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false Reviewer decisions for this plan (final · reviewer via ACE):

- recent_window_short_circuit = skip (planner default: skip). Implement the
  "recent_window_short_circuit = skip" branch; ignore "recent_window_short_circuit =
  keep". Context: "Should artifact_run_prune skip per-run scans for keep-recent-window
  runs, which can never be selected?". Implement only the branches selected above.
  %macros_enabled:true

[1]:
  https://github.com/sase-org/sase--plans/blob/020afe580993f45297ce9024f0822bdd93469244/202611/housekeeping_retention_scan_speedup.md
