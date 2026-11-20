# Chat History - ace-run (toobig-aa.test_checks_agent_publication.0)

- **TIMESTAMP:** 2026-11-20 07:24:24 EST
- **MODEL:** claude/opus
- **AGENT:** toobig-aa.test_checks_agent_publication.0

## Prompt

%id(test_checks_agent_publication.0, clan=toobig-aa)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/doctor/test_checks_agent_publication.py` file into multiple files? Use your best
%wait:toobig-aa.test_commit_publication_bounded_drain.0
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

I'm reviewing the repo's split conventions and the required lint/test memory notes before making the split.

Now verifying the split is faithful: every original test is present once, with bodies identical modulo the helper renames.

All 12 tests pass across the three modules. Now the three requested lint gates, individually.

The read log shows epic `sase-1tz.2.1` agents were already looking into the `OutboxGroup` finding. I'll check whether that epic owns it before filing anything.

I split `tests/doctor/test_checks_agent_publication.py` (705 lines) into four files, each well under 500 lines. All 12 tests pass, mypy and toobig are clean, and `sase tool run check` found no new failures. symvision and the overall check still exit red on one issue that was already on master.

| File | Lines | Contents |
|---|---|---|
| `tests/doctor/_checks_agent_publication_helpers.py` | 88 | Shared helpers, renamed to public names: `doctor_context`, `make_record`, `make_item`, `write_outbox` |
| `tests/doctor/test_checks_agent_publication.py` | 302 | Core outbox states: clean, quarantined/stalled, dropped obsolete, retired, and both settled-terminal tests |
| `tests/doctor/test_checks_agent_publication_groups.py` | 207 | Grouping failures by cause, standing alerts, and the unreadable standing-alert store |
| `tests/doctor/test_checks_agent_publication_sidecar.py` | 151 | Unreadable vs. healthy owner manifest, and the parked diverged-replay warning |

- **Behavior:** a script compared the old and new code. Every test and helper is the same as before apart from the helper renames, and each test exists exactly once. All monkeypatch targets are the same `sase.doctor.*` paths, so nothing needed retargeting.
- **Import path:** `tests.doctor.test_checks_agent_publication` still exists and holds the core tests. I didn't re-export the moved tests from it, because pytest would then collect them twice. Nothing in the repo imports from this module. This matches how the last two test splits in the repo were done.
- **Private names:** no `_`-prefixed name is imported between the new modules. The tests still import two private helpers from `src` (`_outbox_signature_for` and `_write_diverged_replay_marker`), exactly as the original file did.

**Checks:**
- `just _lint-mypy`: passes.
- `just _lint-toobig`: passes. Every file under `tests/` is now below the 700-line info threshold; the original file was above it.
- `just _lint-symvision`: fails on one issue already on master. It reports `OutboxGroup` in `src/sase/doctor/_agent_publication.py` as unused public code, and symvision only scans `src/sase`, which the split didn't touch.
- `sase tool run check`: exits 1 on that same symvision issue. Triage labels it KNOWN with no owner, its verdict is `no_new_failures`, and the 92 test files it picked for this change passed.

The `OutboxGroup` issue was introduced by epic `sase-1tz.2.1`, which already tracks it, so I added a corroborating note there instead of filing a duplicate task. The fix is to make the class private (`_OutboxGroup`).

The split will be committed automatically when this turn ends, as `test(doctor): split agent publication outbox tests into focused modules`.
