# Chat History - ace-run (sase-gg.4)

- **TIMESTAMP:** 2026-08-06 12:37:46 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-gg.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-gg, bead=sase-gg.4)
%model:@small_phase_worker
%auto
Can you complete the work for bead sase-gg.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gg.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gg.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

This phase fixes the root cause in the sibling `sase-core` repo: the maturin-generated `sase_core_rs/__init__.py` template relies on an importlib side effect to bind the submodule name, which breaks on re-import. Let me open that repo properly.

Now update `pyproject.toml` to point maturin at this explicit package source instead of the auto-generated template.

Network access works. Let's build the wheel and reproduce the fix.

Build is running in the background (Rust compile). I'll wait for it to finish.

I'll wait for the maturin build to finish.

The wheel built successfully. Now let's verify the fix reproduces correctly against the reported failure — install into a fresh venv and reproduce the exact re-import scenario from the plan.

Python 3.12 is available. Let's rebuild the venv with it.

Now the critical check — reproduce the exact re-import failure from the plan (evict the parent package while the compiled submodule stays cached).

Let's confirm this genuinely fixes a real defect by reproducing the bug against the currently-published (unfixed) wheel already installed in the sase workspace.

Confirmed: the currently-published wheel reproduces the exact `NameError` from the plan, and my fix — verified against a freshly built wheel from the same source tag — eliminates it. Now let's commit the fix in the sase-core repo and open a PR following its normal workflow.

No doc updates needed — this section doesn't describe the `__init__.py` internals. Let's run `cargo fmt`/`clippy`/`test` quickly as a sanity check (should be unaffected since no Rust code changed), then commit.

Now let's push the branch and open a PR.

PR opened: https://github.com/sase-org/sase-core/pull/89. Now let's record a follow-up suggestion (the wheel-smoke CI doesn't test this re-import scenario) and close the bead.

Bead `sase-gg.4` is closed. Summary:

- **Fix**: In the sibling `sase-core` repo, added an explicit `crates/sase_core_py/python/sase_core_rs/__init__.py` that binds the compiled submodule by name (`from . import sase_core_rs`) before re-exporting it, wired in via `python-source = "python"` in `pyproject.toml`. This replaces maturin's auto-generated star-import template, which relied on an importlib `setattr` side effect that's skipped on re-import once the submodule is already cached.
- **Verified**: Built the wheel with `maturin build --release`, installed it in a fresh Python 3.12 venv, and reproduced the plan's exact repro (`del sys.modules['sase_core_rs']` → re-import) — it now succeeds, whereas the currently-published wheel (already installed in this workspace) still raises `NameError` under the same steps, confirming the defect and the fix.
- **Shipped as a PR**, not a direct push/merge: [sase-core#89](https://github.com/sase-org/sase-core/pull/89) — merging triggers `release-plz`'s automated PyPI publish, which I left for review rather than doing unilaterally.
- **Follow-up filed** on the bead: sase-core's wheel-smoke CI never exercises the re-import path, so it wouldn't have caught this; proposed adding that check.

This unblocks `sase-gg.5` (verify), which is also `in_progress` and blocked on this phase.
