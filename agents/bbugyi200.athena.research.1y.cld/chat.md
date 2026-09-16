# Chat History - ace-run (research.1y.cld)

- **TIMESTAMP:** 2026-09-14 13:21:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1y.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260914_125611.md`

## Prompt

%id(cld, clan=research.1y) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1y.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I've been thinking a lot about the `sase tool` command (see
the sase-zm epic bead--which I intend to cancel and re-design--for context) lately and
what other use-cases are available now that (well, once the `sase tool` command is
implemented) each sase project's slowest tool calls are wrapped by a `sase` command.
Some examples that I've thought of are listed below.

- I figure we can start surfacing these tool calls and their outputs in the TUI and on
  the command-line (via `sase tool` subcommands).
- We should also be able to attempt to predict the endtime of a running command once we
  have a large enough history of that command being run under different machine loads,
  right?
- Are there any good use-cases that I missed?

Can you do some research with the goal of helping me think of the best use-cases that
this new command would enable? Also, think hard about what the best possible UX would
look like for the new `sase tool` command. End your analysis with a recommended solution
/ UX (e.g. the `sase tool` command sub-commands you recommend, the TUI changes you
recommend, etc...). 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Prior-art research for `sase tool`

I didn't fetch any GitHub repo files or write any files. Findings marked **[snippet]** come only from search-result summaries, not the page itself. I couldn't open the Tsafrir paper or the SC15 paper directly (404 and 403), so those rely on the patent page and search abstracts.

## 1. Predicting runtime from history, for scheduling

- **Tsafrir, Etsion, Feitelson (IEEE TPDS 2007).** The predictor is just the *average runtime of the user's last two jobs*. When no history exists, it falls back to the user's own estimate. If a job outlives its prediction, the prediction is raised step by step while it runs: first to the user estimate, then +1 minute, then E + 15·2^(k−2) minutes. They report about 25% less average wait time and bounded slowdown than plain EASY backfilling. https://patents.google.com/patent/US8261283B2/en , https://ieeexplore.ieee.org/document/4180346/
  *Implication:* a "median of the last N runs of this command in this project" predictor is enough at first. Treat the prediction as a lower bound that keeps growing while the command runs, never as a deadline.
- **Smith, Foster, Taylor (JSSPP 1998).** Predictions come from "similar" past jobs, with search deciding which attributes define similarity. They were 21–64% better than other methods. **[snippet]** https://link.springer.com/chapter/10.1007/BFb0053984
  *Implication:* key history by a template such as (command argv, repo, workspace kind). Learn which parts of the key matter rather than hard-coding them.
- **Gaussier et al. (SC15).** Uses machine learning with an *asymmetric loss* that punishes underestimates more than overestimates, for about 28% better bounded slowdown. **[snippet]** https://inserm.hal.science/INRIA/hal-01221186
  *Implication:* bias ETAs upward, e.g. show p75 instead of the mean.
- **Slurm.** Backfill scheduling depends on per-job time limits, and `squeue --start` shows each pending job's expected start time. https://slurm.schedmd.com/sched_config.html , https://slurm.schedmd.com/squeue.html
  *Implication:* a TUI can show "expected start" for queued commands, not just "expected finish".
- **How estimates are shown in CI.** Jenkins predicts from the average of the last three stable builds and shows a flashing bar when it has no history or the build is overdue (https://myhandynotebook.wordpress.com/2016/01/18/jenkinss-estimated-duration/). Buildkite's "speed" is the average of the last 30 builds, with no live ETA; users have asked for one (https://buildkite.com/docs/pipelines/dashboard-walkthrough , https://forum.buildkite.community/t/allow-an-estimated-duration-for-jobs-and-show-a-progress-indicator/2878). GitLab shows P50/P95 durations; a progress-bar ETA is still an open request (https://docs.gitlab.com/user/glql/data_sources/pipeline_analytics/ , https://gitlab.com/gitlab-org/gitlab/-/issues/17218). CircleCI shows p50, p95 and max **[snippet]** (https://circleci.com/docs/guides/insights/insights-tests/). GitHub Actions shows only average run time and queue time (https://docs.github.com/en/enterprise-cloud@latest/actions/concepts/metrics). Launchable lets you pick tests by time budget (`--time 10m`) using a time-vs-confidence curve (https://help.launchableinc.com/features/predictive-test-selection/requesting-and-running-a-subset-of-tests/choosing-a-subset-optimization-target/). Develocity predictive test selection learns from change and outcome history (https://docs.develocity.ai/2026.2/using-develocity/predictive-test-selection/).
  *Implication:* show elapsed / p50 (p90) with an explicit "overdue" state. Percentiles are the norm; a live ETA bar is rare.
- **Load-dependent slowdown.** Dinda's Running Time Advisor (2001) predicts runtime from a forecast of host load. You give it the "nominal time on an otherwise vacant machine" and it returns an expected time plus a confidence interval. https://users.cs.northwestern.edu/~pdinda/Papers/cluster01-rta-dinda.pdf . Linux PSI (`/proc/pressure/cpu`, per-cgroup `cpu.pressure`) reports stall time over 10s, 60s and 300s windows, and can wake a program via poll when a threshold is crossed. https://docs.kernel.org/accounting/psi.html . Develocity build scans record CPU used by "other processes" as well as the build. https://gradle.com/blog/optimize-your-gradle-and-maven-builds-with-resource-usage-data/
  *Implication:* store PSI avg10/avg60 and CPU user/sys time with each run. Predict on uncontended runs, and widen the interval when current pressure is high. **I found no CI product that normalizes durations by host contention**; that gap looks real.

## 2. Build and command analytics UX

- **Develocity Build Scan.** Shows timeline, tasks with their inputs, tests with stack traces, dependency graph, the reason for every cache decision, CPU/memory usage, and a side-by-side comparison of two builds. https://develocity.ai/product/build-scan/ . Failure Analytics first groups failures by exact match, then by meaning using a language model. It separates "verification" failures (compile errors, test assertions) from "non-verification" ones (config, infrastructure), and gives each group a stable identity with a daily frequency curve. https://develocity.ai/product/failure-analytics/
  *Implication:* tag each failure as a verification failure or an infra/tool failure, and give failure signatures stable IDs.
- **BuildBuddy (Bazel Build Event Protocol).** Each invocation page shows the full event stream, a Timing tab built from the Bazel profile, per-attempt logs for retried tests, and past failures of a test. https://www.buildbuddy.io/blog/debugging-slow-bazel-builds/ , https://www.buildbuddy.io/blog/introducing-buildbuddy-v1/
- **Turborepo `--summarize`.** Writes a JSON file under `.turbo/runs/` with each task's hash, cache status (local hit, remote hit or miss), inputs and timing. Diffing two summaries explains why hashes differ. `--dry` previews a run. https://turborepo.dev/docs/crafting-your-repository/caching , https://vercel.com/changelog/turborepo-run-summary-is-now-available
  *Implication:* have `sase tool show <id> --json`, plus a diff between two runs that explains why it didn't dedupe.
- **Nx Cloud.** Run details show a retry badge with a log tab per attempt. https://nx.dev/docs/features/ci-features/flaky-tasks
- **Buildkite Test Engine monitors.** "Transition count" (how often a test flips between pass and fail), "passed on retry" (same SHA), Bayesian probabilistic flakiness, "new test", and a duration threshold over a sliding window with separate alarm and recovery thresholds. https://buildkite.com/docs/test-engine/workflows/monitors

## 3. Local command queues and wrappers: shared vocabulary

- **pueue.** Subcommands: `add` (with `-g` group, `-a` depends-on, `-l` label, `-d` start paused), `status` (JSON available), `log`, `follow`, `wait`, `start`, `pause`, `kill`, `restart`, `remove`, `clean`, `reset`, `group`, `parallel N -g group`. Each group has its own concurrency limit. https://linuxcommandlibrary.com/man/pueue
- **task-spooler (`tsp`).** Flags: `-l` list, `-t` tail, `-c` cat output, `-o` output path, `-s` status, `-w` wait, `-k` kill, `-r` remove, `-i` info, `-u` jump the queue, `-S` slots, `-N` needs N free slots, `-D` run after job succeeds, `-L` label. Output is stored in `$TMPDIR`. https://www.mankier.com/1/tsp
  *Implication:* `-N` ("run only if N slots are free") is already a weighted capacity budget.
- **nq.** No daemon; the queue is a directory. `nqtail` (renamed from `fq`) follows running jobs and exits when they finish. **[snippet]** https://aur.archlinux.org/packages/nq
- **chronic** shows output only if the command fails (`-e` also triggers on any stderr) (https://manpages.debian.org/testing/moreutils/chronic.1.en.html). **ntfy** shell integration and **undistract-me** notify when a command runs longer than about 10s and its terminal isn't focused (https://www.tecmint.com/ntfy-get-desktop-or-phone-alerts-for-linux-commands/). **hyperfine** does warmup runs, a minimum run count, JSON export, mean/σ/median/min/max, and warns about outliers caused by interference (https://www.mankier.com/1/hyperfine). **atuin** stores duration, exit code and cwd per command and can search with `--exit` and `--cwd`, but `atuin stats` is still basic (https://docs.atuin.sh/latest/reference/stats/ , https://calebhearth.com/search-sync-shell-atuin).
- **Machine-wide capacity.** Bazel's `--local_resources=cpu=HOST_CPUS-1` schedules actions against estimated per-action resource use (https://bazel.build/docs/user-manual). make `-l` throttles on load average but lags, so it swings between over- and under-scheduling. A system-wide GNU jobserver (implementations "steve" and "guildmaster") hands out tokens across all builds, with crash-safe token recovery; make, ninja, cargo, GCC and LLVM already speak the protocol. https://blogs.gentoo.org/mgorny/2025/11/30/one-jobserver-to-rule-them-all/
  *Implication:* **the vocabulary tools converge on is add/run, status/list, log/show, follow/tail, wait, kill, restart, clean, plus a parallel/slots setting.** Prefer token budgets (jobserver-style, released on crash) over load-average throttling. Consider exporting a jobserver so tools inside a command share the budget.

## 4. Caching and deduplication by input fingerprint

- **Bazel** caches test results when inputs are unchanged and prints "(cached)". `--nocache_test_results` forces a rerun; `flaky = True` allows up to 3 attempts. https://bazel.build/docs/user-manual
- **Nx** hashes source files, environment variables, runtime inputs and arguments, and on a hit replays stdout/stderr and outputs. **Turborepo** does the same with a global hash plus a package hash, and always replays logs. https://nx.dev/docs/concepts/how-caching-works , https://turborepo.dev/docs/crafting-your-repository/caching
- **pytest-testmon** uses coverage to map tests to code and reruns only tests affected by changes. **pytest's own cache** offers `--lf`, `--ff`, `--sw` and `--lfnf=none`. https://www.testmon.org/ , https://docs.pytest.org/en/stable/how-to/cache.html
- **Single-flight.** Go's `singleflight.Do(key)` lets duplicate callers wait for one in-flight call and share its result; `Forget` drops the key (https://pkg.go.dev/golang.org/x/sync/singleflight). BuildBuddy's "action merging" applies this to build actions: a Redis map from action to primary execution with short, renewed TTLs, reference counting so an execution is only cancelled when nobody waits on it, and "hedged" duplicate runs when an execution is stuck. It merges more than 1,000 actions/s, saving some tests about 3 hours. https://www.buildbuddy.io/blog/action-merging/
  *Implication:* key `just check` by (tree hash + dirty-diff hash + command + toolchain/environment hash). If a matching run is in flight, other agents attach to it; if one finished with a pass, replay it. Reference-count waiters before cancelling, and add a hedge for stuck runs. Never reuse a *failed* result without checking for flakiness (topic 6).

## 5. Coding agents and tool calls

- **Claude Code hooks.** A PreToolUse hook returns `hookSpecificOutput.permissionDecision` ("allow"/"deny"/"ask"/"defer" **[snippet]**; the fetched docs page listed only allow/deny) and `updatedInput`, which partially overrides the tool arguments. It can also add `additionalContext`, and exit code 2 blocks the call. **PostToolUse cannot modify tool output**; it can only add `additionalContext` or `systemMessage`. Default hook timeout is 600s. `async`/`asyncRewake` hooks run in the background, and `asyncRewake` wakes Claude on exit 2. https://code.claude.com/docs/en/hooks
  *Implication:* rewrite Bash `just check` into `sase tool run -- just check` in PreToolUse. Output compaction has to happen inside the wrapper, because PostToolUse can't do it.
- **Codex CLI.** Hooks cover PreToolUse (deny, or `updatedInput`, which for Bash must include a `command` string), PermissionRequest, PostToolUse and others. Unlike Claude, a PostToolUse `"decision":"block"` *replaces the tool result* with the hook's feedback. https://learn.chatgpt.com/docs/hooks . Separately, Starlark `prefix_rule(pattern, decision=allow|prompt|forbidden, justification, match/not_match)` rules apply the most restrictive match and can be tested with `codex execpolicy check`. https://learn.chatgpt.com/docs/agent-configuration/rules . One source says hooks were experimental and first shipped in v0.114 (https://agenticcontrolplane.com/blog/codex-cli-hooks-reference); OpenAI's docs now say they are enabled by default. **Treat the details as version-dependent.**
- **Output cost for agents.** HumanLayer's `run_silent` wrapper prints "✓ description" on success and the full output on failure, and suggests fail-fast flags (https://www.humanlayer.dev/blog/context-efficient-backpressure). Anthropic's parallel-Claudes compiler post says the harness should print "a few lines" and log everything else to a file, put `ERROR` and the reason on one grep-friendly line, pre-compute summary stats, and offer a deterministic `--fast` 1%/10% sample (https://www.anthropic.com/engineering/building-c-compiler). Claude Code's Bash output limit is 30k characters by default, cut from the middle, adjustable with `BASH_MAX_OUTPUT_LENGTH` (https://github.com/anthropics/claude-code/issues/19901). One post shows an assertion at character 44,332 of a 74k-character log never reaching the model (https://wmedia.es/en/tips/claude-code-truncated-output-tests). RTK rewrites commands through a PreToolUse hook to compress output, claiming 60–90% fewer tokens **[snippet; vendor claim]** (https://dev.to/terminalchai/rtk-a-high-performance-rust-cli-proxy-that-slashes-ai-agent-token-costs-3bj5).
  *Implication:* default to printing a short summary (status, duration vs p50, failure lines, path to the full log). Never let failures sit in the middle of the output.
- **Contention between agents.** "Three agents running `npm test` at once on an 8-core machine makes all three slow"; the post suggests 4–6 sessions are fine if only 1–2 are building (https://moltamp.com/blog/run-multiple-claude-code-sessions-2026/). These are anecdotal blog posts; I found no rigorous measurements. Anthropic's post coordinates agents with lock files in `current_tasks/`.

## 6. Flaky tests and duration regressions

- **Same inputs, different outcome** is the common definition. Develocity flags a test when it fails then passes on retry within one run, or when outcomes differ across builds with the same input fingerprint (https://docs.develocity.ai/2026.2/using-develocity/flaky-test-detection/). Nx flags a task hash that both failed and succeeded, retries it on a different agent, and clears the flag after 2 weeks without incidents (https://nx.dev/docs/features/ci-features/flaky-tasks). Buildkite and CircleCI use pass and fail on the same SHA, CircleCI within a 14-day window (https://buildkite.com/docs/test-engine/workflows/monitors , https://circleci.com/docs/guides/insights/insights-tests/).
  *Implication:* sase already has the fingerprint from topic 4, so flakiness detection comes almost for free.
- **Meta's probabilistic flakiness score.** A Bayesian (Stan) model estimates the chance of failing when the code is good, using only existing retries. Rising scores open tickets, and badly flaky tests lose eligibility for change-based test selection. https://engineering.fb.com/2020/12/10/developer-tools/probabilistic-flakiness/
- **Prediction without reruns.** Flip rate plus recent churn gives F1 = 95.5%. https://arxiv.org/abs/2302.09330 . Rerun-based detection needs about 100 reruns to find half of flaky tests. **[snippet]**
- **Duration regressions.** MongoDB and the Hunter tool use E-divisive change-point detection (Hunter swaps the permutation test for a t-test) to find the commit that caused a slowdown. https://www.mongodb.com/blog/post/using-change-point-detection-find-performance-regressions , https://arxiv.org/pdf/2301.03034 . Buildkite's duration monitor uses sliding-window thresholds with hysteresis.
  *Implication:* run change-point detection on each command's contention-filtered duration series (topic 1). Alert on step changes, not single slow runs.

I checked all nine areas. The most important finding is that `sase tool run` has already been designed in this checkout, and the in-progress epic **sase-zm** ("Command capacity reservations and fleet load meters") is building on that design. The design is in `sase/repos/research/202609/command_capacity_and_load_meter/command_capacity_and_load_meter.md:83-178`:
- **Commands:** `sase tool run -- just check`, plus `-q` (queue), `-f` (force), `-w` (extra weight), `-n` (dry run) and `sase tool status`.
- **Refusal:** exit 75 with a `capacity_unavailable` outcome.
- **Accounting and queueing:** a command reservation on top of the agent's base capacity claim; queueing hands the command off to a parked monitor.

Two critiques sit next to it: `command_capacity_epic_critique.md` and `command_capacity_epic_architecture_critique.md`. No `sase tool` code exists in `src/` yet.

---

## 1. Duration and timing history

**Per-test-file durations**
- `tests/_test_selection_timings.py:66-127` sets the location to `<health store>/timings/<UTC>-<pid>.json`. The directory can be overridden with `SASE_TEST_SELECTION_TIMINGS_DIR`.
- Records are built and written at `:151-210`: `{schema, mode, worker_count, host, file_count, durations{path: seconds}}`. `load_timing_table` (`:310`) merges them.
- `tests/_test_selection_timings_plugin.py` does the recording, enabled from `tools/run_pytest:902-921`.
- A committed copy for CI shards lives in `tests/shard_timings.json`, read by `tests/_test_shards.py:61` and refreshed by `tools/refresh_shard_timings`.

**Suite runs and flake history** (`tests/_test_selection_health_store.py`)
- The store is `${SASE_HOME:-~/.sase}/test-selection/<project-key>/`, override `SASE_TEST_SELECTION_HEALTH_DIR` (`:16, :37-60, :119-127`). Retention is 30 days.
- File names follow `<ts>-<head>-<pid>[-kind].json` (`:139-143`). There are two kinds:
  - **`selection`** (`record_selection`, `:171`): the scoped manifest plus `duration` and `outcome`, added by `tools/run_pytest:811-845`. The working copy is `.pytest_cache/sase-selection/manifest.json` (`tests/_test_selection_manifest.py:34-36`).
  - **`full-run`** (`full_run_record`, `:207-238`): `head, mode, exit_status, workspace, changed_files, tree_dirty, failures[]`. It has no duration.
- Readers: `tests/_test_selection_health_records.py:23` (`SelectionRecord`, `.duration` at `:67`) and `:103` (`FullRunRecord`).
- Flakes are derived from these records, not stored separately: `tests/_test_selection_health_correlation.py:110` (`retired_flake_evidence`), `:364` (`reproducible_flake_nodeids`), `:395` (stale). The committed baseline is `tests/reproducible_flake_baseline.txt` (`tools/selection_health:44`).

**Test cost**
- `tests/_test_cost_records.py:29-32` stores records at `<health store>/cost/`, keeping 8 (override `SASE_TEST_COST_DIR`).
- `build_cost_record` (`:241-292`) records per-file wall, CPU and idle seconds, per-cause seconds, worker wall/CPU, collection seconds and an RSS curve.
- Budgets are committed in `tests/perf/baselines/test_cost_budgets.json`, loaded at `tests/_test_cost_budgets.py:55` and checked by `tools/check_test_cost_budgets`.

**Suite gate (pytest worker tokens)**
- Tokens live in `/tmp/sase-pytest-tokens-<uid>` (`tests/_suite_gate_env.py:43-48`).
- Each holder records `argv, budget, granted, heartbeat, lease_id, pid, progress, started, starttime` (`tests/_suite_gate_holders.py:32-47`), plus a progress sidecar (`_suite_gate_progress.py:42-66`). These records are temporary.

**Whole-command durations (`just check` etc.): none are recorded.**
- `tools/run_silent:170-179` writes only `{description, exit_code, status, output_bytes, output_lines, recorded_at_epoch}`. There is no start time or elapsed time.
- It writes to `$SASE_ARTIFACTS_DIR/continuation_stage_diagnostics.jsonl` and `$SASE_MONITOR_DIAGNOSTICS_DIR/stages/<id>.json`. On failure it also keeps bounded output in `stage_output/<id>.log` (256 KiB per stage, 2 MiB total).
- `check` and `check-full` are made entirely of `run_silent` stages (`Justfile:649-687`).
- The closest existing timings:
  - monitor `elapsed_seconds` (§2)
  - proc `started_at`/`finished_at` (§2)
  - per-agent `tool_calls.jsonl` `duration_ms` (§5)
  - `~/.sase/logs/dev_update.jsonl` (`tools/dev_update_timings:14`), for dev-update steps only

**Reuse:** Wrapping each `run_silent` stage with start and elapsed time would give per-stage history almost for free. The health store's project-key layout (`store_directory`, `project_key`) fits a per-project history of command durations. Timing tables and cost records could estimate how long `check` will take.

## 2. Proc and monitor records

**Procs** (`src/sase/procs/`)
- **Paths** (`paths.py:9-26`): `~/.sase/procs/procs.jsonl` (the Rust core owns this file; `store.py` calls bindings at `:320`) and `~/.sase/procs/logs/`.
- **`Proc` fields** (`models.py:32-79`):
  - identity and command: `proc_id, label, kind, status, command, argv, cwd, origin`
  - timing and result: `created_at, started_at, finished_at, exit_code, phase, message, result`
  - process and log: `pid, pgid, log_path, log_owner`
  - attribution: `project, workspace_num, session_id, session_label, cl_name, tags, shell_name, shell_kind`
  - scheduling and limits: `concurrency_keys, request_fingerprint, timeout_seconds, idle_timeout_seconds`
  - supervision and stop: `supervisor_id, stop_requested_*, settled_*`
- A proc has **no queue weight and no agent-family field**; attribution is only session, project and tags.
- `ProcReserve` is at `:297-323`.
- **Output** is merged stdout+stderr through `BoundedLogPipe` (`supervisor.py:147-159`). The cap is `SASE_PROC_LOG_MAX_BYTES`, default 2 MiB (`logs/_bounded.py:13`).
- Text trimming and redaction: `text_bounding.py:31, :45`.
- **CLI:** `main/parser_proc.py` provides `kill` (38), `list` (67), `run` (180; `-c/-j/-l/--shell/-p/-q/-s/-t/-w`) and `show` (278). `main/proc_render.py:75` computes a duration.

**Monitors** (`src/sase/monitor/`)
- A monitor is an agent-family member (`agent_meta.agent_family_role == "monitor"`) whose state is in its artifacts directory (`agent_meta.json`, `done.json`; `store.py:6, :103-117`).
- **`MonitorRecord` fields** (`models.py:88-138`):
  - `command, cwd, reason, label, start_status, stop_status`
  - `timeout_seconds, idle_timeout_seconds, tail_lines, monitor_state`
  - `pid, pgid, exit_code, elapsed_seconds, output_path, output_truncated`
  - `starter_agent, followup_agent, profile, policy_digest, completion_ref`
  - `diagnostic_manifest_ref, retained_log_ref, monitor_result_id/ref`
  - `host_completion_status/message/reason, budget_decision_path`
  - `monitor_elapsed_seconds` is written at `proc_adapter.py:242, :327`.
- **Output** goes to `<artifacts>/live_reply.md`, capped by `SASE_MONITOR_LOG_MAX_BYTES` (default 2 MiB, keeps head and tail) (`logs.py:15-27`).
- **Finish** (`supervise.py:422-470`): records exit code, truncation and timeout kind, then assembles `diagnostics/diagnostic_manifest.json` from the stage reports (`diagnostics.py:16-78`).
- **Queue weight:** `monitor/start.py:218` passes `queue_weight_override`. `core/runner_slots/_admission_capacity_records.py:17-21` allows a quiet zero-weight monitor start.
- **`sase monitor show`** (`main/monitor/show.py:23-66`) prints `monitor_detail(record)` (imported from `main/monitor_render`) and then the output tail. Options: `--follow`, `--log-lines`, `--all-lines`, `--range`, `--max-bytes`, `--diagnostics`, `--format/--json`, `--output-only` (`parser_monitor.py:125-198`).

**TESTING/TESTED: there is no command recognizer.** The labels are only the `verify` profile (`monitor/profiles.py:9-27`), chosen explicitly with `-p verify` or `-s/-S`. The skill text is `xprompts/skills/sase_monitor.md:42-50`, and label matching is case-insensitive (`monitor_status.py:135`). Nothing classifies argv.

**Reuse:** The proc runner already provides a supervised process with a bounded log, timeouts and a durable record. It is the natural host for `sase tool run`, plus a new `kind`/tag and weight fields. Monitor diagnostics already consume `run_silent` stages.

## 3. Telemetry and event logs

**`sase telemetry`**
- An in-house metric registry flushed to a Rust-owned SQLite store at `~/.sase/telemetry/metrics.sqlite` (`telemetry/_config.py:46-48`; `_registry.py:35, :98-119` has init, flusher thread and flush).
- Metrics are declared in `METRIC_DEFS` (`metrics.py:80+`) as `(attr, kind, name, doc, labels, kwargs)`, including histogram buckets. `HOOK_DURATION`, `WORKFLOW_DURATION` and `AGENT_RUN_DURATION` already exist (`:19-79`).
- Subcommands (`main/parser_telemetry.py`): `cleanup` (21), `health` (49), `list` (59), `snapshot` (75), `status` (92). Queries: `telemetry/query.py:51, :97`.

**Append-only JSONL event logs**
- `logs/run_log.py:1-122`:
  - `log_agent_run(..., duration_seconds, status)` writes `~/.sase/logs/runs.jsonl`
  - `log_event(event=..., **kw)` writes `~/.sase/logs/events.jsonl`, with 17 call sites
- `logs/tui_telemetry.py:45-98` defines perf JSONL logs (stalls, git_ops, launch_timing, external_tools, agent_loads, startup). `stats/perf_query.py:1-30` combines these with telemetry for the Statistics pane.

**Reuse:** Add a `TOOL_RUN_DURATION` histogram labelled by profile and status, plus a `log_event(event="tool_run", ...)` record, or a dedicated JSONL written through `logs/_bounded.append_jsonl_record` (which rotates).

## 4. ACE TUI

**Layout**
- The top-level tabs are **agents, artifacts, axe** (`tab_order.py:12, :27`). There is no top-level Procs or Notifications tab.
- **Procs** is a pane in the Admin Center (`modals/config_center_catalog.py:88-172`, tabs config/logs/machines/procs/projects/statistics/updates). Files: `modals/procs_pane.py` (plus `_render`, `_store`, `_filter`, `_actions`, `_agent_jump`) backed by `proc_observer.py` / `_proc_observer_store.py`.
- Top-bar counters: `widgets/proc_indicator.py:11` (`ProcIndicator`, `MonitorIndicator`).
- Other panels: `modals/runners_modal.py` + `_runners_data.py`; `modals/machines_pane*.py`; `statistics_pane_runners.py` (built by `stats/_runner_view.py`).
- Notifications: `modals/notification_modal*.py`, `widgets/notification_indicator.py`.

**Tools panel**
- `src/sase/ace/tui/tools/` reads each agent's `tool_calls.jsonl` regardless of provider:
  - `ToolCallEntry` (`_entry.py:14-40`): `tool_name, status, duration_ms, recorded_at, completed_at, tool_input_summary` (includes `command`), `tool_response_summary`, `cwd, session_id, transcript_path`
  - `slow.py:20-28` defines `SlowToolCall`; the default slow threshold is 20 s (`_constants.py`)
- `tools/report.py` writes Markdown **slow tool-call reports** to `~/.sase/tool_call_reports/`, keeping 50. It recovers the full output from the provider transcript (`_report_recovery`).
- `widgets/tools_panel.py` is the Tools timeline in the agent detail view. `widgets/_tools_panel_details.py` renders the expanded detail (stdout/stderr previews, command, timeout). Report hints: `widgets/prompt_panel/_tool_call_report_hints.py`.

**Proc and monitor rows in the Agents tab**
- `models/agent_proc_shells.py:1-40` turns observed procs into Agent rows (preview limit 4000 chars, log tail 12000).
- Detail sections, including running output:
  - `prompt_panel/_agent_proc_shell_section.py:165, :214` (`build_proc_shell_output`)
  - `prompt_panel/_agent_monitor_section.py:248, :277-320`: `build_monitor_output` renders `live_reply.md` through `render_axe_output` with a truncation notice

**Reuse:** A tool run shown as a proc-shell or monitor row gets the detail panel and live output for free. The slow tool-call surface already identifies which Bash commands are slow.

## 5. Provider hooks and Bash tool-call records

**SASE does not install PreToolUse/PostToolUse hooks.**
- `llm_provider/_tool_calls.py:1-11`: new Claude runs parse `stream-json` and do not install tool-call hooks.
- `_tool_call_claude.py:24-28` keeps hook parsing only for old artifacts.
- Providers run with permissions bypassed: `claude.py:339-341` (`--output-format stream-json --dangerously-skip-permissions`) and `codex.py:413-416` (`exec --dangerously-bypass-approvals-and-sandbox`).
- `_hookspec.py` holds pluggy provider-plugin hooks, and `file_hooks/` is commit/artifact file hooks; neither is a tool hook.
- **SASE therefore cannot intercept or rewrite an agent's Bash calls.** It only observes them afterwards. Steering today is instruction-based, for example the `sase_monitor` skill.

**Recorded calls**
- Location: `$SASE_ARTIFACTS_DIR/tool_calls.jsonl`, written by per-provider normalizers `_tool_call_{claude,codex,qwen,grok,muse,agy}.py`.
- Schema: `_tool_call_common.py:12-13, :48, :497-516`.
- `duration_ms` is measured by the parser between the ToolUse and ToolResult events (`:535-550`), so it is approximate.
- Command output tail and redaction: `:413, :470`. Unfinished calls are closed at `_tool_call_finalize.py:17-58`; write errors go to `tool_calls_writer_errors.jsonl`.

**Reuse:** Mining every agent's `tool_calls.jsonl` for Bash `command` + `duration_ms` yields historical slow-command data today, with no new instrumentation.

## 6. Runner slots and capacity

**Configuration:** `default_config.yml:57-67` sets `max_running_agents: 10`. A normal agent claims 1.0; `%queue(weight=...)` can change that. Serial families share one claim, while axe runners and workflow steps are excluded. Readers are `config.core.get_max_running_agents` / `get_configured_max_running_agents`, used for example at `integrations/agent_list_entries.py:190`.

**How load is computed:** it is the sum of claimed queue weights in the Rust capacity snapshot built from artifact scans. It is not measured machine load.
- `core/runner_slots/_admission.py:29` (`running_agent_slot_count`) and `:43` (waiters)
- `_admission_snapshot.py:18, :63` (`runner_capacity_snapshot(effective_limit)`)
- `_admission_capacity_records.py:28-57, :130-160` (how weight is resolved)
- `_admission_types.py:20-23` (weight must be positive and finite)
- `_signal.py` (state-change signal) and `_scan_cache.py`

**Machine load sampling:** there is **no loadavg or `/proc/pressure` sampling** anywhere in `src/`, `tests/` or `tools/`.
- The only memory check reads `MemAvailable` from `/proc/meminfo` for the pytest token budget, reserving 700 MiB per token (`tests/_suite_gate_budget.py:37, :96-133`).
- The only other hint is `os.cpu_count()` sizing a thread pool at `ace/tui/models/_loaders/_json_cache.py:80`.

**Reuse:** Rust admission is the single authority the sase-zm design says to extend with reservations. The suite gate's memory-based budget is the only existing hardware-aware policy.

## 7. Notifications and gates

**Notifications**
- Store: `~/.sase/notifications/notifications.jsonl`, appended through Rust (`notifications/store.py:37-48, :64`).
- API: `append_notification` (`:134`), `upsert_notification` using `dedup_key` (`:177`), `append_notification_plus_one` (`:147`).
- `Notification` fields (`models.py:25-44`): `id, timestamp, sender, icon, color, notes, files, tags, action, action_data, read, dismissed, silent, muted, snooze_until, plus_ones, dedup_key`.
- A ready template is `senders.py:20-44` (`notify_workflow_complete`), with `_format_duration` at `:331`.
- Monitors do not send notifications. On completion they start a follow-up agent or run host completion (`monitor/followup.py:106`).

**Gates**
- `sase gate` has `act, answer, cancel, list, create, show, wait` (`main/parser_gate.py:52-522`).
- Each gate is a bundle of `request.json`, `response.json` and `cancellation.json` (`notification_gates/paths.py:23-40`); gate-shell members live in `gate_shell/`.

**Sudo**
- `sudo/gate.py:21-171`: the request carries a manifest SHA-256, approve/deny options and risk badges.
- `sudo/runner.py:13` returns a JSON receipt, validated at `sudo/receipt.py:16`.

**Reuse:** `notify_workflow_complete`-style notifications with a `dedup_key` fit "check-full finished". Gates cover force/queue decisions that need the user's approval.

## 8. Patch HOOKS

- **Model** (`ace/patch/models/hooks.py`):
  - `HookStatusLine` (`:9-48`): `stitch_id, timestamp, status` (RUNNING/PASSED/FAILED/KILLED), `duration` (text such as "1m23s"), `suffix, suffix_type, summary`
  - `HookEntry` (`:105-126`): `command, status_lines`
  - These are persisted as text in the Patch file's HOOKS section.
- **Execution** (`ace/hooks/execution.py:26+`): a bash wrapper retries up to 3 times, 60 s apart, on known transient errors. It writes output plus an end marker carrying the end timestamp and exit code.
- **Completion** (`:255-292`): computes the duration and records `HOOK_EXECUTIONS`, `HOOK_DURATION` and `HOOK_RETRIES`.
- **Output:** `sharded_path("hooks", "<patch>-<ts>.txt")` (`persistence.py:20-32`), compacted by `output_capture.py:16`.
- Durations are recorded in both the Patch file and telemetry.

**Reuse:** The end-marker plus timestamp duration pattern and `HOOK_DURATION` are a working precedent. Hook commands could run through the same wrapper and reservation.

## 9. Verification receipts

- **`sase final prepare`** (`finalizers/prepare.py:58-192, :474-526, :570`):
  - persists a conditional completion intent as `<intent_id>.json` plus `index.json`
  - records each repo's `head`, `head_tree` and `index_tree`
- **Contract types** (`core/continuation_wire.py:303-370`): `ConditionalCompletionIntentWire` with a verification contract, `verification_command`, observations, a seal (including `worktree_fingerprint`) and a binding (`monitor_id`, `bound_command`).
- **Binding:** `sase monitor start -f/--completion REF`, single-use (`parser_monitor.py:257`).
- **Host completion** (`monitor/host_completion.py:1-60`): when the monitor succeeds, finalizers run without a model.
  - `host_completion_state.py:112` and `:480-504` recompute the observation fingerprint; `execution_context_drifted` detects stale verification.
  - The receipt is `<artifacts>/host_completion_receipt.json` (`monitor/delivery.py:34, :378-397`).
- **sase-zl** is the closed epic "Reliable monitor continuations with clear results and bounded context". It produced monitor result projection (`monitor/result_projection.py`), diagnostic manifests and `presentation.py` summaries.
- **"Tested at commit X" for pytest:** full-run health records store `head` + `exit_status` + `tree_dirty` (§1).
- There is no general receipt saying "`just check` passed at HEAD X".

**Reuse:** The prepared-completion seal (head, tree and index fingerprint plus bound command) is ready-made "verified at commit" data. A tool-run receipt could reuse `_observation_fingerprint` so that re-running an unchanged tree can be skipped.

I wrote the report and registered it as a durable snapshot (`file:explicit:4f089bcc6687ce577eea32fb`). The host accepted the commit declaration for the research repo.

**Report:** `sase/repos/research/202609/sase_tool_use_cases_and_ux__b.md`

## What the data says

I measured 35 days of history on athena: 180,441 agent Bash calls from `tool_calls.jsonl` and 1,054 monitors.

- **Most of the wasted time isn't a capacity problem.**
  - 61 of the 67 wall-hours spent in `just check-full` monitors went to runs that failed or timed out.
  - In 13 of the 23 recent failures with stage diagnostics, a lint gate (symvision, mypy, ruff and others) failed first.
  - 44% of verification monitors' follow-up text tells the next agent how to tell pre-existing failures from new ones.
- **Most heavy verification runs inline, not in monitors.** Agents ran `just check` inline 7,020 times (341 hours), and `just check-full` inline 504 times even though the memory says to use a monitor. A monitor-based design would miss most of the real load.
- **Some inline runs are killed by the provider.** Their durations cluster at exactly 120 s and 600 s, which matches provider Bash timeouts.
- **Your end-time prediction idea holds up, but nothing records load today.** The median inline `just check` goes 5.0 → 7.2 → 14.3 min as overlapping heavy commands rise. That correlation is confounded, so treat it as suggestive. Load has to be recorded on every run starting now.

## Your two ideas, sharpened

- **Visibility:** make a tool run its own record and show it live on the owning agent's row and in its details. Inline runs need to show up too.
- **Prediction:** show a range and a clear "overdue" state rather than a countdown. The most useful thing a prediction does is decide automatically whether to run inline or hand off to a monitor, so agents stop guessing. It also gives queued work an expected start time, feeds scheduling, and replaces guessed timeouts.

## Use cases you missed (highest leverage first)

1. **Reusing passing results:** skip a rerun when the tree and inputs are unchanged, including skipping `just install` (1,798 calls, 74.5 hours).
2. **Failure triage:** tag failures as new, known or flaky, grouped across agents.
3. **Output sized for agents:** a short summary with the full log kept on disk.
4. **Cheap stages first:** run lint before reserving heavy capacity.
5. **Hang detection:** timeouts set from past run times instead of guesses.
6. **Measured weights:** set capacity weights from recorded CPU and memory use.
7. **Cost per bead or epic:** machine-hours, including time spent on failed runs.
8. **Slowdown detection:** notice when a tool's typical duration steps up.

## Recommended UX

- **Per-project tool list:** each project names its tools in `sase/sase.yml`.
- **One command for agents:** `sase tool run check -n '…'`. In one turn it decides whether to reuse a passing result, run inline, hand off or queue, and says why on one line.
- **Bare `sase tool`:** a dashboard with one row per tool.
- **Other subcommands:** `runs`, `show`, `status` and `stop` first; later `stats`, `receipt`, `failures` and `rerun`.
- **Option letters:** shared concepts use the same letters as `sase monitor start`, and `-w` always means the command's own cost.
- **TUI:**
  - a `TESTING check 6:12 / ~9m` chip on agent rows;
  - a tool-run card in agent details;
  - a new Tools pane in the Admin Center.

## Recommended order

1. Record every run, starting from a backfill of existing history.
2. Add prediction and automatic hand-off.
3. Add result reuse and failure triage.
4. Build the capacity queue last, calibrated by what was recorded.

This order is also the "observability first" and "shadow mode" step that both earlier critiques of `sase-zm` asked for.

The specimen CLI outputs in the report are marked illustrative wherever the numbers aren't measured.
