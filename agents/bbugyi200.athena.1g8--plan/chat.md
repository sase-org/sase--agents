# Chat History - ace-run (1g8--plan)

- **TIMESTAMP:** 2026-11-25 16:40:09 EST
- **MODEL:** claude/opus
- **AGENT:** 1g8--plan

**Plan:** /home/bryan/.sase/plans/202611/fix_sase_telegram_ci_display_seam.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/fix_sase_telegram_ci_display_seam.md`

> # Plan: Fix sase-telegram CI by retargeting the stale project-display test seam
> ## Problem
> Every `CI` run on `sase-org/sase-telegram` master since 2026-11-20 (commits `60a94ab`,
> `ceffb63`, `bffd4f6`, `4f2939f`, plus release-please PR #41 for 0.4.30) fails in the
> `Run tests` step. Lint passes. Each run shows the same 4 setup errors and no assertion
> failures (e.g. `881 passed, 4 errors`):
> ```
> ERROR tests/test_formatting.py::TestBuildForkCopyText::test_tag_prompt_renders_tag_form
> ERROR tests/test_inbound.py::TestBeadProjectContext::test_extract_project_from_tag_prompt
> ERROR tests/test_inbound.py::TestBeadProjectContext::test_records_project_context_for_tag_prompt

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase GitHub Actions is failing for the sase-telegram repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'll start by running `actstat` to see the failing jobs.

Let me load the planning and repo skills, then pull the job logs.

All four failed runs' logs are downloaded. Next I'll go through the test failures.

Now the current sase-side module, to see what replaced `_project_display_name_map_cached`:

The module is now a thin facade (commit `19f497f82d` split it into private modules). Next I'll check where the cached map lives now and how the humanizer reads it.

The sase workspace venv's `sase_core_rs` isn't built, so it can't be used. I'll check whether the globally installed `sase` tool env has a working core binding and the post-split modules.

First I'll reproduce the CI errors on the unmodified export:

`-I` drops PYTHONPATH, and this is the user's own code, so I'll run without it:

That reproduces CI exactly. Now I'll apply the candidate fix to the `/tmp` copy only and rerun:

All 19 pass with the retargeted seam. Now the full suite on the patched copy, to check nothing else is hiding behind these four errors:

Lint is clean too. Before writing the plan, I'll check whether to consolidate the duplicated fixture, and look for other private sase seams the tests patch.

Validation needs `title`/`goal` and shorter decision text. Fixing those:

Validation passes. Proposing the plan:

The proposal is staged. I'll clean up the scratch verification dir (outside any repo) and then finish through `/sase_final`.

I found the cause and submitted a fix plan for your review. Nothing in either repo has been changed yet; the work starts after you approve.

**What's failing:** Every CI run on sase-telegram master since Nov 20 fails at the "Run tests" step with the same 4 errors (lint passes). That covers the last four commits plus the open release PR #41 for 0.4.30. The other Python version's job in each run was just cancelled when the first one failed.
```
AttributeError: <module 'sase.project_display_names'> does not have the attribute '_project_display_name_map_cached'
```

**Root cause:**
- **The break:** On Nov 6, sase commit `19f497f82d` split `sase.project_display_names` into private `_project_display_*` modules and removed `_project_display_name_map_cached`. That commit updated sase's own tests, but sase-telegram has two copies of a `_fake_tag_catalog` test fixture (in `tests/test_formatting.py` and `tests/test_inbound.py`) that still patch the old name. The plugin's actual source code only uses public names and is unaffected.
- **Why nobody noticed for two weeks:** sase-telegram CI runs against whatever sase master looks like at the time, and only when sase-telegram itself gets a push. There were no pushes between Oct 19 (green) and Nov 20, so the first push after the split was the first run to go red.

**Verified fix:** I reproduced the 4 errors on a temporary copy of sase-telegram, set up outside the repo, against current sase. Pointing the patch at `sase._project_display_labels.cached_project_display_snapshot` fixed them:
- the 19 tests in the two affected classes pass;
- the full suite passes (885 tests);
- `ruff` is clean on the edited files.

Patching the public `sase.project_display_names` module instead would not work, because the label helpers keep their own reference to that function. I ran this in a local Python 3.14 environment rather than CI's 3.12/3.13, but the error has nothing to do with the Python version.

**The plan** (a small single-agent plan, all changes in sase-telegram):
1. Replace the two copied fixtures with one shared `_fake_tag_catalog` fixture in `tests/conftest.py` using the new patch target. It keeps the same name, so no test signatures change, and the next move on the sase side only needs fixing in one place.
2. Delete the two local copies.
3. Run `just install-venv`, the targeted tests, then `sase tool run check`.

**One decision for you (`drift_watch`):** add a daily scheduled run plus a manual "run workflow" button to `.github/workflows/ci.yml`, so future sase changes that break the plugin show up within a day. It costs nothing because the repo is public, but scheduled failures will send you email. It defaults to **daily**; choose `skip` to leave the CI file alone.

Once the fix lands on master, CI there should go green, and release-please will update PR #41, which re-runs its CI.
