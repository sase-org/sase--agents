- **AGENTS:**
  - [bbugyi200.athena.toobig-4p.bench_prompt_search.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-4p.bench_prompt_search.0/README.md)

%wait:toobig-4p.driver.0 %id(bench_prompt_search.0, clan=toobig-4p) %model:@medium %auto
%wait(runners=3) %wait(priority=20) #gh:gh_sase-org__sase Can you help me split the
`tests/perf/bench_prompt_search.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.
