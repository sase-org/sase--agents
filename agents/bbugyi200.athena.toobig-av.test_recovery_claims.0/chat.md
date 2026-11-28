# Chat History - ace-run (toobig-av.test_recovery_claims.0)

- **TIMESTAMP:** 2026-11-28 07:24:11 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-av.test_recovery_claims.0

## Prompt

%id:toobig-av.test_recovery_claims.0
%clan(toobig-av, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 722  tests/test_bead/test_recovery_claims.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_bead/test_recovery_claims.py` file into multiple files? Use your best
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

I'll split `tests/test_bead/test_recovery_claims.py` into modules of 500 lines or fewer, then lint and check. First I'll read the split conventions, the current file, and the relevant SASE notes.

I'll load the lint/symvision notes and inspect the recovery_claims test plus nearby split patterns.

The file is 722 lines, so I’ll inspect its structure and nearby split examples before cutting it.

I'll look at recent toobig splits and how facades re-export public names.

I have the local split pattern: a `__test__ = False` facade, shared public helpers in a `_`-prefixed module, and focused test files. Next I’ll write those files.

I'll move the `threading` import to module level and confirm each new file stays under 500 lines.

I'll rename the fixture function so it no longer collides with the `fake_core` parameter, matching the attachment-fetch pattern.

The first two lints raced on venv setup; I’ll wait for mypy, then rerun the failed gates one at a time.

All three lint gates passed. Next I’ll run the split tests, then `sase tool run check`.

Check failed on one NEW scoped test. I’ll inspect that failure and see whether the split caused it.

The inner tests passed; a sibling xdist worker left a temp directory and tripped the leak guard. I’ll confirm that in isolation and inspect the named owner bead.

The isolated re-run passed. I’ll file this as discovered flake work if it isn’t already tracked, then finalize the split.

Split `tests/test_bead/test_recovery_claims.py` (722 lines) into four modules, each under 500 lines, and kept the original public import path.

**Layout**
- `test_recovery_claims.py` — non-collected facade (`__test__ = False`) that re-exports public names
- `_recovery_claims_helpers.py` (264) — `FakeRecoveryCore`, `claim_key`, `claim_request`, and the `fake_core` fixture as `recovery_fake_core`
- `test_recovery_claims_publication.py` (297) — in-store activation and claim tests
- `test_recovery_claims_checkouts.py` (208) — competing-checkout tests, with git helpers kept private in that file

Shared helpers live as public names in the already-private helpers module. Checkout git helpers stay in the only consumer. Monkeypatch targets still point at `sase.bead.recovery` and `sase.bead.background_store`.

**Verification**
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed
- The 10 split tests passed
- `sase tool run check` failed on an unrelated NEW flake: `test_header_resolver_late_read_does_not_poison_leak_snapshot`. The inner tests passed; a sibling xdist worker left `release-watch-abandon-*` in the shared temp root. Isolated rerun passed. Filed as `sase-1vz` (did not +1 `sase-1vl`; that bead is 60s timeouts on different nodes).
