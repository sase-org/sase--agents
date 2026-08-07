#gh:gh_sase-org__sase The `just test` command is failing (see the command output below for context). Can you help me diagnose the root cause of this issue and fix it? #plan #m_opus 
```
============================================================================= short test summary info ==============================================================================
FAILED tests/test_notification_modal_tags.py::test_a_gate_declared_panel_icon_reaches_the_classified_tab - AssertionError: assert [('deployments', None)] == [('deployments', '🚀')]
FAILED tests/test_bead/test_snooze_gate.py::test_bead_snooze_gate_preview_carries_the_real_snooze_note - AssertionError: assert '## Notes' in '> [!NOTE] **◈ Snoozed by `@bryanbugyi34@gmail.com` on 2026-08-07 15:59:14 EDT**\n>\n> **Wakes:** 2026-08-09 09:00:00 ..._preview_0-1 — Fo...
FAILED tests/test_bead/test_snooze_lifecycle.py::test_snooze_round_trips_through_every_persistence_surface - AssertionError: assert False
FAILED tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget - AssertionError: contract set normalized to 31.0s of reference CPU, over the 30s budget
FAILED tests/test_bead/test_cli_snooze.py::test_snooze_leaves_one_note_naming_wake_time_length_target_and_reason - AssertionError: assert False
FAILED tests/test_bead/test_cli_snooze.py::test_bare_snooze_with_no_reason_or_target_still_leaves_a_note - AssertionError: assert '' == '[2026-08-06T...4:00 (in 3d).'
FAILED tests/test_bead/test_cli_snooze.py::test_re_snoozing_appends_a_second_note_naming_the_replaced_wake_time - AssertionError: assert 1 == 2
FAILED tests/test_bead/test_cli_snooze.py::test_a_multiline_reason_collapses_to_one_note_but_keeps_the_raw_reason - AssertionError: assert 'Reason: line one line two' in ''
======================================================= 8 failed, 27056 passed, 7 skipped, 69 warnings in 179.11s (0:02:59) ========================================================
```