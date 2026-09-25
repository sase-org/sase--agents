# Chat History - ace-run (toobig-4p.bench_prompt_search.0)

- **TIMESTAMP:** 2026-09-06 08:22:39 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-4p.bench_prompt_search.0

## Prompt

%wait:toobig-4p.driver.0
%id(bench_prompt_search.0, clan=toobig-4p)
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `tests/perf/bench_prompt_search.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting `tests/perf/bench_prompt_search.py` and the surrounding test layout so we can split it into files of 500 lines or less.

The file is large; I'll map its structure, line count, and how similar perf tests are already split.

The file is 916 lines. Next I’ll read the rest of it and match the split to how other perf benches are packaged.

I'll split this the way `tui_trace` is structured: a thin `bench_prompt_search.py` entry plus a `prompt_search/` package for corpus, worker, measurement, and harness.

I'll pin the worker subprocess to the repo root so `python -m` resolves, then check line counts.

Next I’ll run the smoke test to confirm the split still launches workers, then `just check`.

`just check` passed. Next I’ll pull the finalizer context and submit the turn declaration.

Split `tests/perf/bench_prompt_search.py` (916 lines) into a thin entry module plus a `tests/perf/prompt_search/` package, matching the `tui_trace` layout. Every file is well under 500 lines.

| File | Role | Lines |
| --- | --- | --- |
| `tests/perf/bench_prompt_search.py` | CLI + pytest smoke test | 84 |
| `tests/perf/prompt_search/corpus.py` | Synthetic archive/local corpus | 213 |
| `tests/perf/prompt_search/worker.py` | Fresh-process search worker | 132 |
| `tests/perf/prompt_search/measure.py` | Timing summaries + Unicode microbench | 231 |
| `tests/perf/prompt_search/harness.py` | Scenarios, subprocess runs, `run_bench` | 332 |
| `tests/perf/prompt_search/__init__.py` | Package marker | 1 |

Behavior is unchanged: `just bench-prompt-search` still runs the same script, and workers now launch as `python -m tests.perf.prompt_search.worker` so the package split does not depend on `__file__`.

Verified with the slow smoke test (`1 passed`) and `just check`.
