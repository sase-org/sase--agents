#gh:sase_fq_8_1_scratch_probe_1 #fork:tw It looks like there is still an issue (see the GitHub `test` job's partial failure output below). Can you help me diagnose the root cause of this issue and fix it? #plan #m_opus
```
ERROR tests/test_run_pytest_scoped.py::test_scoped_escalation_runs_the_governed_fast_lane - Failed: tests/test_run_pytest_scoped.py::test_scoped_escalation_runs_the_governed_fast_lane left TMPDIR: '/var/tmp/sase-d1260045/pytest-of-runner/pytest-0/popen-gw2/test_scoped_mode_reports_a_fai0/scratch' -> '/var/tmp/sase-d1260045/pytest-of-runner/pytest-0/popen-gw2/test_scoped_escalation_runs_th0/scratch' changed after its own teardown. Route the mutation through monkeypatch.setenv()/delenv() so teardown restores it -- an unrestored TMPDIR points every later test on this worker at a tmp_path pytest has already deleted.
= 3 failed, 25831 passed, 18 skipped, 69 warnings, 10 errors in 742.34s (0:12:22) =
error: Recipe `test` failed on line 333 with exit code 1
Error: Process completed with exit code 1.
```