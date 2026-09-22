# Chat History - ace-run (toobig-5r.ssh.0)

- **TIMESTAMP:** 2026-09-21 20:42:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.ssh.0

## Prompt

%id(ssh.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/sudo/ssh.py` file up into multiple files? Use your best
%wait:toobig-5r.execution.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Split complete, pending the final `just check` confirmation — I'll report once it lands.

Summary of the change so far:

- `src/sase/sudo/ssh.py` (989 lines) → 5 modules, all ≤500 lines: `ssh.py` (28-line compat facade, same `__all__`), `ssh_defs.py` (constants + models), `ssh_paths.py` (remote path sets), `ssh_transport.py` (SSH runner, TTY stdio, remote file fetch/copy), `ssh_exec.py` (contract probe, stage, sync/detached spawn), `ssh_detached.py` (liveness, ledger wait, cleanup).
- Helpers shared across files had to become public (`run_ssh`, `ssh_argv`, `coerce_paths`, …) — the repo's symvision gate forbids cross-file private imports; file-local helpers kept their underscore names.
- Updated `tests/test_sudo_ssh.py` / `tests/test_sudo_acceptance.py` patch targets and helper imports to the new homes.
- Targeted suites pass (52 passed); ruff, format, and symvision are green.

Done. `src/sase/sudo/ssh.py` (989 lines) is now five modules, all comfortably under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `ssh.py` | 28 | Compatibility facade; same `__all__` as before |
| `ssh_defs.py` | 104 | Shared constants, `CommandRunner`, path/contract/liveness models |
| `ssh_paths.py` | 71 | Remote handoff path sets + `allocate_remote_sudo_paths` |
| `ssh_transport.py` | 357 | SSH runner/argv, TTY stdio, remote file fetch/copy |
| `ssh_exec.py` | 339 | Contract probe, manifest staging, sync + detached spawn |
| `ssh_detached.py` | 250 | Liveness probe, ledger wait, remote cleanup |

Notes:

- No behavior change — pure move, plus one tiny simplification (`_cleanup` adapter folded into direct `cleanup_remote_sudo` calls).
- Helpers used across files had to drop the underscore prefix (`run_ssh`, `ssh_argv`, `coerce_paths`, …): the repo's symvision gate forbids cross-file private imports. File-local helpers kept underscore names.
- `tests/test_sudo_ssh.py` and `tests/test_sudo_acceptance.py` patch targets updated to the new homes (e.g. `sase.sudo.ssh_detached.REMOTE_POLL_SECONDS`).
- Verified: `just check` passes (all lint gates + scoped tests), and the targeted suites pass — 52 tests across `test_sudo_ssh`, `test_sudo_detach`, `test_sudo_acceptance`.

One known tradeoff: anyone importing the old private names from `sase.sudo.ssh` (e.g. `_run_ssh`) will need to import the public name from the owning submodule instead.
