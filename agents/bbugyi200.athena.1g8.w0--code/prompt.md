%model:@small
#gh:gh_sase-org__sase @plan:202611/sase_core_macos_canonical_path_ci.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- archive_paths = lexical (planner default: lexical). Implement the "archive_paths = lexical" branch; ignore "archive_paths = canonical". Context: "Should named dismissed-bundle lookups report the bundle path under the caller's root instead of its canonical form?".
- ci_no_fail_fast = ci (planner default: ci). Implement the "ci_no_fail_fast = ci" branch; ignore "ci_no_fail_fast = none". Context: "Should the CI test step run with --no-fail-fast so one failing test binary cannot hide failures in later binaries?".
- agents_md_repro = add (planner default: add). Implement the "agents_md_repro = add" branch; ignore "agents_md_repro = skip". Context: "Should sase-core's AGENTS.md macOS bullet gain a Linux repro recipe that uses a symlinked TMPDIR?".
Implement only the branches selected above.
%macros_enabled:true
