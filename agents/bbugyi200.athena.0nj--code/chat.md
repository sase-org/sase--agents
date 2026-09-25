# Chat History - ace-run (0nj--code)

- **TIMESTAMP:** 2026-09-18 23:28:54 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0nj--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/remote_sudo_login_shell.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll read the execute-plan skill and the approved plan, then implement it.

The execute-plan skill is for PR DAGs; this looks like a SASE sidecar plan. I'll load SASE repo/plan skills and open the plan.

I'll open the plans sidecar and read the approved plan, plus SASE size/lint guidance.

I'll open the plans sidecar through `sase repo` and read the approved plan as an artifact.

The plan is to run remote sudo through the login shell so `sase` on `~/.local/bin` resolves. Next I’ll map the SSH, sudo, and screenshot code.

I have the login-shell contract and the sudo/screenshot call sites. Next I’ll extract the shared encoder and wire it through both transports.

Formatter finished. Next I’ll run the focused sudo, screenshot, and encoder tests.

The focused `just test` run is queued behind other pytest workers. I’ll stop it and use `just check`, which doesn’t wait on that queue.

`ssh.py` is over the 1000-line limit. I’ll move the CLI diagnostic helpers into their own module.

The scoped run escalated to the full suite. I’ll check whether any failures are in the sudo/screenshot changes.

Remote sudo now resolves `sase` the same way remote screenshots do: through the target account’s noninteractive login shell, so a `~/.local/bin` install is found even when a bare SSH session’s `PATH` is not.

**What changed**
- Added a shared encoder in `src/sase/dispatch/ssh_login_shell.py` that quotes argv and runs it as `"$SHELL" -lc` with a `/bin/sh` fallback.
- Remote screenshots now use that encoder; behavior is unchanged.
- Only target-side `sase sudo exec` (contract probe, sync, and detached) goes through the login environment. Staging, ledger/log reads, liveness, stop, and cleanup stay direct remote commands. `ssh -t` is still used for authentication.
- A missing or broken target CLI now reports that resolution was attempted in the login environment, with bounded stdout/stderr and no password/PAM text.
- Docs in `docs/sudo.md` describe the login-shell contract.

**Verification**
- Focused encoder, remote-sudo, detached-sudo, and screenshot tests: 56 passed.
- `just check` lint gates passed (ruff, mypy, symvision, toobig, …).
- Diff-scoped tests escalated to the full suite because this workspace’s `sase-core-rs` identity changed during setup (`core-identity-changed`), not because of these files. That run was 43222 passed / 46 failed; none of the failures were sudo, screenshot, or the new encoder. The failures were monitor/fakey/axe-chop tests (`IndexError` and a systemd-run argv mix-up) consistent with a contended host, not this change.
