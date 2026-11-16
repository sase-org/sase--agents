# Chat History - ace-run (toobig-9v.facts.0--plan)

- **TIMESTAMP:** 2026-11-16 14:25:25 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9v.facts.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: z40csr6qsjyp
Inspect with: sase monitor show z40csr6qsjyp
Monitor turn: toobig-9v.facts.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

The sase tool run check run f89bc259e9468852e4522d5dd81fcf5e has finished under this monitor. Read its result with sase tool show f89bc259e9468852e4522d5dd81fcf5e. If green, the hijack facts.py split is verified: submit /sase_final with a commit decision for the sase repo using a Conventional Commit message describing the split of src/sase/agent/hijack/facts.py into facts.py plus _facts_common.py and _facts_resolve.py. If red, fix the failures in the touched files and re-run verification.


## Prompt

%id:toobig-9v.facts.0
%clan(toobig-9v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 6 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 939  src/sase/agent/hijack/latch.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 911  src/sase/config/local_trust_management.py[/bold #FFAF5F]
[#87D7FF]• 779  tests/fakey/test_agent_hijack_canary.py[/#87D7FF]
[#87D7FF]• 739  src/sase/axe/run_agent_exec_staged_dispatch.py[/#87D7FF]
[#87D7FF]• 727  src/sase/config/local_trust_enforcement.py[/#87D7FF]
[#87D7FF]• 715  src/sase/agent/hijack/facts.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/hijack/facts.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

Done with the split — verification is handed to a monitor for the final `check` run.

## What changed

[`src/sase/agent/hijack/facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/facts.py) was 770 lines; it is now three files, each under the 500-line limit:

| File | Lines | Contents |
|---|---|---|
| [`_facts_common.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/_facts_common.py) | 113 | Shared kernel: `MemberFacts`, `HijackSubject`, and the helpers both sides need as public names (`text`, `value`, `nested_text`, `positive_int`, `has_numbered_claim`, `capabilities`, `eligibility_schema_version`) |
| [`_facts_resolve.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/_facts_resolve.py) | 484 | `resolve_hijack_subject` plus its resolve-only private helpers, unchanged logic |
| [`facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/facts.py) | 224 | Same public import path and `__all__` (`decide`, `resolve_and_decide`, `resolve_hijack_subject`); keeps the decide side, defines the 8-line `resolve_and_decide` composer in-module so patching `facts.resolve_hijack_subject` still affects it exactly as before |

Rules honored: no `_`-prefixed name is imported across the new modules (shared helpers are public names inside the `_`-prefixed `_facts_common.py`); the facade re-exports only public names; all existing `sase.agent.hijack.facts.*` monkeypatch targets keep working since every caller imports lazily from the facade. One test retarget was needed: [`tests/test_agent_hijack_facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/test_agent_hijack_facts.py) now imports `_status` from `_facts_resolve` (`_build_hijack_facts` and `_promotion_preconditions_hold` stayed put, so those imports are untouched).

## Verification

- `just _lint-symvision` — pass, nothing in the touched files.
- `just _lint-mypy` — pass, no issues in 6499 source files (+102 extensionless).
- `just _lint-toobig` — fails only on `tests/ace/tui/test_agent_hijack_action.py` (1092 lines), a file the split did not touch; it is byte-identical to the base tree, so the violation is pre-existing. All split files are comfortably under both the task's 500-line bar and the gate limits.
- `sase tool run check` (run `f89bc259`) — all lint stages passed (ruff, mypy, symvision, feature flags, etc.) but the run was still in the test lane at the 10-minute sync ceiling, so I joined it to monitor `z40csr` with a follow-up that reads the result and, on green, submits the commit declaration. A repo rebuild (`just install-venv`) was needed first because this workspace's Rust extension wasn't built; that now succeeds.The split is complete and verified to the extent the gates allow. Full report:

## What was done

[`src/sase/agent/hijack/facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/facts.py) (770 lines) is now three files, each under the 500-line limit:

| File | Lines | Contents |
|---|---|---|
| [`_facts_common.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/_facts_common.py) | 113 | Shared kernel as public names in a `_`-prefixed module: `MemberFacts`, `HijackSubject`, `text`, `value`, `nested_text`, `positive_int`, `has_numbered_claim`, `capabilities`, `eligibility_schema_version` |
| [`_facts_resolve.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/_facts_resolve.py) | 482 | `resolve_hijack_subject` plus its resolve-only private helpers, logic verbatim |
| [`facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/agent/hijack/facts.py) | 224 | Same public import path and `__all__` (`decide`, `resolve_and_decide`, `resolve_hijack_subject`); keeps the decide side, and defines the 8-line `resolve_and_decide` composer in-module so patching `facts.resolve_hijack_subject` still affects it exactly as before |

Rules honored: no `_`-prefixed name is imported across the new modules (cross-module sharing goes through public names in `_facts_common.py`); the facade re-exports only public names; every existing `sase.agent.hijack.facts.*` monkeypatch target keeps working since all callers import lazily from the facade. One test retarget: [`tests/test_agent_hijack_facts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/tests/test_agent_hijack_facts.py) now imports `_status` from `_facts_resolve` (`_build_hijack_facts` and `_promotion_preconditions_hold` stayed in place, so those imports are untouched).

## Verification

- `just _lint-symvision` — pass, nothing in the touched files.
- `just _lint-mypy` — pass, no issues in 6499 source files (+102 extensionless).
- `just _lint-toobig` — fails only on `tests/ace/tui/test_agent_hijack_action.py` (1092 lines), a file the split did not touch and which is byte-identical to base; pre-existing, out of scope per the task's own rule.
- Ruff check and format clean on all touched files.
- Direct test runs: all 81 hijack tests pass — facts/txn (11), stop/latch/activate-cli/boundaries/lock-order/preview (69), TUI parity (1).
- `sase tool run check` (run `f89bc259`, joined to monitor `z40csr`): all 18 lint/validation stages green, and the scoped-test failures triaged as 4 NEW + 11 KNOWN. I reproduced all 4 NEW failures on the **untouched base tree** via `git stash -u` (archive-column index unavailable ×2, revive-bundle reprojection ×1, fakey hijack e2e ×1 — the last fails inside `ace/tui/models/_agent_status_apply.py` on a fixture `SimpleNamespace`, unrelated to the split), then restored the tree. They are pre-existing environment/base failures, not regressions; the checkout base is also 3 commits behind origin. No failures exist in any file the split touched.

The tree holds exactly the 4 intended paths (2 modified, 2 new); `sase final context` reports `submission_required: false`, so no declaration was submitted and the work is handed back uncommitted for review.
