# Chat History - ace-run (1gd--plan)

- **TIMESTAMP:** 2026-11-26 05:44:48 EST
- **MODEL:** claude/opus
- **AGENT:** 1gd--plan
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261126_053230.md`

**Plan:** /home/bryan/.sase/plans/202611/fix_sase_github_ci_tests.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/fix_sase_github_ci_tests.md`

> # Fix sase-github CI: align plugin tests with sase's push-identity guard and staged handoffs
> ## Goal
> Make `sase-org/sase-github` CI green again. The work is test-only and lives entirely in
> the linked **sase-github** repo. No sase, sase-core, or sase-github `src/` changes are
> needed.
> Open the repo with `sase repo open sase-github -r "<reason>"` and work only in the
> printed path. Read its `CLAUDE.md` first.
> ## Diagnosis (already done; do not re-derive)
> `actstat` shows `sase-org/sase-github` CI run #163 (push of `5f85ceb` to `master`):
> - `test (3.12)` failed at "Run tests".

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase GitHub Actions is failing for the sase-github repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm pulling the failing job logs for sase-github CI run #163. The 3.12 test job failed at "Run tests".

Reproducing locally next: I'm checking whether the sase workspace venv can run the sase-github tests against current sase master.

Same 7 failures reproduce locally against current sase master. Next I'm reading the plugin's mail and PR code, plus the tests.

Now the failing tests and the `_MOCK_TARGET` they patch:

Let me print what `error` actually is in these failing cases:

Root cause emerging: sase's command runner now has a Git mutation guard that runs `git rev-parse --show-toplevel` before mutating git commands. I'm locating it in sase.

The guard comes from sase commit a14bffcdbf (2026-11-10, "guard Git mutations and pushes by checkout identity"). I'm checking `push_guard` and how sase's own tests adapted to it.

Let me confirm the proposed test fix works before planning: a fake that answers the identity probes, the way sase's own tests do.

With SASE_HOME isolated, the flow is hermetic and only 2 probe calls are added. Now I'm reading the full bodies of the 6 failing plugin tests to see which assertions depend on call order or count.

Only the test references the retired marker. Quick check that staging a real handoff makes `gh_release` skip:

Both fixes are confirmed in probes. Next I'm loading the planning skill and the decisions roster (required before writing a plan).

The roster points to `guarded-recipes` (sase-github's `just check` is guarded), `check-full-is-explicit`, and `ci-two-speed-split`. I'm reading those to cite them correctly.

Lint is clean against sase master, so the 7 test failures are the whole problem. Quick check for an existing bead covering this:

No related beads exist. One last probe before writing the plan: confirming the `create_pull_request` success and failure paths behave as planned when the fake answers the identity probes.

Probes confirm the planned fakes work on both sase master and sase 0.18.1. I have everything needed, so I'm writing the plan.

Plan written. Validating it with `--explain`:

Validation needs `title` and `goal` in the frontmatter. Adding them:

Validation passes. Submitting the plan:

Staged. Cleaning up my scratch files in /tmp, then finishing through `/sase_final`.

I found why sase-github's CI is failing and submitted a fix plan, `sase_plan_fix_sase_github_ci_tests.md`, as a small tale. It's waiting for your approval and no files have been changed yet. Nothing was committed this turn because nothing needed committing.

**What `actstat` shows:** the last CI run on sase-github `master` (#163, commit `5f85ceb`, from Nov 13) failed in the `test (3.12)` job, and `test (3.13)` was cancelled because of it. Lint passed. The open release PR #33 (release 0.2.25) is failing for the same reason. The scheduled "Release dependency floor" runs are all green and unrelated.

**Root cause:** sase-github's CI builds and tests against sase `master`, not a released sase. Two intentional sase changes (both in the v0.19.0 tag) broke 7 tests. The plugin code itself is fine.
- **New push safety check (6 tests in `tests/test_github_plugin.py`):** since sase commit `a14bffcdbf`, every `git push` first checks that the folder is a real git checkout with an origin. The tests fake all subprocess calls with a fixed list of answers, so the check uses up those answers or gets an empty one. It then refuses the push, and the mail and pull-request tests fail with "git push failed".
- **Handoff signal changed (1 test, `test_gh_release_step_skips_on_handoff` in `tests/test_gh_workspace_claims.py`):** since sase commit `d3518e567d`, a handoff is detected from a staged handoff record, not the old `.sase_monitor_pending` marker file. The test still writes the old marker, so the workspace gets released and it sees `released=true`.

**How I confirmed it:**
- **Failures reproduce:** running the suite against current sase master gives exactly the same 7 failures.
- **Older sase passes:** against sase 0.18.1, the latest on PyPI, all 355 tests pass.
- **Lint is clean:** ruff and mypy pass against sase master.
- **Fixes work:** I tried each fix in a throwaway script against both sase master and 0.18.1, and each behaved as planned.

**What the plan does** (test-only, two files, all in sase-github):
- **Fake the safety check:** the subprocess fakes answer its checks, and the tests point `SASE_HOME` at an empty temp folder. Without that, the check reads your real repo list, so the tests depend on the machine they run on.
- **Order-independent assertions:** the tests assert on the plugin's own commands, ignoring the safety check's.
- **Stage a real handoff:** the handoff test creates an actual staged handoff record, the same way sase's own test does.
- **Two misleading tests fixed:** `test_direct_mail_push_fails` now passes only because the safety check refuses first. `test_vcs_create_pull_request_pr_create_fails` was already stopping at "No staged changes" before it got near a pull request. Both get rewritten to test what their names say.

**Older sase still works:** sase v0.19.0 is tagged but isn't on PyPI yet, and a default local setup of sase-github installs 0.18.1. The rewritten tests still pass there. The handoff test is skipped on 0.18.1, because the module it needs only exists from 0.19.0.

After the fix lands on sase-github `master`, CI should go green and PR #33's checks will re-run. You can confirm with `actstat`.
