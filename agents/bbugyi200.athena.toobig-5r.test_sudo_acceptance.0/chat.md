# Chat History - ace-run (toobig-5r.test_sudo_acceptance.0)

- **TIMESTAMP:** 2026-09-22 02:50:03 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_sudo_acceptance.0

## Prompt

%id(test_sudo_acceptance.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_sudo_acceptance.py` file up into multiple files? Use your best
%wait:toobig-5r.test_run_agent_wait.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 986-line `tests/test_sudo_acceptance.py` is now five files, all well under 500 lines:

- [tests/_sudo_acceptance_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/_sudo_acceptance_helpers.py) (197 lines) — shared builders and canary-token assertions (`_request`, `_runner_ledger`, `_runner_receipt`, `_sensitive_tokens`, `_assert_*`, `_iter_files`, `_FAKE_CAPABLE_RUNNER`, `_install_capable_runner`), following the existing `tests/_*_helpers.py` + `from tests._sudo_ssh_fake import ...` convention.
- [tests/test_sudo_acceptance_credentials.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_sudo_acceptance_credentials.py) (160 lines) — canary credential non-persistence (2 tests).
- [tests/test_sudo_acceptance_refusals.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_sudo_acceptance_refusals.py) (146 lines) — headless/TTY refusals and manifest/command integrity (4 tests, one parametrized ×4).
- [tests/test_sudo_acceptance_detached.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_sudo_acceptance_detached.py) (294 lines) — detached answer/finalize flows (4 tests).
- [tests/test_sudo_acceptance_remote.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_sudo_acceptance_remote.py) (265 lines) — remote finalize flows (2 tests).

The original file is deleted. No test logic changed: an AST comparison of all 23 top-level definitions against the original confirmed identical bodies with nothing added or dropped, and function-local imports were left in place.

Verification: all 15 tests pass under the project venv (8.7s), and `sase tool run check` succeeded end-to-end (ruff, mypy, symvision, toobig, and the diff-scoped test lane). One environment note: the system `python3.11` can't even import this repo's packages — tests must run under `.venv/bin/python`.

Declaration submitted: commit of the sudo acceptance test split.
