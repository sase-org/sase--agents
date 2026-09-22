# Chat History - ace-run (0pj--code)

- **TIMESTAMP:** 2026-09-22 17:01:43 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0pj--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0pj__plan-260922_154615.md`
- **2. --code** — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0pj__code-260922_154615.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202609/rename_research_swarm_image_input.md

The above plan has been reviewed and approved. Implement it now.


## Response

Rename edits are in place in both repos; formatter and check runs are still going — I'll report verification once they land.

The sase-side test now passes against the renamed plugin. The single wheel-test rerun is still going — I'll dig into its result when it lands.

Count fix applied to the wheel smoke and its CI mirror — the rerun will confirm the full lane.

Smoke isolation applied — rerunning the wheel test to confirm the full lane goes green.

Lint and final name-sweep running — then the full wheel lane.

Diffs verified — waiting on the full wheel lane for the final verdict.

Done — the rename is implemented in both repos and verified, and the final declaration is submitted (both repos commit).

What changed:
- `sase-research-artifacts`: `should_generate_image` → `image` in [research_swarm.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/linked/sase-research-artifacts/src/sase_research_artifacts/xprompts/research_swarm.md) (input list + image segment guard), plus matching updates in `test_xprompt_loading.py`, `test_wheel_contract.py`, `docs/xprompts.md` (table kept aligned), and `README.md`. No alias/shim, per plan.
- `sase`: three `image=true` callers in [test_runner_slots_e2e.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/tests/fakey/test_runner_slots_e2e.py:285).
- `chezmoi`, `sase-core`: no references found, unchanged.

Verification: plugin `just check` 79 passed; `just test-wheel` 4 passed; sase target test passes against the renamed plugin; `should_generate_image` returns nothing repo-wide.

Two things worth knowing:
- The plan's `just test-wheel` step was red for reasons outside the rename: the wheel smoke still asserted 4 authored `%q(w=0.25` segments (the template has had 8 since the grok/muse/gemini/critique additions), and the smoke inherited machine-wide provider disables (codex is hard-disabled on this machine), making segment counts nondeterministic. I fixed the count to 8 in the smoke and its `publish.yml` mirror, and gave the smoke an isolated `SASE_HOME` mirroring the fast suite's existing fixture. Test-only changes; behavior is identical where no disables exist.
- The plan assumed the sase venv has PyPI plugin 0.2.0; here the venv resolves the plugin to the local linked checkout, so the sase test exercises the new code directly (and passes). Also, sase `just check` fails on a pre-existing `symvision` finding in two files I didn't touch — every recorded run shows the same failure, so it's unrelated to this change.

Commit messages declared: `feat(research-swarm): rename should_generate_image input to image` (plugin, non-breaking as the plan directed) and `test(fakey): use renamed research_swarm image input` (sase).
