#gh:gh_sase-org__sase #fork:01d Something still isn't working right (see the command output below for context). Can you help me diagnose the root cause of this issue and fix it? #plan %m:@xlarge
```
❯ sase bead work x7 -Y
Epic sase-x7 is already ready; retrying remaining non-closed phases.
Epic sase-x7 — Canonical-only SASE across athena, mac, and apollo: 11 phase agent(s) in 10 wave(s) plus 1 land agent (sase-x7.land).
  Clan: sase-x7 · Tribe: @epic
  Wave 0: sase-x7.4 → sase-x7.4
  Wave 1: sase-x7.5 → sase-x7.5, sase-x7.7 → sase-x7.7
  Wave 2: sase-x7.8 → sase-x7.8
  Wave 3: sase-x7.9 → sase-x7.9
  Wave 4: sase-x7.10 → sase-x7.10
  Wave 5: sase-x7.11 → sase-x7.11
  Wave 6: sase-x7.12 → sase-x7.12
  Wave 7: sase-x7.13 → sase-x7.13
  Wave 8: sase-x7.14 → sase-x7.14
  Wave 9: sase-x7.15 → sase-x7.15
  Land waits on: sase-x7.4, sase-x7.5, sase-x7.7, sase-x7.8, sase-x7.9, sase-x7.10, sase-x7.11, sase-x7.12, sase-x7.13, sase-x7.14, sase-x7.15

Existing agents for epic sase-x7:
  REMOVE   (FAILED) sase-x7.4 bead=sase-x7.4  for bead sase-x7.4 at /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/06/20260906221416
Traceback (most recent call last):
  File "/home/bryan/.local/bin/sase", line 10, in <module>
    sys.exit(main())
             ~~~~^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/entry.py", line 165, in main
    handler(args)
    ~~~~~~~^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_handler.py", line 157, in handle_bead_work
    dispatch_bead_work(args, timer_factory=make_bead_work_timer)
    ~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_entry.py", line 42, in handle_bead_work
    _handle_bead_work_locked(
    ~~~~~~~~~~~~~~~~~~~~~~~~^
        args,
        ^^^^^
    ...<5 lines>...
        correlation_id=correlation_id,
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    )
    ^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_entry.py", line 336, in _handle_bead_work_locked
    launched = cli_work_handler.launch_epic_bead_work(
        proj,
    ...<6 lines>...
        extra_waits=extra_waits,
    )
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_handler.py", line 412, in launch_epic_bead_work
    query = prepare_selected_bead_work_force_reuse(
        query,
    ...<2 lines>...
        timer=timer,
    )
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_cleanup_apply.py", line 72, in prepare_selected_bead_work_force_reuse
    _verify_cleanup_target_still_selected(
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^
        target,
        ^^^^^^^
    ...<2 lines>...
        timer=timer,
        ^^^^^^^^^^^^
    )
    ^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_cleanup_apply.py", line 175, in _verify_cleanup_target_still_selected
    matching = _fresh_cleanup_target(target, slot=slot, bead_assignees=bead_assignees)
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_work_cleanup_apply.py", line 212, in _fresh_cleanup_target
    return classify_artifact_record(
        slot,
    ...<4 lines>...
        identity=AgentIdentitySnapshot.current(),
    )
TypeError: classify_artifact_record() got an unexpected keyword argument 'identity'
```