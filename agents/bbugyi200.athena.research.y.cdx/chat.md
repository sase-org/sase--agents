# Chat History - ace-run (research.y.cdx)

- **TIMESTAMP:** 2026-08-05 18:21:16 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.y.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260805_173621.md`

## Prompt

%clan(research.y, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] This project's test suite is getting to be very large and very slow, especially when parallel agents are run. Can you do some research with the goal of helping me mitigate this problem somehow? Don't be afraid to explore/recommend large architectural changes if that's genuinely the right approach, like splitting up the repo for example. End your analysis with a recommended solution.]]) %id:research.y.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase This project's test suite is getting to be very large and very slow, especially when parallel agents are run. Can you do some research with the goal of helping me mitigate this problem somehow? Don't be afraid to explore/recommend large architectural changes if that's genuinely the right approach, like splitting up the repo for example. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll combine a local test-suite audit with current evidence on large-suite scaling, then write a decision-oriented report with a concrete recommendation. Because the requested destination is the configured research sidecar, I’m using the `sase_repo` workflow to resolve that repository before touching it.

The initial inventory confirms this is no longer a conventional Python suite: roughly 23,000 test functions across about 1,000 Python files, with 157 MB under `tests/`. I’m now separating collection cost, execution cost, visual/golden assets, and resource contention so the recommendation targets the actual bottlenecks rather than only suggesting more workers.

One important finding already: the project has implemented a host-wide xdist token pool, so the obvious “cap parallelism” mitigation is present. That helps prevent overload, but it also means agents can spend substantial time waiting for a minimum four-worker grant; the suite still performs full collection in every workspace and the CI matrix repeats almost the entire nonvisual suite three times. I’m quantifying those duplicated costs next.

A cached serial collection still takes about 15 seconds internally (about 20 seconds wall) and expands to 25,915 tests, of which 25,500 are in the default nonvisual/non-slow selection. Since xdist makes every worker collect the same suite, a 28-worker run asks Python to construct roughly 725,000 test items before useful parallel execution begins. That points strongly toward reducing the selected test universe per invocation, not increasing the worker ceiling.

The controlled four-worker benchmark is running at roughly 10% per minute, so the contention-floor experience is likely around ten minutes even before waiting for tokens. I’m letting it finish because its slow-test distribution will show whether a few integration tests dominate or whether the problem is broad suite volume; those require different remedies.

The run is confirming a volume problem rather than an early handful of pathological cases: progress is steady but only about 8–10 percentage points per minute. The source layout also matters: ACE/TUI accounts for about 8,166 tests, while over 15,000 tests remain outside ACE, bead, and CLI directories—so extracting only the TUI would reduce load but would not solve the core scaling issue.

The benchmark has surfaced two failures around 38%; I’ll preserve their details in the report and distinguish baseline/infrastructure failures from timing data. If they expose an independent project defect rather than contention behavior, I’ll follow the project’s task-triage rules instead of silently discarding them.

At the halfway point, failures are sparse and progress remains broadly linear. That reinforces the working diagnosis: the dominant cost is thousands of ordinary tests plus per-worker collection/import/setup, not a small tail that can be fixed by optimizing ten slow cases. The final durations will still identify useful secondary cleanup targets.

The four-worker run is now past 80% at about eleven minutes. That provides a realistic lower-bound agent experience under contention: add up to 45 minutes of gate waiting in the current configuration, then roughly this execution time. The mitigation should therefore make ordinary agent checks scoped and cheap, while reserving exhaustive validation for a deduplicated owner/CI path.

The measured run finished in 14:09 wall time with four workers: 25,487 passed, seven failed, seven skipped. The slow tail matters but is secondary—three unmarked tests alone consumed about 149 seconds of worker time, yet the overall run used roughly 1,590 CPU-seconds, so removing those would not transform the experience. I’m now validating the architectural options against their official documentation and the project’s coupling profile.

The benchmark failures also reveal a migration constraint: parts of this suite depend on live xprompt configuration, shared temp-directory behavior, and timing-sensitive multiprocess locks. I’m invoking the project’s `sase_new_task` triage workflow now because the instructions require independently discovered baseline failures to be checked for duplicates and recorded if genuinely new; this won’t broaden the requested implementation work.

The task-triage skill requires an audited read of the long-term bead policy, so I’m using the `sase_memory_read` workflow for that policy before checking duplicates.

The “slow tail” is not merely an xdist artifact: a focused serial rerun of the three dismissed-bundle tests is still taking over a minute. These tests are currently in the default fast lane despite names and behavior that make them performance/soak tests, so lane taxonomy is an immediate, low-risk win.

The evidence now points to a two-speed verification architecture: cheap dependency-aware checks in phase-agent workspaces, and exhaustive validation once at integration boundaries. I’m writing the report with Pants as the strategic caching/orchestration candidate, testmon as a low-cost bridge, and repo splitting explicitly evaluated—but deferred until the existing ACE dependency inversion is removed.

The report is drafted. It concludes that repo splitting is premature, recommends a testmon bridge plus a bounded Pants pilot, and gives staged thresholds for making affected selection authoritative. Because the report now materially supports the benchmark findings and task-triage evidence, I’m using the `sase_artifact_file` workflow to register it as a durable artifact before attaching duplicate evidence.

Task triage found the bead-mutation timeout and full-xdist isolation failures are already covered, so I attached fresh evidence instead of duplicating them. The one genuinely new deterministic issue is the ambient `research_swarm` leak into xprompt tests; its task creation is currently waiting in the project’s synchronous sidecar publication path, so I’m letting that bounded operation resolve before final verification.

Research written to [test_suite_scaling_strategy.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/test_suite_scaling_strategy.md).

Recommended direction:

- Introduce affected-test checks for phase agents and reserve exhaustive checks for land agents/CI.
- Create genuine unit, integration, system, visual, and performance lanes.
- Replace greedy worker allocation with fair job classes.
- Pilot testmon immediately and Pants for dependency-aware execution and shared caching.
- Defer repository splitting until ACE’s dependencies are untangled.

Key measurement: 25,500 nonvisual tests took 14:09 with four workers. Additionally, [xdist performs full collection in every worker](https://pytest-xdist.readthedocs.io/en/stable/how-it-works.html), multiplying collection overhead.

The report is formatted, validated, and registered as durable artifact `file:explicit:93f0fff0d91c393a140e217d`. Baseline failures were attached to existing tasks `sase-e2` and `sase-ct`; new ready tasks `sase-ff` and `sase-fg` cover ambient xprompt leakage and the 88-second dismissed-bundle test setup.

The research file is mine, so I’m applying the required `sase_git_commit` finalizer workflow to commit that single file in the research sidecar, then I’ll verify the sidecar is clean.

The diff contains only the new research report. I’m committing it as a documentation change with a file-scoped commit, so no unrelated sidecar content can be staged.

Committed the research report:

- File: [test_suite_scaling_strategy.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/test_suite_scaling_strategy.md)
- Commit: `291ca53 docs: research test suite scaling strategy`
- Research sidecar is clean and synchronized with `origin/main`.
