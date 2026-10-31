# Chat History - ace-run (toobig-8y.test_deck_view_main_pilot.0)

- **TIMESTAMP:** 2026-10-31 13:28:13 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8y.test_deck_view_main_pilot.0

## Prompt

%auto
%id(test_deck_view_main_pilot.0, clan=toobig-8y)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py` file into multiple files? Use your best
%wait:toobig-8y.index_queries.0
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

Done. The 745-line [test_deck_view_main_pilot.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py) is now four files, all under 500 lines:

- [_deck_view_main_support.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/_deck_view_main_support.py) (130 lines): shared fixtures with public names — `MainDetailApp`, `make_reply_card`, `make_document`, `pin_settings`, `get_panel`, `settle_view`. Single-use helpers (`_meta`, `_block`) stayed private inside it.
- [_deck_view_main_transitions_tests.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/_deck_view_main_transitions_tests.py) (244 lines): 6 transition/offset/pin tests plus the helpers only they use (`_scroll`, `_following`, `_anchor_on_b1`, `_expected_row`, `_STARTS`, `_TRANSITIONS`), kept private in-file.
- [_deck_view_main_policy_tests.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/_deck_view_main_policy_tests.py) (413 lines): the other 10 policy/persistence/cycle tests.
- [test_deck_view_main_pilot.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py) (53 lines): facade re-exporting all public names and all 16 test functions (`X as X`), no `_private` names. No `_`-prefixed name is imported across the new modules.

One retarget was required: [test_deck_context_landing.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/decks/test_deck_context_landing.py) imported `_document`/`_reply_card` from the old module. It now imports `make_document`/`make_reply_card` from the support module. Monkeypatch targets were unaffected (they patch instance attributes, plus a `src`-local `_badge_variants` import preserved verbatim).

Verification, all observed:

- `just _lint-symvision`: pass ("All public/private classes/functions are used properly!")
- `just _lint-mypy`: pass ("Success: no issues found in 6283 source files")
- `just _lint-toobig`: pass (only pre-existing warnings in untouched files)
- Facade collects the same 23 test cases; direct run of the facade plus the retargeted file: 31 passed
- `sase tool run check`: succeeded, exit 0 (all lint stages, SASE validation, and the 91-file scoped test lane green)

Declared the test split for host commit.
