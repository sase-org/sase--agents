# Chat History - ace-run (sase-ha.3)

- **TIMESTAMP:** 2026-08-07 22:06:36 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ha.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-ha, bead=sase-ha.3)
%model:@medium_phase_worker
%auto
%w:sase-ha.1
%w(bead=sase-ha.1)
Can you complete the work for bead sase-ha.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-ha.3 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ha.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now let me write the code. Starting with the shared models and metadata plumbing.

Now detect.py, to read the two new install-metadata keys:

Now promote the status lookup helper in `operations.py` so the install planner can share it:

Now the history additions:

Now the core `install.py`:

Now replace the duplicated helpers with shared ones:

Now the presentation layer, `cli_install.py`:

Now the parser and dispatch:

Now update the package `__init__.py` exports:

Now a history test for the new install fields:

Now run the full lint + scoped test gate:

I'll wait for the check run to report.

While that runs, let me review the final shape of `install.py`:

While that runs, let me record the flaky-test follow-up on the bead:

I'll wait for the test lane to finish.

The work is complete. Let me close the bead:

Bead `sase-ha.3` is done and closed.

## What I built

**`src/sase/agent_clis/install.py`** — the plan/execute core:
- `fetch_install_script()` rejects non-HTTPS before the request and re-checks the URL the server actually served, so a redirect can't downgrade the transport; enforces a 1 MB cap, writes to a `0o600` file under `get_sase_managed_tmpdir("agent-clis")`, and returns the SHA-256.
- Fetching happens at **plan** time so `--dry-run` shows the digest of the exact bytes an execution would run. `plan.cleanup()` removes every fetched script, called from a `finally`.
- Execution goes through the existing shell-free `run_command` with the provider's `install_env` — never `curl | bash`. Afterwards it re-locates the binary, re-probes the version, and reports where it landed and whether that directory is on `PATH`, printing the exact `export PATH=...` line when it isn't, alongside "SASE did not edit any shell rc file."

**`src/sase/agent_clis/cli_install.py`** — Rich panel + versioned JSON envelope matching `cli_list`/`cli_update`. Exit 2 for usage errors, unknown names, and unconfirmed runs; exit 1 for failures.

**Confirmation is mandatory**: `-y|--yes`, or an interactive prompt. Non-interactive or `--json` without `--yes` prints the plan and refuses.

**Supporting changes**: registered the subcommand (metavar `{install,list,update}`, alphabetical, every long option given a short alias per `cli_rules`); added `install_dir`/`install_dir_env` install-metadata keys so the target is knowable before the run; added `AgentCliOperation` + `script_digest` so installs journal into the same durable history as updates, with old records still decoding. I promoted five existing private helpers to shared public ones rather than duplicating them.

## Verification

34 new tests plus extended detect/history/registry tests — 146 agent-CLI/provider/doctor tests green, no network. All `just check` lint gates pass (ruff, mypy, symvision, keep-sorted, toobig, changelog). Smoke-tested the npm-skip, dry-run, unknown-name, and `--help` paths live.

## Two things I did not cause

The scoped test lane surfaced 6 failures in `tests/test_gate_cli_show.py` and `tests/gate_conformance` — a `GateError` on legacy shared-input fixtures from commit a1cc172d3. I confirmed these reproduce on a clean master checkout. There was also one order-dependent flake in `test_multi_prompt_launcher_xprompt_groups.py` that passes in isolation and on a clean tree. Both are recorded as `PROPOSED FOLLOW-UP:` notes on the bead, along with a third: every `sase` invocation warns that the user-layer `research-highlights` file hook wasn't migrated with the `globs` → `path_globs` rename.

The close is published (no unpublished-commit diagnostic). Now committing.

Done.

**Bead close published.** Re-running `sase bead close sase-ha.3` reported `Already closed` with no unpublished-commit diagnostic, and added the verification note.

**Commit landed and pushed.** `85d12614e feat(agent-clis): add a confirmed, shell-free \`sase agent-cli install\`` — working tree clean, `master` in sync with `origin/master`. All 17 listed files were staged explicitly with `-f`; the rebase over the new upstream commit `050c9477c` completed automatically.

One wrinkle: the first `sase_git_commit` invocation exceeded my 2-minute command ceiling and was killed after the commit and push succeeded but before post-commit bookkeeping finished. I ran `sase_git_commit --resume`, which completed the bookkeeping (exit 0). It warned that the project has 1 quarantined agent-hood publication request, so the agent-hood link written into this commit may not resolve yet. I ran the suggested `sase agent sync --retry-quarantined`; its output is entirely pre-existing complaints about *other* agents' family lanes ("no family member run remains and v2 family containers require at least one member"), unrelated to this commit. **I could not confirm the quarantined publication actually cleared** — that's the one thing left unverified here.

**What the commit contains** (bead `sase-ha.3`): `install.py` fetches the provider-declared installer over HTTPS-only with a post-redirect URL re-check, a 1 MB cap, and a `0o600` temp file; the fetch happens at plan time so `--dry-run` shows the digest of the exact bytes that would run, with cleanup in a `finally`. Execution goes through the existing shell-free `run_command` — never `curl | bash` — then re-probes the binary and prints the `export PATH=...` line when the install directory isn't on `PATH`, without editing any rc file. Confirmation is mandatory (`-y|--yes` or an interactive prompt; non-interactive or `--json` without `--yes` refuses with exit 2). Supporting changes add the `install_dir`/`install_dir_env` metadata keys, `AgentCliOperation` + `script_digest` for durable history, and promote five shared helpers instead of duplicating them.
