#gh:gh_sase-org__sase GitHub Actions is failing with the below error. I have a feeling this is just a transcient error. Can you help me confirm/deny my suspicion, diagnose the true root cause of this issue, and fix it? #plan #m_opus 
```
.venv/bin/python tools/validate_sase_core_rs_version --pyproject pyproject.toml --published-minimum
.venv/bin/sase validate
SASE validation
  ok     init memory --check
  ok     init repo --check
  ok     init skills --check
  fail   plan links validate

plan links validate failed (exit 1)
stdout:
SDD validation failed: 2 errors, 537 warnings (use --show-warnings to display)
stderr:
error: 202607/prompts/vcs_backed_artifact_capture.md: 202607/vcs_backed_artifact_capture.md is missing a valid 'prompt' link (reverse-link)
error: 202607/vcs_backed_artifact_capture.md: missing 'prompt' link to 202607/prompts/vcs_backed_artifact_capture.md (missing-link)

For broader diagnostics, run `sase doctor -v` or `sase doctor -j` and attach the output when asking for help.
error: Recipe `validate` failed on line 518 with exit code 1
Error: Process completed with exit code 1.
```