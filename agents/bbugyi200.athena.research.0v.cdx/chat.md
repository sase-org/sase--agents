# Chat History - ace-run (research.0v.cdx)

- **TIMESTAMP:** 2026-08-21 19:59:15 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0v.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260821_193052.md`

## Prompt

%clan(research.0v, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I recently implemented pluggable sase finalizers (see the sase-rn and sase-rr epic beads for context). I would like to improve sase's finalizers by fixing any existing bugs and making some improvements to make them more powerful if possible. Can you do some research to help me find any existing bugs and (if possible) make sase's finalizers more powerful? End your analysis with a ranked list of recomended bug fixes / improvements.]]) %id:research.0v.cdx
%model:@research_a 
#gh:gh_sase-org__sase I recently implemented pluggable sase finalizers (see the sase-rn and sase-rr epic beads for context). I would like to improve sase's finalizers by fixing any existing bugs and making some improvements to make them more powerful if possible. Can you do some research to help me find any existing bugs and (if possible) make sase's finalizers more powerful? End your analysis with a ranked list of recomended bug fixes / improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the two epic beads into the finalizer implementation and tests, then probe the behavior with focused experiments and compare it against the intended workflow. I’m using the SASE memory-read procedure because bead/artifact rules apply here, and I’ll use the required final-declaration skill only after the report is complete and verified.

The governing notes confirm that the report should be treated as a durable artifact and that the bead context must be read through SASE’s recorded interfaces. I’m now mapping the epics’ promises to the actual CLI, hook, manifest, and test paths; after that I’ll reproduce candidate failure modes rather than ranking code-smell alone.

The current landed tree already contains fixes for the two most visible rollout regressions (external payload delivery/validation and fakey turn identity), so I won’t duplicate those as recommendations. The next pass is a fresh audit of the contract boundary—including the shared Rust core—plus fault-injection around isolation, retries, fixed-point behavior, and declaration freshness. I’m using the repository-opening skill because that shared core is a separate repository under SASE’s rules.

Two concrete protocol gaps are now emerging from the audit: external `max_attempts` is never applied, and execution reloads live configuration without checking the plan’s sealed config/provider digest. I’m also testing an outcome inconsistency where a plugin can return `skipped`, cause the run to fail, yet leave `finalizer_result.json` labeled successful. These are distinct from the rollout issues already fixed in `sase-rr`.

The code and public docs disagree on a core policy: the docs promise `max_attempts` bounds commit execution, but only `builtin@command` reads that field. External plugins run once, while commit can rerun across controller cycles without an instance-level cap. I’m treating that as one systemic attempt-policy defect, not three separate wishlist items. Installation is still rebuilding the local Rust binding; the audit itself is continuing while that finishes.

The linked Rust core used by this workspace exactly matches the checkout I audited. A separate safety gap also looks real: the supposedly sealed plan is trusted from a writable JSON artifact, and controller loading silently accepts/skips malformed entries without validating the plan digest or matching each entry’s provider/config digest against live configuration. I’ll distinguish the integrity risk (host-owned boundary) from the ordinary config-drift bug in the final ranking.

The focused finalizer suite is green (59 tests), which is useful: the defects are gaps in coverage, not failures already caught by the existing matrix. Four independent probes reproduced the attempt-policy miss, `skipped → aggregate success`, model-controlled repository ordering, and acceptance of an invalid empty plan digest as controller success. I’m opening the research sidecar now so the report follows its local conventions.

The core audit is complete: all 59 focused finalizer tests pass, but targeted probes exposed several protocol gaps beyond the existing suite. I’m now tightening the evidence and writing the ranked report into the research repository.

Two additional probes confirmed less-visible extension failures: provider distribution names are not normalized consistently, and controller re-runs preserve attempt numbers but discard earlier evidence and diagnostics. I’m folding these into a new post-retirement audit rather than overwriting the existing finalizer research.

The report is drafted and ends with a 14-item ranking. Its top recommendation is a new critical finding: authenticate the resolved plan outside the writable artifact it is supposed to validate. I’m registering the report as a durable research artifact now, then I’ll run the final repository checks and declaration.

The report and repository checks are clean apart from the intended new research file. Per the requested `/sase_final` skill, I’m now inspecting the host-issued obligations and submitting the atomic final declaration; after it succeeds I will make no further changes.

Research completed and saved to [finalizer_protocol_integrity_audit.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202608/finalizer_protocol_integrity_audit.md).

Key findings:

- Critical: writable `finalizer_plan.json` can bypass every finalizer while recording success.
- Retry limits are inconsistently enforced.
- `skipped` can produce contradictory controller and aggregate statuses.
- Plugin naming, output limits, evidence retention, and repository ordering contain confirmed bugs.
- The highest-leverage improvement is a sealed provider-description handshake enabling typed, optional, and mutation-aware finalizers.

All 59 focused finalizer tests passed; additional adversarial probes exposed the uncovered issues. The report ends with 14 ranked fixes and improvements and is attached to `sase-rr`. The final declaration was accepted.
