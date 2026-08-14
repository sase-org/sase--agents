# Chat History - ace-run (sase-m4.6_1--mon)

- **TIMESTAMP:** 2026-08-14 17:46:06 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-m4.6_1--mon

## Prompt

sase monitor start --command 'just check-full' --reason 'Run exhaustive verification for bead sase-m4.6 after focused checks, visual suite, and just check passed'

## Response

✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✓ test cost
✗ flake baseline

┌───────────────────────────────────────────────────────┐
│                RUNNING: just selection-health         │
└───────────────────────────────────────────────────────┘
store: /home/bryan/.sase/test-selection/gh_sase-org__sase
retention: 30 days

Diff-scoped test selection health

scoped runs recorded:   961
  escalated to full:    570 (59.3%)
  median selected:      131 (5.0% of 2642)
  p90 selected:         720 (27.3% of 2642)
  median duration:      106.4s
  p75 duration:         343.9s
  p90 duration:         513.8s
  max duration:         1628.5s
full-lane runs recorded: 955

worker-seconds avoided vs. running the full suite instead: 1,156,751 (~19,279 worker-minutes, at 3,650s per full run)

broadening rules fired:
   377  context-baseline-stale
   248  context-selection
   424  contract-set-always
    92  contract-set-only
   359  core-identity-changed
     5  directory-conftest
   115  justfile
   377  no-baseline-depth-boost
    47  packaging-config
    66  rename-or-delete
    28  root-conftest
    39  selection-tooling
   209  serial-budget-exceeded
   123  src-data-asset

scoped run outcomes:
   570  escalated
    77  failed
   314  passed

scoped runs slower than the full lane (232.0s): 130 of 961
  570 escalated run(s) not counted here: cost not measured (handed off to the full lane before the runner could time it)
  20260808T145757Z-c902dd71cd07-2072264.json: 1628.5s, 612 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260814T185106Z-402b3b65ad16-910978.json: 1624.5s, 463 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260808T183332Z-92f0ff3774ca-1601237.json: 1403.8s at 4 workers, 2099 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T213747Z-3f69267d516c-2473187.json: 1372.6s, 413 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260806T212715Z-3f69267d516c-2325227.json: 1363.3s, 413 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260808T205003Z-25be8cc68334-981091.json: 1284.7s at 4 workers, 1856 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260812T172343Z-59967cc062a7-1449992.json: 1211.8s at 4 workers, 1798 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T131100Z-6b0976bcb6e5-2989628.json: 1032.6s, 494 file(s) selected, rules: context-selection, contract-set-always
  20260808T220431Z-607b72bb0d94-2728982.json: 981.5s at 4 workers, 1452 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260811T191716Z-48617f3eec9d-3870316.json: 895.7s at 4 workers, 2292 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260813T165301Z-bd6167875cc8-3068313.json: 887.6s at 4 workers, 1790 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260811T191716Z-48617f3eec9d-3876312.json: 886.8s at 4 workers, 2292 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260811T190014Z-48617f3eec9d-3525575.json: 880.0s at 4 workers, 2292 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260808T191539Z-92f0ff3774ca-2252501.json: 803.2s at 4 workers, 1893 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T055913Z-a4a340679580-1936762.json: 797.2s at 4 workers, 1939 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T140908Z-491579083016-1537050.json: 781.1s at 4 workers, 2076 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T135454Z-491579083016-1314498.json: 769.7s at 4 workers, 2076 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T162052Z-8a0fd07a062b-3005677.json: 761.3s at 4 workers, 1676 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260812T163317Z-51996c57e0ea-570331.json: 750.6s at 4 workers, 835 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T064107Z-a4a340679580-2568661.json: 738.4s at 4 workers, 1950 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T231551Z-0c971ff81078-4158910.json: 730.9s at 4 workers, 311 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T232202Z-0c971ff81078-73414.json: 726.4s at 4 workers, 494 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T062645Z-a4a340679580-2444068.json: 720.6s at 4 workers, 1950 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260812T143402Z-f14b98c08723-2414377.json: 715.9s at 4 workers, 1793 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T163053Z-6a0c35c8ec28-2880756.json: 699.5s at 4 workers, 1788 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T121341Z-1928bd79866c-3336485.json: 651.9s, 580 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260806T193546Z-25285417d045-363877.json: 626.3s, 369 file(s) selected, rules: context-selection, contract-set-always
  20260808T015114Z-47b9f0017075-2374822.json: 595.5s at 4 workers, 720 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T013813Z-47b9f0017075-2129469.json: 595.4s at 4 workers, 720 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T205503Z-64ddea98a879-3112063.json: 595.3s at 4 workers, 1097 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260809T161247Z-f5fb72438ce5-3265095.json: 578.8s at 4 workers, 976 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T232119Z-0c971ff81078-107127.json: 576.9s at 4 workers, 586 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T231754Z-0c971ff81078-53426.json: 568.5s at 4 workers, 311 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T154451Z-21633ba1bf04-2452441.json: 557.0s at 4 workers, 759 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T204304Z-15cdba4aa619-3151977.json: 540.1s at 4 workers, 903 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T010344Z-62fb94129662-4079678.json: 537.5s at 3 workers, 531 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260809T155959Z-f5fb72438ce5-2942629.json: 533.0s at 4 workers, 976 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T135456Z-1e355887f664-2801381.json: 533.0s at 4 workers, 675 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T232702Z-0c971ff81078-213123.json: 526.3s at 4 workers, 586 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T020313Z-44fa7eee2445-2768678.json: 513.8s at 4 workers, 888 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T004939Z-62fb94129662-3738755.json: 508.9s at 4 workers, 531 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260812T164321Z-51996c57e0ea-902867.json: 506.8s at 4 workers, 835 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T011752Z-62fb94129662-111047.json: 503.5s at 4 workers, 926 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260811T000128Z-62a4ddeb5feb-2800617.json: 503.2s at 4 workers, 624 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260808T002950Z-7bbd82a47ed7-999204.json: 502.6s at 4 workers, 596 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T122848Z-1928bd79866c-3480701.json: 499.8s at 4 workers, 1097 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T004057Z-7bbd82a47ed7-1168199.json: 480.4s at 4 workers, 596 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T154618Z-f5fb72438ce5-2647096.json: 475.5s at 4 workers, 976 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T031259Z-f980248c1995-4022898.json: 469.4s at 4 workers, 462 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T133231Z-6b0976bcb6e5-3484731.json: 465.7s, 94 file(s) selected, rules: context-selection, contract-set-always
  20260808T011430Z-7bbd82a47ed7-1695836.json: 463.4s at 4 workers, 581 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260811T115136Z-1e8b373625d4-1916760.json: 462.6s at 4 workers, 450 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T205049Z-15cdba4aa619-3374707.json: 458.9s at 4 workers, 903 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T233837Z-62a4ddeb5feb-2309761.json: 453.3s at 4 workers, 624 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260808T020216Z-44fa7eee2445-2770488.json: 451.7s at 4 workers, 798 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T231911Z-0c971ff81078-107115.json: 448.3s at 4 workers, 311 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260812T221155Z-526b1283b9f9-2307343.json: 445.4s at 4 workers, 971 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T235429Z-62a4ddeb5feb-2664392.json: 442.1s at 4 workers, 815 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T135920Z-6b0976bcb6e5-4173069.json: 435.8s, 94 file(s) selected, rules: context-selection, contract-set-always
  20260806T204218Z-cb1007e0900c-1967669.json: 431.6s, 133 file(s) selected, rules: context-selection, contract-set-always
  20260813T111033Z-8340b457af2d-2710370.json: 431.3s at 4 workers, 881 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T111918Z-8340b457af2d-2783795.json: 427.6s at 4 workers, 881 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T144143Z-57a045cfc6a7-3932310.json: 423.8s at 4 workers, 445 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T145054Z-57a045cfc6a7-4115013.json: 423.6s at 4 workers, 445 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T214215Z-ba77762e68fd-3984513.json: 422.7s at 4 workers, 534 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T125500Z-3e76e59fdb33-3732945.json: 418.5s at 4 workers, 503 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T135144Z-0968318b17a3-2428674.json: 417.5s at 4 workers, 219 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T154827Z-6a0c35c8ec28-2453062.json: 413.7s at 4 workers, 513 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T134717Z-6b0976bcb6e5-3915023.json: 413.1s, 94 file(s) selected, rules: context-selection, contract-set-always
  20260814T145700Z-443566f7d058-1556161.json: 413.0s, 217 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260811T121321Z-1e8b373625d4-2426687.json: 409.5s at 4 workers, 450 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T165652Z-c9b0e2958282-2864651.json: 407.4s at 4 workers, 478 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T153913Z-6a0c35c8ec28-2321043.json: 407.2s at 4 workers, 513 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T141652Z-4651ed1991a3-447950.json: 406.4s, 188 file(s) selected, rules: context-selection, contract-set-always
  20260813T125037Z-3e76e59fdb33-3700817.json: 404.5s at 4 workers, 828 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T175901Z-baebfcd21631-2840510.json: 404.0s, 517 file(s) selected, rules: context-selection, contract-set-always
  20260807T175201Z-4c7c635d2db3-4028212.json: 403.7s at 4 workers, 441 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T160455Z-6a0c35c8ec28-2701877.json: 402.1s at 4 workers, 513 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T155712Z-6a0c35c8ec28-2639453.json: 401.3s at 4 workers, 513 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T214409Z-64ddea98a879-4029568.json: 399.1s at 4 workers, 553 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T000912Z-b5872ca3ac37-56628.json: 394.9s at 4 workers, 570 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T214036Z-932277b2691a-18827.json: 392.6s at 4 workers, 369 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T034720Z-0a13ffed4da8-390991.json: 375.0s at 4 workers, 444 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T154028Z-bce09f8bf57f-2360600.json: 373.3s at 4 workers, 570 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T221036Z-932277b2691a-607772.json: 369.8s at 4 workers, 369 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T143139Z-57a045cfc6a7-3788989.json: 368.1s at 4 workers, 445 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T153233Z-bce09f8bf57f-2262128.json: 365.8s at 4 workers, 570 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T222332Z-396380c640bf-3359427.json: 360.4s at 4 workers, 502 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T181122Z-402b3b65ad16-731645.json: 359.3s at 4 workers, 294 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T020942Z-5ec9262274d8-638054.json: 356.2s at 4 workers, 418 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T172146Z-08f1b28f8477-2555919.json: 354.3s, 331 file(s) selected, rules: context-selection, contract-set-always
  20260808T223726Z-544e98a1904f-3911693.json: 353.6s at 4 workers, 420 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T021730Z-5ec9262274d8-730218.json: 353.1s at 4 workers, 418 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T191903Z-28e8ed1cebc3-1199105.json: 352.6s at 4 workers, 519 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T171805Z-e368d5756e1e-448505.json: 352.1s at 4 workers, 422 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T022432Z-e1da6d1b76fd-3354775.json: 348.0s at 4 workers, 398 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T225427Z-0c971ff81078-3854886.json: 347.4s at 4 workers, 494 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T223628Z-0c084068cfa7-3552250.json: 344.6s at 4 workers, 181 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T010750Z-62fb94129662-21300.json: 343.3s at 4 workers, 251 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260807T171355Z-c9b0e2958282-3136306.json: 342.4s at 4 workers, 372 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260811T011652Z-6385a8ebb16d-259527.json: 341.8s at 4 workers, 615 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T022439Z-5ec9262274d8-780797.json: 340.4s at 4 workers, 418 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T192223Z-5f6d8ea64f6e-1209658.json: 338.3s at 4 workers, 357 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260810T191342Z-5f6d8ea64f6e-1015554.json: 333.5s at 4 workers, 357 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T203227Z-2d054ed19903-1941572.json: 330.8s at 4 workers, 170 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260806T231553Z-96a53e7ab0d0-3719115.json: 324.7s at 4 workers, 290 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T170458Z-c9b0e2958282-3039892.json: 323.0s at 4 workers, 372 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T151549Z-0bea6801eace-642729.json: 319.7s at 4 workers, 513 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260811T012402Z-6385a8ebb16d-432547.json: 306.8s at 4 workers, 615 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T190738Z-b473a10d0989-1067870.json: 300.8s at 4 workers, 226 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T133722Z-829030f97434-324284.json: 297.0s at 4 workers, 232 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T134322Z-829030f97434-411310.json: 296.6s at 4 workers, 232 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T151955Z-7ca08ae0ef47-746361.json: 294.3s at 4 workers, 217 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T024338Z-29c137436af7-4150494.json: 292.9s at 4 workers, 579 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T184724Z-3bb9bd1d1c35-1108815.json: 285.4s at 4 workers, 172 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T151559Z-010b01a4143e-2553096.json: 279.7s at 4 workers, 176 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T212706Z-d3c5254ca8cb-2670712.json: 271.2s at 4 workers, 149 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T190151Z-ee6f3c7d302e-1440021.json: 268.1s at 4 workers, 142 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260809T121449Z-fcc9be44f2cf-2291074.json: 262.2s, 245 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260813T200008Z-1004f9eb33d6-2543617.json: 261.1s at 4 workers, 304 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260812T152146Z-2f1512c7cf52-3313851.json: 259.9s at 4 workers, 232 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T120141Z-2b64c5582926-130336.json: 258.0s at 4 workers, 412 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T120956Z-2b64c5582926-224767.json: 258.0s at 4 workers, 412 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260807T184929Z-b473a10d0989-733366.json: 254.0s at 4 workers, 338 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T032609Z-0a1502a041f4-101972.json: 253.5s at 4 workers, 372 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T171738Z-afcad43f868c-35475.json: 252.6s, 134 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260812T154504Z-2f1512c7cf52-3865204.json: 249.5s at 4 workers, 232 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260814T212109Z-d3c5254ca8cb-2632981.json: 246.4s at 4 workers, 149 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260813T205003Z-36d6dc8dd865-3439386.json: 239.9s at 4 workers, 237 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260808T203656Z-25be8cc68334-1058942.json: 238.8s at 4 workers, 179 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded

middle gear: 176 run(s) leased a bounded width, 33 refused and escalated instead
  timed runs by width: 215 at 1 worker, 4 at 3 workers, 172 at 4 workers
  the durations above pool these widths; a wide run's wall clock is not a serial one's

coverage contexts:
  runs that consulted it: 424 of 961 (537 escalated before it mattered)
  runs with a baseline:  422 of 424
  runs without one:      2 (static closure alone)
  runs on a stale one:   377
  test files contributed: 17925 (cumulative)

false negatives: 1908 (3447 scoped run/failure matches)
  matching rule: a scoped run is charged with a full-run failure only when
  both records name the same workspace, the scoped run's HEAD is an ancestor
  of the full run's, and the full run's change set covers the scoped run's.
  33 record(s) predate schema 2 (10 scoped, 23 full-lane),
  carry no workspace or change set, and are excluded from correlation.
  tests/ace/changespec/test_project_name_query.py::test_changespec_search_cli_uses_effective_project_name[project:gh_acme__widgets-expected2]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/deltas/test_compute.py::test_compute_deltas_with_known_parent_resolves_parent_branch
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/deltas/test_diff_name_status_git.py::test_resolve_current_changespec_head_ref_prefers_fetched_remote
    failed in 20260809T052937Z-a4a340679580-1693831-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_accepts_expected_deleted_exact_dir
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_marks_missing_exact_dir_for_broad_fallback
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_normalizes_exact_artifact_dirs_without_broad_load
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_lazy_attempt_hydration.py::test_normal_disk_load_does_not_hydrate_attempt_history
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_bad_index_uses_bounded_tier1_source_scan
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_falls_back_to_find_all
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 11 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_full_history_reconciles_from_source
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_missing_index_uses_bounded_tier1_source_scan
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_passes_snapshot_through
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_loader_phase5_wiring.py::test_load_agents_from_disk_uses_artifact_index_for_initial_tier
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_failed_plan_family_without_live_retry_remains_terminal[False-True]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_failed_plan_family_without_live_retry_remains_terminal[True-False]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_live_failed_plan_family_projects_retry_immediately
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_search_history_split.py::test_async_agents_search_load_stays_visible_inbox
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/actions/test_agent_search_history_split.py::test_sync_agents_search_load_stays_visible_inbox
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_ctrl_g_ctrl_x_ctrl_x_opens_panel_in_snippet_mode
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_request_converts_placeholders_for_xprompt_preview_only
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_request_keeps_placeholders_when_conversion_disabled
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_request_opens_one_screen_with_active_pane_snippet_source
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_request_reuses_undeclared_jinja_name_without_duplicate_input
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_save_request_returns_while_location_reads_are_stuck
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_skill_draft_requests_canonical_skill_destinations
    failed in 20260810T191247Z-5f6d8ea64f6e-1073390-full-run.json (head 5f6d8ea64f6e)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_agent_hints.py::test_cold_agent_hint_render_keeps_view_mode_open_for_enrichment
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_commit_hint_copy_suffix_copies_short_sha
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_commit_hint_editor_suffix_opens_raw_diff_path
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_commit_hint_opens_commit_view_modal
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_multiple_commit_hint_copy_suffix_copies_all_short_shas
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_multiple_commit_hint_editor_suffix_opens_raw_diff_paths
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_multiple_commit_hints_open_one_navigable_commit_view_modal
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_rendered_clan_commit_hint_editor_suffix_opens_raw_diff
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_commits.py::test_rendered_clan_commit_hint_opens_commit_view_modal
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_artifact_file_viewer_warning_is_surfaced
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_clipboard_suffix_bypasses_artifact_file_viewer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_editor_suffix_bypasses_artifact_file_viewer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_image_only_selection_uses_artifact_file_viewer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_mixed_selection_routes_all_files_in_order
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_text_only_selection_uses_pager
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_video_only_selection_uses_artifact_file_viewer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_image.py::test_view_submission_schedules_untracked_worker
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_mixed_report_and_file_selection_preserves_order
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_tool_call_report_hint_is_materialized_for_clipboard
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_tool_call_report_hint_is_materialized_for_editor
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_tool_call_report_hint_is_materialized_for_pager
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_tool_call_report_materialization_failure_drops_path
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/actions/test_view_files_reports.py::test_tool_call_report_materialization_runs_off_event_loop_thread
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_agent_run_log_contracts.py::test_run_log_loads_active_dismissed_and_meta_created_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_help_modal.py::test_help_digits_do_not_load_saved_queries
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_help_modal.py::test_help_modal_refresh_for_tab_rebuilds_sections
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 4 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_help_modal_guide.py::test_help_modal_builds_changespec_guide
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_image_mode_marks_layout_widgets
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_image_size_uses_scroll_viewport
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_modal_current_image_path_tracks_file_index
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_modal_uses_image_preview_before_text_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_modal_uses_video_placeholder_before_text_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_view_image_action_runs_viewer_for_video
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_view_image_action_runs_viewer_inside_suspend
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_notification_image_files.py::test_notification_view_image_action_warns_for_non_image
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_preview_panel_modal.py::test_preview_modal_forwards_percent_to_app_copy_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_management_modal_delete.py::test_project_management_modal_bulk_delete_deletes_once_and_preserves_failed_marks
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_management_modal_delete.py::test_project_management_modal_delete_confirm_reloads_and_removes_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_management_modal_edit.py::test_project_management_modal_alias_editor_updates_selected_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_management_modal_edit.py::test_project_management_modal_edit_opens_selected_project_spec
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_select_modal.py::test_empty_state_toggles_with_no_matches
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_select_modal.py::test_filter_updates_match_count_and_highlights_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_select_modal.py::test_picker_separates_labels_from_canonical_identity_and_duplicates
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_select_modal.py::test_project_select_modal_excludes_named_project_rows_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_project_select_modal.py::test_project_select_modal_loads_launchable_projects_and_active_changespecs
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/modals/test_saved_query_picker.py::test_focused_query_input_can_type_artifact_file_digits_and_star
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_malformed_cached_query_reports_error_without_crashing
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_picker_digit_loads_query_and_preserves_history_semantics
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_picker_is_pr_only_and_bare_digits_only_switch_artifacts
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_picker_mouse_selection_and_empty_state
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_picker_navigation_enter_cancel_and_empty_slot_warning
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_saved_query_picker.py::test_picker_uses_immutable_cached_snapshot_and_active_order
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_snippet_name_modal.py::test_derived_only_collision_returns_composed_template
    failed in 20260813T234301Z-c1b2724a1fc4-2672018-full-run.json (head c1b2724a1fc4)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_unified_xprompt_save_modal.py::test_project_skill_destination_verdict_is_project_qualified
    failed in 20260808T164713Z-125b5c31b23a-23762-full-run.json (head 125b5c31b23a)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_unified_xprompt_save_modal.py::test_skill_destination_verdict_shows_both_names
    failed in 20260808T164713Z-125b5c31b23a-23762-full-run.json (head 125b5c31b23a)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_xprompt_select_modal.py::test_xprompt_select_ctrl_o_loads_read_only_definition_without_target
    failed in 20260808T225434Z-01fa3b106a3e-233876-full-run.json (head 01fa3b106a3e)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_xprompt_select_modal.py::test_xprompt_select_ctrl_o_loads_selected_definition_for_editing
    failed in 20260808T225434Z-01fa3b106a3e-233876-full-run.json (head 01fa3b106a3e)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_agent_groups_grouping_mode_keys.py::test_clan_descendants_inherit_outer_anchor_keys_in_every_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_agent_groups_grouping_mode_keys.py::test_grouping_keys_for_agents_by_date_uses_bucket_at_l0
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_agent_groups_grouping_mode_keys.py::test_grouping_keys_for_agents_by_status_uses_bucket_at_l0
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_agent_groups_grouping_mode_keys.py::test_panel_uses_changespec_level_ignores_project_scoped_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_agent_groups_grouping_mode_keys.py::test_panel_uses_changespec_level_skipped_in_non_standard_modes
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_collapsed_subgroup_hides_only_that_subgroup
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_earlier_emits_weeks_newest_first_then_no_timestamp
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_singleton_today_emits_one_hour_subgroup
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_sorts_within_bucket_by_latest_timestamp_desc
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_this_week_emits_days_newest_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_today_emits_hourly_groups_and_newest_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_date_yesterday_emits_windows_newest_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_project_emits_project_l1_and_sibling_l2_for_grouped_roots
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_project_singleton_root_does_not_emit_l1_banner
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_status_collapsed_sibling_root_hides_only_its_members
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_status_emits_sibling_sub_banner_under_status_bucket
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_status_keeps_input_order_within_bucket
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_by_status_singleton_root_does_not_emit_l1_banner
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_collapsed_group_suppresses_descendants_and_leaves_siblings_alone
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_collapsed_sibling_root_hides_only_its_members
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_layout.py::test_default_fold_registry_renders_everything_expanded
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_build_parses_each_cs_once
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_changespec_groups_perf.py::test_by_date_enumerate_parses_each_cs_once
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_changespec_groups_perf.py::test_by_status_build_does_not_parse_timestamps
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/models/test_changespec_groups_perf.py::test_walk_order_uses_supplied_latest_map
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/repro/test_agents_tab_replay.py
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/repro/test_capture_ring.py
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/repro/test_invariants.py
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/repro/test_repro_cli.py
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_agent_fold_transitions_tools.py::test_capital_l_still_expands_all_folds_on_other_tabs
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agent_launch_dispatch.py::test_run_agent_launch_body_bulk_multi_prompt_rejection_records_failed_history
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agent_marking.py::test_bulk_change_status_keeps_changespec_status_flow
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agent_neighbor_navigation.py::test_changespec_sibling_navigation_still_direct_jumps
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agent_neighbor_navigation_targets.py::test_folded_clan_neighbor_excludes_starting_and_dismissed_members
    failed in 20260813T202712Z-15cdba4aa619-3002707-full-run.json (head 15cdba4aa619)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agents_jump_to_prs_subtab.py::test_enter_from_agents_lands_on_prs_subtab_for_matching_patch
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agents_jump_to_prs_subtab.py::test_enter_from_agents_rewrites_query_and_lands_on_prs_subtab
    failed in 20260809T031429Z-2634fb4759db-242185-full-run.json (head 2634fb4759db)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agents_jump_to_prs_subtab.py::test_load_saved_query_from_agents_lands_on_prs_subtab
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agents_panel_fold_mode.py::test_changespec_direct_level_sets_every_section_exactly[1-FoldLevel.COLLAPSED]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agents_panel_fold_mode.py::test_changespec_direct_level_sets_every_section_exactly[2-FoldLevel.EXPANDED]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agents_panel_fold_mode.py::test_changespec_direct_level_sets_every_section_exactly[3-FoldLevel.FULLY_EXPANDED]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agents_panel_fold_mode.py::test_changespec_fold_dispatch_remains_unchanged
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agents_panel_fold_mode.py::test_direct_dispatch_uses_configured_agent_and_changespec_subkeys
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_agents_panel_fold_mode.py::test_exhaustive_panel_state_does_not_enter_changespec_cyclers
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifact_file_vcs_clipboard.py::test_copy_as_path_and_contents_materialize_vcs_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifact_file_vcs_clipboard.py::test_marked_copy_contents_uses_snapshot_mode_and_materializes
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifact_pane_tab_navigation.py::test_next_tab_switches_from_agents_when_no_live_artifact_pane
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifact_pane_tab_navigation.py::test_prev_tab_from_axe_goes_to_changespecs
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifact_pane_tab_navigation.py::test_prev_tab_from_axe_goes_to_patches
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bead_plan_jump.py::test_beads_open_plan_selects_unloaded_plans_pane
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bead_plan_jump.py::test_crosslink_actions_warn_when_counterpart_is_missing
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bead_plan_jump.py::test_plans_open_bead_clears_filter_and_selects_closed_bead
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_beads_mutations.py::test_editor_result_submits_only_changed_type_valid_fields
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_beads_navigation.py::test_selection_marks_jumps_and_reload_preserve_stable_target
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bugs.py::test_bugs_load_lazily_navigate_filter_and_jump_links
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bugs_backend.py::test_snapshot_collects_provider_issues_and_local_links
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_bugs_backend.py::test_snapshot_resolves_display_name_scope_for_local_bead_links
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_chats_filtering.py::test_enter_pushes_full_transcript_preview
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_chats_filtering.py::test_filter_bar_and_provenance_cycle_update_rows_and_summary
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_chats_loading.py::test_first_page_paints_before_full_extension
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_chats_loading.py::test_jk_navigation_skips_headers_without_highlight_echoes
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_marked.py::test_marked_bugs_copy_the_marked_set
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_marked.py::test_marked_chats_copy_the_marked_set
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_marked.py::test_marked_commits_copy_in_visual_order_with_labeled_sections
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_marked.py::test_marked_files_contents_report_pre_filtered_binary_rows
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_marked.py::test_marked_plans_copy_the_marked_set
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_mode.py::test_bugs_copy_targets_include_an_agent_ready_prompt
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_chats_copy_targets_use_path_agent_and_full_transcript
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_chats_percent_n_never_copies_a_changespec_name
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_commits_copy_targets_use_the_visible_commit_and_terminal_plan_tag
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_footer_uses_the_active_artifacts_subtab[bugs-expected3]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_footer_uses_the_active_artifacts_subtab[chats-expected2]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_footer_uses_the_active_artifacts_subtab[commits-expected0]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_footer_uses_the_active_artifacts_subtab[other-expected4]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_footer_uses_the_active_artifacts_subtab[plans-expected1]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_copy_mode_rejects_empty_artifacts_without_using_hidden_pr_state
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_mode.py::test_each_artifacts_copy_menu_supports_snapshot_and_names_unknown_keys[bugs]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_each_artifacts_copy_menu_supports_snapshot_and_names_unknown_keys[chats]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_each_artifacts_copy_menu_supports_snapshot_and_names_unknown_keys[commits]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_copy_mode.py::test_each_artifacts_copy_menu_supports_snapshot_and_names_unknown_keys[other]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_each_artifacts_copy_menu_supports_snapshot_and_names_unknown_keys[plans]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_binary_contents_refuse_with_kind_named_warning
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_copy_targets_cover_contents_paths_source_and_label
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_generic_reference_keys_degrade_safely_on_empty_scaffold[at]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_generic_reference_keys_degrade_safely_on_empty_scaffold[exclamation_mark]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_marked_paths_preserve_visible_order
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_files_percent_unknown_key_never_reaches_changespec_dispatch
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_link_and_json_keys_dispatch_uniformly_across_artifacts_subtabs[bugs-l-J]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_link_and_json_keys_dispatch_uniformly_across_artifacts_subtabs[chats-l-J]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_link_and_json_keys_dispatch_uniformly_across_artifacts_subtabs[commits-l-J]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_link_and_json_keys_dispatch_uniformly_across_artifacts_subtabs[other-L-j]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_link_and_json_keys_dispatch_uniformly_across_artifacts_subtabs[plans-l-J]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_plans_copy_targets_use_the_selected_plan_payload
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_plans_design_copy_warns_when_selected_row_has_no_bead_design
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_plans_owner_copy_targets_preserve_the_bead_link
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_reference_keys_dispatch_uniformly_across_artifacts_subtabs[bugs]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_reference_keys_dispatch_uniformly_across_artifacts_subtabs[chats]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_reference_keys_dispatch_uniformly_across_artifacts_subtabs[commits]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_mode.py::test_reference_keys_dispatch_uniformly_across_artifacts_subtabs[plans]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_references.py::test_files_markdown_link_dispatch_preserves_visible_order[False]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_copy_references.py::test_files_markdown_link_dispatch_preserves_visible_order[True]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_files_detail.py::test_enriched_metadata_is_humanized_and_sha_is_shortened
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_detail.py::test_explicit_and_default_origins_are_plain_and_distinct
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_filtering.py::test_filter_tokens_match_file_fields_and_date_bounds
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_filtering.py::test_free_text_filter_matches_vcs_relative_path
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_filtering.py::test_project_filter_accepts_display_name_without_rendering_storage_key
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_filtering.py::test_repeatable_kind_is_or_while_free_text_terms_are_anded
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_loading.py::test_cursor_survives_refresh_and_jk_has_no_highlight_echoes
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_loading.py::test_data_loader_uses_only_project_scope_and_limit
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_loading.py::test_error_snapshot_renders_status_without_crashing
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_loading.py::test_first_page_paints_before_full_extension
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_open.py::test_files_explicit_viewer_handoff_uses_visible_mark_order
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_rendering.py::test_info_uses_precomputed_kind_and_explicit_counts
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_rendering.py::test_rows_stay_newest_first_with_date_headers_and_display_names
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_rendering.py::test_viewer_classifier_drives_icons_colors_origin_and_size
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_subtabs.py::test_files_child_is_remembered_and_only_visible_child_is_active
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_subtabs.py::test_marks_and_jump_history_are_isolated_by_leaf_pane_key
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_subtabs.py::test_parenthesis_keys_cycle_only_inside_files_with_wraparound
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_list_navigation.py::test_configured_navigation_actions_route_to_non_pr_list
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_list_navigation.py::test_files_implements_shared_stable_target_navigation
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[beads]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[bugs]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[chats]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[commits]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[other]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_clear_marks_is_scoped_to_the_active_artifacts_subtab[plans]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_non_pr_artifact_mark_toggles_stable_target_without_touching_pr_marks[bugs-target3]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_non_pr_artifact_mark_toggles_stable_target_without_touching_pr_marks[chats-target2]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_non_pr_artifact_mark_toggles_stable_target_without_touching_pr_marks[commits-target0]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_non_pr_artifact_mark_toggles_stable_target_without_touching_pr_marks[other-target4]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_non_pr_artifact_mark_toggles_stable_target_without_touching_pr_marks[plans-target1]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_artifacts_marking.py::test_project_scope_change_clears_every_non_pr_mark_set
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_plans_data.py::test_snapshot_partitions_live_linked_documents_from_archive
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_plans_data.py::test_snapshot_reuses_unchanged_previous_snapshot
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_plans_interactions.py::test_proposal_actions_keep_existing_approval_flow
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_plans_loading.py::test_snapshot_resolves_display_name_scope_without_store_errors
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_click_message_and_reactivation_keep_lazy_pane_state
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_ctrl_space_dispatches_repeat_agent_from_every_subtab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_direct_artifacts_start_initializes_default_non_pr_state
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_palette_has_direct_jump_for_every_artifacts_subtab
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 3 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_scope_inventory_is_lazy_and_picker_updates_all_placeholders
    failed in 20260812T122925Z-62951abcb4a2-1301764-full-run.json (head 62951abcb4a2)
    excluded by 2 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_startup_scope_keeps_unresolvable_ref_unchanged
    failed in 20260812T122925Z-62951abcb4a2-1301764-full-run.json (head 62951abcb4a2)
    excluded by 2 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_startup_scope_normalizes_display_name_to_project_key
    failed in 20260812T122925Z-62951abcb4a2-1301764-full-run.json (head 62951abcb4a2)
    excluded by 2 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 3 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_collector.py::test_collector_classifies_against_runtime_interval
    failed in 20260812T142717Z-46773f606446-2492554-full-run.json (head 46773f606446)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_collector.py::test_collector_falls_back_to_config_interval_without_runtime_status
    failed in 20260812T142717Z-46773f606446-2492554-full-run.json (head 46773f606446)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_changespec_detail_only_refresh.py::test_detail_only_refresh_skips_update_list
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_detail_only_refresh.py::test_full_refresh_still_calls_update_list
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_calls_patch_changespec_row_once_no_clear_options
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_detail_only_refresh.py::test_mark_toggle_falls_back_to_full_refresh_on_patch_failure
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_graph_index.py::test_update_relationships_from_index_avoids_per_row_rebuilds
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_hooks_or_collapse_routes_to_cl_grouped_collapse
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_jk_in_grouped_mode_walks_collapsed_banner_stops
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_jump_targets_include_collapsed_banner_in_render_order
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_banner_to_cl_triggers_refresh_even_when_idx_unchanged
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_navigate_steps_through_collapsed_banner_then_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_include_collapsed_banner
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouped_navigation.py::test_navigation_stops_skip_expanded_banners
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_date_to_by_status
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_advances_by_project_to_by_date
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_clears_current_changespec_group_key
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_emits_cl_grouping_toast
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_on_cls_tab_does_not_touch_agents_state
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_schedules_changespec_grouping_mode_save
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_cycle_wraps_back_to_by_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_fold_state_preserved_after_cycle_round_trip
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_per_mode_registry_dict_grows_lazily
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_rapid_changespec_cycles_save_latest_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_project_to_by_status
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_advances_by_status_to_by_date
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_reverse_cycle_wraps_back_to_by_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_three_cycles_returns_to_by_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_cycle.py::test_three_reverse_cycles_returns_to_by_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_integration.py::test_o_cycles_widget_through_every_grouping_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_grouping_integration.py::test_tab_switch_preserves_each_tabs_grouping_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespec_query_corpus_routing.py::test_async_reload_prepares_corpus_inside_worker
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hidden_when_patches_exist
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_hides_after_first_patch_arrives
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_mounts_single_quickstart_panel
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_explicit_limit_truncates_and_remains_visible
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_sidecar_filter_and_compatibility_toggle_share_collection_scope
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_unchanged_relative_query_reuses_cache_and_refreshes_its_clock
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap]
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[aggregate-cap]
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[exact]
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[provider-cap]
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_absent_project_token_collects_all_projects
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_ace_query_project_overrides_config_and_cwd_before_first_collection
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_commits_filter_bar_rejects_invalid_submit
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_committed_project_key_alias_and_unknown_ref_canonicalization
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_custom_default_query_controls_first_collection
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_filters.py::test_inferred_project_is_visible_before_first_collection
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_interactions.py::test_commit_fetch_task_uses_visible_project_name_and_matching_file
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_interactions.py::test_commits_cycle_merges_updates_query_and_recollects
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_interactions.py::test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_interactions.py::test_commits_refresh_override_drives_action_footer_and_help
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows
    failed in 20260808T035646Z-315a5f9ffbb4-652651-full-run.json (head 315a5f9ffbb4)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_center_navigation.py::test_repeated_first_navigation_is_idempotent
    failed in 20260814T004329Z-62fb94129662-3787925-full-run.json (head 62fb94129662)
    excluded by 3 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_center_tabs.py::test_catalog_is_the_single_numbered_alphabetical_source
    failed in 20260814T014619Z-5ec9262274d8-457113-full-run.json (head 5ec9262274d8)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_pane_widget.py::test_config_filter_accepts_brackets_and_tab_switches_main_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_copy_as_palette_contexts.py::test_bead_rows_cover_every_default_target_with_warm_previews
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_bead_rows_hide_empty_optional_body_and_design_targets
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_changespec_context_filters_missing_pr_fields_and_uses_display_name
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_commit_plan_target_is_filtered_when_warm_row_has_no_plan
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_copy_as_palette_contexts.py::test_commit_rows_join_registry_keys_availability_and_warm_previews
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_copy_as_palette_contexts.py::test_duplicate_and_rebound_accelerators_follow_dispatch_precedence
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[beads-No beads entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[bugs-No bugs entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[chats-No chats entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[commits-No commits entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[other-No other entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_empty_artifacts_context_warns[plans-No plans entry to copy]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[contents-path]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[handoff-link]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[json-contents]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[link-json]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[path-source]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[reference-handoff]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[snapshot-reference]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_collision_winners_match_dispatch_precedence[source-label]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_pdf_row_previews_the_source_path_its_copy_actually_yields
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_rows_cover_every_default_target_with_warm_previews
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_rows_filter_binary_contents_and_missing_source_from_warm_state
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_files_vcs_row_keeps_materializable_path_and_contents_targets
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_contexts.py::test_marked_commit_context_uses_visible_order_and_plural_labels
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_copy_as_palette_contexts.py::test_marked_files_keep_partially_representable_targets_with_warm_counts
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_entrypoints.py::test_percent_opens_palette_for_each_live_artifacts_subtab[commits]
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_copy_as_palette_modal.py::test_copy_palette_stacks_over_forwarding_modal
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_modal.py::test_modal_navigation_enter_unknown_and_cancel_behavior
    failed in 20260809T010110Z-bcf5748b6bf7-2831382-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_modal.py::test_pr_palette_dispatch_and_lifecycle_parity
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_modal.py::test_real_escape_and_q_restore_normal_footer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_modal.py::test_snapshot_dispatch_waits_until_palette_is_unmounted
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_as_palette_modal.py::test_unknown_key_retains_real_palette_and_copy_mode
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_targets.py::test_changespec_link_uses_humanized_name_and_pr_url
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 4 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_targets.py::test_changespec_link_warns_without_a_pr_url[None]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_targets.py::test_changespec_link_warns_without_a_pr_url[]
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_copy_targets.py::test_copy_target_registry_exactly_covers_default_keymap_targets
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_deltas_builder.py::TestChangeSpecDetailFileHints::test_update_display_with_hints_includes_expanded_deltas
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_deltas_builder.py::TestPatchDetailFileHints::test_update_display_with_hints_includes_expanded_deltas
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_entry_points_vcs_prefix_persistence.py::test_quick_changespec_skips_save_for_non_launchable_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_entry_points_vcs_prefix_selection.py::test_quick_current_changespec_reports_vcs_detection_error_without_saving
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_entry_points_vcs_prefix_selection.py::test_start_custom_agent_selector_hides_home_project_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_artifact_dirty_flags.py::test_artifact_change_marks_all_surfaces_dirty
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_artifact_dirty_flags.py::test_artifact_change_schedules_only_changespecs_for_bead_file
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_artifact_dirty_flags.py::test_artifact_change_schedules_only_changespecs_for_project_file
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_artifact_dirty_flags.py::test_artifact_change_uses_cached_sdd_beads_dir_for_local_store
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_artifact_dirty_flags.py::test_selection_navigation_does_not_trigger_refresh_work
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_nav_gate.py::test_artifact_change_marks_dirty_and_dispatches_changespecs_when_idle
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_deferred_resumes_refresh_after_prompt_closes
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_defers_refresh_work_during_prompt_input
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_gate_debug_modal.py::test_notification_row_opens_debug_even_without_gate_bundle
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_hint_input_bar_duplicate_guard.py::test_view_files_refocuses_existing_hint_bar_instead_of_remounting
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_entries_prs_subtab.py::test_dismiss_with_none_result_does_nothing
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_entries_prs_subtab.py::test_jump_to_agents_entry_leaves_artifacts_subtab_untouched
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_entries_prs_subtab.py::test_jump_to_changespec_entry_selects_prs_subtab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_backtick_remains_control_during_partial_hint
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_bgcmd_entry_falls_back_without_info
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_bgcmd_entry_includes_command
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_ctrl_d_scrolls_without_dismissing
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_ctrl_u_scrolls_up_without_dismissing
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_no_last_position
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_on_key_uses_uppercase_event_character
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_stores_last_position
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_styles_stopped_agent_status
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_all_modal_hints.py::test_jump_all_modal_two_character_hint_dispatches_only_after_completion
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_jump_to_changespec.py
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 4 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_jump_to_changespec.py::TestProjectAgentNoMeta::test_action_notifies_on_no_changespec
    failed in 20260809T013520Z-bcf5748b6bf7-3326301-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_changespec.py::TestUnknownClName::test_action_notifies_on_unknown
    failed in 20260809T013520Z-bcf5748b6bf7-3326301-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_hints.py::test_inline_jump_to_entry_allocates_and_dispatches_uppercase_hint
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_hints.py::test_inline_two_character_jump_escape_clears_partial_prefix
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_hints.py::test_inline_two_character_jump_waits_for_second_character
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_apostrophe_selects_first_target_directly_at_two_character_width
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_apostrophe_without_history_dispatches_first_changespec_hint
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_changespec_banner_anchor_restores_forward
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_changespec_jump_stack_walks_back_and_forward
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_discards_stale_changespec_back_stack_before_fallback
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_discards_stale_changespec_back_stack_before_valid_restore
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_selects_first_target_directly_at_two_character_width
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_with_history_pops_changespec_stack_lifo
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_with_history_restores_changespec_and_pops_origin
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_fast_jump_without_history_dispatches_first_changespec_without_footer
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_new_changespec_hint_jump_clears_forward_history
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_entry_history.py::test_push_changespec_to_history_records_origin_and_clears_forward
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_mentor_review.py
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_jump_to_mentor_review.py::test_does_not_open_modal_when_entry_id_not_found
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_mentor_review.py::test_does_not_open_modal_when_navigation_fails
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_mentor_review.py::test_does_not_open_modal_when_no_status_lines
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_mentor_review.py::test_does_not_open_modal_when_passed_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_jump_to_mentor_review.py::test_opens_mentor_review_when_comments_exist
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_launch_repeat_bulk.py::test_bulk_launch_takes_changespec_snapshot
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 4 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_leader_keybinding_footer.py::test_footer_surfaces_agent_run_log_only_on_cls_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_leader_keybinding_footer.py::test_footer_surfaces_space_run_agent_on_cl_and_agents_tabs
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_leader_keymap_dispatch.py::test_leader_space_runs_agent_from_current_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_leader_keymap_dispatch.py::test_leader_space_runs_agents_from_marked_cls
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_log_panel_keymap.py::test_admin_center_tabs_are_alphabetical_by_label
    failed in 20260814T014619Z-5ec9262274d8-457113-full-run.json (head 5ec9262274d8)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_log_panel_keymap.py::test_keyless_logs_command_opens_logs_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_log_panel_keymap.py::test_keyless_statistics_command_opens_statistics_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_log_panel_keymap.py::test_keyless_tasks_command_opens_tasks_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_mail.py::TestMailExecuteTaskSuccess::test_calls_execute_mail_with_correct_args
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_mail.py::TestMailExecuteTaskSuccess::test_calls_transition_with_correct_args
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_mail.py::TestMailExecuteTaskSuccess::test_returns_success_on_mail_and_transition
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_mail.py::TestMailExecuteTaskSuccess::test_returns_success_when_transition_fails
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_mail.py::TestMailExecuteTaskWorkspaceLifecycle::test_workspace_released_on_success
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_dispatches_custom_gate
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_dispatches_task_triage_without_marking_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_dispatches_view_report
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_silently_marks_actionless_notification_read[   ]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_silently_marks_actionless_notification_read[None]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_silently_marks_actionless_notification_read[]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_custom_gate.py::test_notification_flow_warns_for_unknown_action
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_notification_report_pane.py::test_display_file_dispatches_report_before_empty_attachment_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_scrolls_both_regions_in_reading_order
    failed in 20260809T195204Z-755987ff5b42-3162225-full-run.json (head 755987ff5b42)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_scrolls_incoming_commits[size1]
    failed in 20260809T195204Z-755987ff5b42-3162225-full-run.json (head 755987ff5b42)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_filter_forwards_brackets_and_tab_switches_main_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_projects_pane.py::test_admin_center_leaves_projects_tab_with_shift_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_projects_pane.py::test_projects_filter_yields_tab_to_admin_center
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_exact_name_match
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_fallback_no_match
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_fallback_suffix_appended
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_fallback_suffix_stripped
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_nearest_neighbor_when_selected_changespec_filtered_out
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_reload_and_reposition.py::test_off_tab_reload_does_not_mutate_current_idx
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_revert_agent_action.py::test_mixed_changespec_branch_marks_error_and_do_not_submit
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_saved_query_slot_keys.py::test_bare_digit_still_switches_subtab_without_prefix
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_digit_from_commits_lands_on_prs
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_digit_loads_slot_from_prs_subtab
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_empty_slot_leaves_query_unchanged
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_escape_cancels
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_saved_query_slot_keys.py::test_zero_then_zero_loads_slot_zero
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_show_agent_run_log_keymap.py::test_default_keymap_binds_v_to_agent_run_log_and_a_to_artifacts
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_show_agent_run_log_keymap.py::test_leader_a_opens_agent_run_log_for_selected_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_startup_stopwatch_live_update.py::test_read_changespecs_from_disk_returns_list
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_startup_stopwatch_live_update.py::test_slow_mount_state_read_does_not_block_app_key_dispatch
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_statistics_legends_states.py::test_overview_tile_click_uses_set_view_without_loading_again
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_legends_states.py::test_view_renderables_include_verified_metric_definitions
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_bindings.py::test_configured_bindings_dispatch_and_render_effective_help
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_interactions.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_interactions.py::test_range_and_project_group_switches_coalesce_to_latest_selection
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_interactions.py::test_seven_view_keyboard_and_mouse_navigation_share_order_without_reload
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_interactions.py::test_view_cycle_reuses_composite_result_and_updates_strip
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_loading.py::test_refresh_preserves_selection_and_hidden_tick_is_inert
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_statistics_pane_rendering.py::test_renderers_use_projected_labels_and_canonical_project_colors
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 5 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_statistics_view_number_select.py::test_jump_key_then_digit_selects_view
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_feedback_submitted_at
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_plan_submitted_at
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_loader_agent_plan_times_reflects_mid_run_update
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_wait_modal.py::test_modal_displays_and_preserves_read_only_bead_waits
    failed in 20260811T104757Z-81e7b02d6906-675287-full-run.json (head 81e7b02d6906)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_xprompt_browser_load_keymap.py::test_shift_tab_switches_admin_center_tab_on_yaml_backed_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_admin_center_tab_on_eligible_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_xprompt_browser_load_keymap.py::test_tab_switches_main_tab_after_typed_filter_text
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_y_keymap_non_blocking.py::test_reload_does_not_block_event_loop
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_y_keymap_non_blocking.py::test_run_async_refresh_sets_and_clears_loading_flag
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/test_y_keymap_non_blocking.py::test_schedule_when_idle_spawns_pump_free_task
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_writes_loop_recovery_record
    failed in 20260807T224841Z-0c084068cfa7-3855043-full-run.json (head 0c084068cfa7)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/visual
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/widgets/test_agent_display_name_model_metadata.py::TestAgentNameMetadata::test_named_agent_renders_name_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_display_name_model_metadata.py::TestAgentNameMetadata::test_unnamed_agent_renders_unassigned_name_first
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_display_plan_section.py::test_plan_and_artifacts_lead_context_in_maximal_append_flow
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_display_plan_section.py::test_plan_lane_follows_optional_sections_inside_sase_context
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_display_project_names.py::TestProjectDisplayNameRendering::test_dotless_logical_project_name_keeps_empty_grouping_name_root
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_list_grouping.py::test_mixed_project_scoped_agent_uses_no_changespec_bucket
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_list_status_indicators.py::TestRelativeWaitDurationRendering::test_family_child_header_renders_waiting_for_like_root_waiting_row
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_agent_page_url.py::test_page_lane_appears_after_name_and_before_project_fields
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_info_panel_grouping.py::test_status_and_grouping_render_on_separate_lines
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_info_panel_grouping.py::test_update_countdown_keeps_countdown_on_second_line
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_grouped.py::test_banner_natural_width_uses_two_cell_prefix_for_l1
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_falls_back_when_idx_out_of_range
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_falls_back_when_name_drifts
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_records_optimal_target_width
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_refuses_when_banner_rows_offset_indices
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_returns_false_before_initial_render
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_list_patch.py::test_patch_unmarks_row_falls_back
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_onboarding.py::test_changespec_onboarding_content_includes_docs_lifecycle_and_storage
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_onboarding.py::test_changespec_onboarding_queue_card_uses_active_keymap_registry
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_onboarding.py::test_changespec_onboarding_uses_active_keymap_registry
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_changespec_onboarding.py::test_patch_onboarding_content_includes_docs_lifecycle_and_storage
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_changespec_onboarding.py::test_patch_onboarding_uses_active_keymap_registry
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_marks_provider_candidates_as_directories
    failed in 20260814T153756Z-21633ba1bf04-2503692-full-run.json (head 21633ba1bf04)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_model_paren_completion_offers_alias_keys_and_model_values
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_navigation_widgets.py::test_info_panel_fold_indicator_all_fully_expanded
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_navigation_widgets.py::test_info_panel_fold_indicator_mixed_states
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_navigation_widgets.py::test_info_panel_fold_indicator_shown_when_any_expanded
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py::test_artifact_ref_kind_cache_warms_off_thread
    failed in 20260808T213424Z-48e8f10d3c79-2334611-full-run.json (head 48e8f10d3c79)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor
    failed in 20260806T134713Z-fa8fc69e46c4-4053698-full-run.json (head fa8fc69e46c4)
    excluded by 2 scoped run(s), first 20260806T134633Z-fa8fc69e46c4-4030190.json (head fa8fc69e46c4)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-selection, contract-set-always
  tests/ace/tui/widgets/test_prompt_glossary.py::test_glossary_context_change_repaints_highlights
    failed in 20260809T135801Z-e5487ce35812-230951-full-run.json (head e5487ce35812)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_glossary.py::test_glossary_overlay_survives_real_insert_before_changed_handler
    failed in 20260809T135801Z-e5487ce35812-230951-full-run.json (head e5487ce35812)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_glossary.py::test_glossary_overlay_survives_repeated_real_inserts
    failed in 20260809T135801Z-e5487ce35812-230951-full-run.json (head e5487ce35812)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_glossary.py::test_glossary_scan_is_cached_by_text_and_compiled_catalog
    failed in 20260809T135801Z-e5487ce35812-230951-full-run.json (head e5487ce35812)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_preview_target.py::test_slash_skill_resolution_looks_up_the_skills_reference_name
    failed in 20260808T164713Z-125b5c31b23a-23762-full-run.json (head 125b5c31b23a)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_tab_quickstart.py::test_artifacts_quickstart_advertises_every_subtab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_tab_quickstart.py::test_artifacts_quickstart_uses_configured_subtab_keys
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_tab_quickstart.py::test_tab_quickstart_no_match_callout_is_prs_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/ace/tui/widgets/test_tab_quickstart.py::test_tab_quickstart_wrapped_descriptions_use_hanging_indent
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_candidates_include_changespec_metadata
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 6 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_menu_renders_changespec_project_display_name
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_menu_renders_project_and_changespec_badges
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_colon_auto_opens_ref_menu
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_xprompt_completion.py::test_slash_skill_completion_filters_to_skills_and_uses_slash_insertions
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_commit_publication.py::test_push_failure_is_queued_and_next_commit_drains_idempotently
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_commit_publication_queue.py::test_mixed_queue_publishes_good_items_and_quarantines_only_bad_item
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_clears_stale_index_lock_before_recovery
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_failure_after_payload_write_restores_clean_tree
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_recovers_dirty_payload_before_pull
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_reuses_one_name_registry_load_session
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_transaction_commits_and_pushes_only_payload
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_non_fast_forward_recomputes_and_retries_push_once
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_import_boundaries.py::test_agents_sync_does_not_import_ace_layer
    failed in 20260812T123416Z-62951abcb4a2-1339391-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive_validation.py::test_each_archive_diagnostic_has_a_single_purpose_built_source
    failed in 20260811T211606Z-f53e43ab139a-955496-full-run.json (head f53e43ab139a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive_validation.py::test_full_validate_check_set_passes_with_pending_queue_and_unpublished_prompt
    failed in 20260811T211606Z-f53e43ab139a-955496-full-run.json (head f53e43ab139a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_reports_unpublished_even_when_queued
    failed in 20260811T211606Z-f53e43ab139a-955496-full-run.json (head f53e43ab139a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive_validation.py::test_pending_manifest_run_without_queue_entry_is_a_nonfailing_warning
    failed in 20260811T211606Z-f53e43ab139a-955496-full-run.json (head f53e43ab139a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_referenced_by_planning.py::test_plan_referenced_by_requests_for_document_sidecar_refs
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_parsing.py::test_record_schema_rejects_schema_one
    failed in 20260811T185120Z-48617f3eec9d-3666226-full-run.json (head 48617f3eec9d)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_prompt_materialization.py::test_clone_failure_is_reported_as_actionable_hint
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_prompt_materialization.py::test_kind_to_role_mapping_includes_builtin_and_custom_ref_kinds
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_prompt_materialization.py::test_missing_document_sidecar_materializes_and_expands
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_changespec_refs.py
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_model_xprompts.py::test_model_xprompts_warn_for_unroutable_alias_override_value
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_invalid_sidecar_ref_policy
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_leftover_name_field
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_ok_for_canonical_bucketed_config
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_ok_when_sidecar_is_unset
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_scalar_sidecar_value
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_repos.py::test_repos_reports_undescribed_enabled_lazy_custom_entry
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand
    failed in 20260808T021234Z-e1da6d1b76fd-3179230-full-run.json (head e1da6d1b76fd)
    excluded by 4 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/fakey/test_runner_slots_e2e.py::test_crashed_fakey_runner_frees_slot_without_done_marker
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_fakey_agents_respect_cap_and_release_in_fifo_order
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_fakey_drain_barrier_waits_for_later_eligible_launch
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_fakey_priority_admission_differs_from_park_order
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_killing_parked_fakey_agent_keeps_queue_healthy
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_live_config_raise_releases_fakey_waiter_without_axe
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_catalog.py::test_resolve_agent_falls_back_to_meta_chat_path
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_catalog.py::test_resolve_agent_via_done_response_path
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_resume_refs.py::test_template_resume_ref_resolves_latest_concrete_agent_chat
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_resume_refs.py::test_template_suffix_resume_ref_resolves_latest_concrete_agent_chat
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_prompt.py::test_save_prompt_history_uses_atomic_replace
    failed in 20260814T152143Z-adea6b1dfcc2-2062240-full-run.json (head adea6b1dfcc2)
    excluded by 6 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_codex_fallback_artifacts.py::test_codex_finalizer_parser_cycle_appends_tool_artifacts
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_codex_fallback_invocation.py::test_codex_finalizer_includes_bead_close_when_bead_id_set
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_codex_fallback_invocation.py::test_codex_finalizer_runs_from_invoke_agent_when_dirty
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_codex_fallback_spawn_workspace.py::test_finalizer_inspects_spawn_workspace_when_parent_env_stale
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_additional_dirty_file_uses_provider_path
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_non_status_sdd_markdown_change_uses_provider_path
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_sibling_done_status_change_uses_provider_path
    failed in 20260814T150034Z-443566f7d058-1702877-full-run.json (head 443566f7d058)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_baseline.py::test_pre_existing_sibling_file_is_excluded_and_reported_separately
    failed in 20260814T163652Z-877465a5ad44-3521230-full-run.json (head 877465a5ad44)
    excluded by 36 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_bead_fast_path.py::test_bead_create_dispatch_records_acting_agent_as_created_by
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_bead_fast_path_mutations.py::test_execute_bead_cli_materializes_when_the_fast_path_context_defers
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_bead_fast_path_mutations.py::test_fast_path_rm_uses_rust_on_sidecar_layout
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_bead_fast_path_mutations.py::test_warm_sidecar_fast_mutation_commits_without_network_git
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_chat_handler_show.py::test_show_agent_via_done_response_path
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_agent_docs.py::test_init_memory_does_not_migrate_single_custom_provider_file
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_memory_agent_docs.py::test_init_memory_overwrites_multiple_custom_provider_files
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_memory_formatting.py::test_format_keeps_inline_code_spans_atomic_at_wrap_points
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_memory_glossary.py::test_memory_apply_generates_glossary_idempotently_and_copies_provider_shims
    failed in 20260808T234629Z-65f82ccd9f52-1443127-full-run.json (head 65f82ccd9f52)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_glossary.py::test_memory_init_retires_generated_glossary_when_config_is_removed
    failed in 20260808T234629Z-65f82ccd9f52-1443127-full-run.json (head 65f82ccd9f52)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_glossary.py::test_memory_plan_blocks_invalid_project_glossary
    failed in 20260808T234629Z-65f82ccd9f52-1443127-full-run.json (head 65f82ccd9f52)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_glossary.py::test_memory_plan_refuses_to_overwrite_unmarked_glossary_note
    failed in 20260808T234629Z-65f82ccd9f52-1443127-full-run.json (head 65f82ccd9f52)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_handler_outputs.py::test_init_memory_project_memory_includes_workspace_section
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_memory_handler_outputs.py::test_init_memory_project_memory_uses_managed_checkout_marker_name
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_memory_handler_repo_access.py::test_init_memory_mixed_linked_repos_render_repo_open
    failed in 20260807T153249Z-64922e12acef-1077169-full-run.json (head 64922e12acef)
    excluded by 5 scoped run(s), first 20260806T072850Z-531138373fc4-767279.json (head 531138373fc4)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_plan.py::test_skill_frame_default_render_is_stable
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_skills_sources.py::test_git_commit_skill_invokes_observable_wrapper
    failed in 20260807T153249Z-64922e12acef-1077169-full-run.json (head 64922e12acef)
    excluded by 11 scoped run(s), first 20260806T072850Z-531138373fc4-767279.json (head 531138373fc4)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_gate-expected_phrases3]
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_monitor-expected_phrases7]
    failed in 20260813T170517Z-29cb7924a87d-3470125-full-run.json (head 29cb7924a87d)
    excluded by 5 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_patches-expected_phrases4]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_patches-expected_phrases5]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_plan-expected_phrases8]
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_repo-expected_phrases11]
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_var-expected_phrases13]
    failed in 20260807T131800Z-c37e68f7a5bc-2434332-full-run.json (head c37e68f7a5bc)
    excluded by 2 scoped run(s), first 20260806T063622Z-3e8600168e48-207353.json (head 3e8600168e48)
    distinct change sets: 1
    rules across those runs: contract-set-always, contract-set-only
  tests/main/test_lsp_handler_environment.py
    failed in 20260811T183906Z-48617f3eec9d-3383645-full-run.json (head 48617f3eec9d)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_json_envelope_is_stable
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_limit_trims_the_newest_first_result
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_markdown_format_renders_a_pipe_table
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_shows_only_active_monitors_by_default
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_follow_streams_new_output_until_terminal
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_output_only_suppresses_the_detail_panel
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_output_reads_rotated_and_active_logs
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_notify_handler.py::test_explicit_create_path_writes_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_notify_handler.py::test_show_json_and_markdown
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_parser_command_defaults.py::test_bare_list_group_records_delegation_metadata
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_narrowing.py::test_patch_parser_supports_canonical_command_and_legacy_alias[patch0]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_narrowing.py::test_patch_parser_supports_canonical_command_and_legacy_alias[patch1]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_root_help.py::test_root_help_renders_compact_help
    failed in 20260810T203709Z-64ddea98a879-2931211-full-run.json (head 64ddea98a879)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_repo_init_plan.py::test_plan_reports_asset_only_agents_guide_refresh
    failed in 20260811T200618Z-e2cacbe34ce1-427612-full-run.json (head e2cacbe34ce1)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_update_command_entry.py::test_update_json_schema_version_is_pinned_to_dev_schema
    failed in 20260809T173230Z-2bb7ce46382f-1020456-full-run.json (head 2bb7ce46382f)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_xprompt_handler.py::test_xprompt_list_prints_load_issues_to_stderr
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_xprompt_show_handler.py::test_show_full_hit_renders_without_color_when_disabled
    failed in 20260808T054217Z-ab442ed247db-2331847-full-run.json (head ab442ed247db)
    excluded by 5 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_xprompt_show_handler.py::test_show_json_outputs_parseable_schema_and_stderr_warnings
    failed in 20260808T054217Z-ab442ed247db-2331847-full-run.json (head ab442ed247db)
    excluded by 5 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_xprompt_show_handler.py::test_show_raw_outputs_exact_definition_without_added_newline
    failed in 20260808T054217Z-ab442ed247db-2331847-full-run.json (head ab442ed247db)
    excluded by 5 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_xprompt_show_handler.py::test_show_raw_unavailable_exits_two_and_keeps_stdout_clean
    failed in 20260808T054217Z-ab442ed247db-2331847-full-run.json (head ab442ed247db)
    excluded by 5 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_holds_the_claim_when_the_followup_launch_succeeds
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls
    failed in 20260813T170517Z-29cb7924a87d-3470125-full-run.json (head 29cb7924a87d)
    excluded by 5 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_releases_the_claim_when_the_followup_launch_fails
    failed in 20260813T154514Z-6a0c35c8ec28-2526072-full-run.json (head 6a0c35c8ec28)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/notification_store/test_mute_snooze.py::TestExpireDueSnoozes::test_leaves_not_ready_rows
    failed in 20260810T182730Z-b67a8420f22d-93191-full-run.json (head b67a8420f22d)
    excluded by 1 scoped run(s), first 20260810T182627Z-b67a8420f22d-53811.json (head b67a8420f22d)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/notification_store/test_mute_snooze.py::TestMarkSnoozed::test_round_trip
    failed in 20260811T110417Z-81e7b02d6906-1036025-full-run.json (head 81e7b02d6906)
    excluded by 3 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/notification_store/test_senders.py::TestNotifyMentorsComplete::test_emits_jump_to_mentor_review_action
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/notification_store/test_snooze_e2e_matrix.py::TestResurfacedRowIsRecentActivity::test_old_row_leads_limited_ace_cli_and_mobile_pages
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_existing_positive_clone_adopts_new_legacy_artifacts_without_provider
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_existing_positive_clone_remains_usable_offline
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_explicit_init_denial_is_forwarded_for_managed_repo
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_local_and_in_tree_artifacts_are_imported_without_deleting_in_tree
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_materialization_bootstraps_primary_and_numbered_workspace
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_materialization_is_idempotent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_materialization_recovers_from_concurrent_sidecar_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_mismatched_local_git_repo_is_imported_via_staging
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_old_negative_record_is_retried_and_replaced
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_materialize.py::test_versioned_stale_clone_defers_overlap_and_skips_runtime_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_cleanup_push_warns_and_next_run_pushes_existing_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_import_push_preserves_schema_two_and_rerun_retries
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_accepts_minimal_config_and_projection_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_imports_pushes_cleans_and_reruns_without_new_commits
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/stats/test_views.py::test_builds_all_presentation_views_from_binding_payloads
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_views_projects.py::test_project_display_snapshot_projects_every_project_bearing_row
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_views_projects.py::test_work_rows_tolerate_partial_and_invalid_values
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_testing.py::test_ace_page_initial_state
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_ace_testing.py::test_ace_page_press
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_testing.py::test_expect_modal
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_deltas_fold_mode_cycles_summary_files_lines
    failed in 20260809T010110Z-bcf5748b6bf7-2831382-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_mark_single_spec_stays
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_navigation_next_at_end
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_navigation_next_key
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_navigation_prev_at_start
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_query_edit_modal_apply
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_query_edit_modal_cancel
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_query_edit_modal_invalid_query
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py::test_unmark_navigates_to_next_spec
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_acknowledge_terminal_status.py::test_strip_terminal_status_markers_processes_comments
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_acknowledge_terminal_status.py::test_strip_terminal_status_markers_processes_comments_running_agent
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_acknowledge_terminal_status.py::test_strip_terminal_status_markers_processes_hooks
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_acknowledge_terminal_status.py::test_strip_terminal_status_markers_processes_hooks_empty_running_agent
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_acknowledge_terminal_status.py::test_strip_terminal_status_markers_processes_mentors_running_agent
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_includes_anonymous_appears_as_agent_workflow
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_matches_source_scan_for_anonymous_workflows
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_still_filters_explicit_workflow_state_hidden
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_excludes_current_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_resolves_latest_completed_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_suffix_shape_resolves_latest_completed_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_explicit_completed_agent_uses_done_response_path
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_explicit_running_agent_falls_back_to_meta_chat_path
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_main_emits_parseable_json
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_malformed_metadata_is_ignored
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_missing_chat_history_fails_clearly
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_multiple_agents_resolve_in_invocation_order
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_multiple_aliases_to_same_transcript_are_coalesced
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_omitted_name_excludes_current_artifacts_dir
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_omitted_name_uses_most_recent_named_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_unreadable_transcript_is_rejected_before_loading
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_clan.py::test_agent_then_overlapping_clan_keeps_unique_later_member
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_clan.py::test_clan_and_agent_sources_preserve_parent_order
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_tribe.py::test_mixed_tribe_and_named_fork_parents_preserve_order
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_display_meta_priority.py::TestMetaChangespecPriority::test_changespec_preferred_over_project
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_display_meta_priority.py::TestMetaChangespecPriority::test_changespec_shown_alone
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_display_meta_priority.py::TestMetaChangespecPriority::test_changespec_with_cl_num
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader.py::test_load_all_agents_assigns_axe_summarize_hook_to_review_tribe
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader.py::test_load_all_agents_filters_hook_processes
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader.py::test_load_all_agents_includes_axe_fix_hook
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader.py::test_load_all_agents_with_running_claims
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_changespec.py::test_load_all_agents_with_crs_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 15 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_changespec.py::test_load_all_agents_with_fix_hook_review_agent
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 15 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_changespec.py::test_load_all_agents_with_mentor_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 15 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_changespec.py::test_load_all_agents_with_summarize_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 15 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_merge.py::test_done_json_dedup_with_changespec
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_merge.py::test_done_json_dedup_with_patch
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 13 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_merge.py::test_load_all_agents_dedup_preserves_workspace_num
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 15 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_merge.py::test_mentor_workflow_dedup_with_changespec
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_merge.py::test_mentor_workflow_dedup_with_patch
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 13 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_merge.py::test_running_workflow_dedup_ace_run
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_merge.py::test_workflow_dedup_propagates_failed_status
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_families.py::test_live_family_root_survives_shared_pid_for_runner_slot_context
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_families.py::test_pid_dedup_preserves_followup_workflow_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_reuse.py::test_pid_reuse_keeps_both_running_agents_with_different_suffix
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_reuse.py::test_pid_reuse_merges_running_agents_with_missing_suffix
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_reuse.py::test_pid_reuse_merges_running_agents_with_same_suffix
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_safety_net.py::test_pid_dedup_merges_running_workflow_rows_for_same_artifact
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_safety_net.py::test_pid_dedup_safety_net
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_pid_safety_net.py::test_pid_dedup_safety_net_works_on_review_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_fields_merged_into_axe_agent
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_removed_by_axe_pid
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_removed_by_plain_workflow_name
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_removed_by_workflow_axe_pid
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_removed_when_changespec_fix_hook_is_in_review_tribe
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs.py::test_embedded_vcs_removed_when_patch_fix_hook_is_in_review_tribe
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 13 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_fields_merged_into_axe_agent
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_removed_by_axe_pid
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_removed_by_plain_workflow_name
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_removed_by_workflow_axe_pid
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_removed_when_changespec_fix_hook_is_in_review_tribe
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_agent_loader_dedup_vcs_removal.py::test_embedded_vcs_removed_when_patch_fix_hook_is_in_review_tribe
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 13 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_epic_created_status.py::test_host_epic_metadata_reload_crosses_real_artifact_loader_boundary
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_model_timestamps.py::test_snapshot_agent_timestamps_display_includes_scalar_plan
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_name_wipe.py::test_wipe_done_agent_clears_lookup_registry_and_notifications
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix
    failed in 20260810T230434Z-62a4ddeb5feb-1713590-full-run.json (head 62a4ddeb5feb)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_exact_name_preferred_over_workflow
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_agent_by_workflow_name
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_dismissed_prefixed_artifact_without_done
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_done_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_local_bare_and_qualified_selectors_share_exact_first_lookup
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_only_done_returns_none_when_no_done
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_only_done_skips_running
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_prefers_running_over_done
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_returns_none_when_not_found
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_skips_dead_agent_without_done
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[epic_approved]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[noop]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[plan_committed]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::test_bare_named_agent_with_plan_rejected_outcome_is_not_wait_success
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_child_keeps_exact_reference
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_template_suffix_uses_latest_concrete_name
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_template_uses_latest_concrete_name
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_context.py::test_waited_agent_variables_load_as_fallback_context
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_plan_wait_exposes_plan_file_under_row_key
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_plan_wait_without_plan_path_exposes_nothing
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_planner_populates_both_base_and_row_keys
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_workflow_context.py::test_submitted_plan_file_renders_in_later_workflow_prompt
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_workflow_context.py::test_waited_producer_variables_render_in_later_workflow_prompt
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_ref_resolution.py::TestResolveAgentPatch::test_no_meta_changespec
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_ref_resolution.py::TestResolveAgentPatch::test_returns_patch
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_meta.py::test_revive_existing_meta_without_name_preserves_stored_lookup
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_changespec_claims_workspace_100_plus
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_changespec_fails_on_archive_error
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_changespec_fails_with_non_terminal_children
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_changespec_fails_without_pr
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_changespec_releases_workspace_on_failure
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_patch_claims_workspace_100_plus
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_patch_fails_on_archive_error
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_patch_fails_with_non_terminal_children
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_patch_fails_without_pr
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_archive.py::test_archive_patch_releases_workspace_on_failure
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 7 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_create_bead_attachment.py::test_a_bare_flag_attaches_to_the_agents_own_bead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_artifact_create_bead_attachment.py::test_a_bare_flag_without_a_bead_in_the_environment_fails_loudly
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_artifact_create_bead_attachment.py::test_an_explicit_bead_id_receives_the_minted_reference
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_artifact_create_bead_attachment.py::test_an_unknown_bead_id_fails_before_the_artifact_is_created
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_artifact_create_bead_attachment.py::test_omitting_the_flag_leaves_every_bead_untouched
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_artifact_provider_registry.py::test_registry_discovers_ref_providers_with_provenance
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_provider_registry.py::test_registry_honors_independent_disable_env
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_provider_registry.py::test_registry_registers_builtin_plan_and_entry_kind_descriptors
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_provider_registry.py::test_registry_rejects_malformed_ref_provider_icon
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_provider_registry.py::test_registry_skips_duplicate_and_invalid_ref_providers
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_external_issue_mirror.py::test_mirror_chop_closes_mirrored_bead_and_reports_counter
    failed in 20260812T171555Z-59967cc062a7-1769253-full-run.json (head 59967cc062a7)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_runner_script.py::test_run_configured_chop_once_reuses_passed_context_file
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_wait_checks_beads.py::test_wait_checks_keeps_unclosed_bead_only_wait_parked[missing]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_axe_chop_wait_checks_beads.py::test_wait_checks_keeps_unclosed_bead_only_wait_parked[open]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_axe_chop_wait_checks_beads.py::test_wait_checks_mixed_agent_and_bead_wait_requires_both
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_axe_chop_wait_checks_beads.py::test_wait_checks_observes_closed_bead_after_store_refresh
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_axe_chop_wait_checks_beads.py::test_wait_checks_resolves_closed_bead_only_wait
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_axe_process_start.py::test_ensure_recovers_unpublished_lock_holder_after_grace
    failed in 20260814T213608Z-d3c5254ca8cb-2839258-full-run.json (head d3c5254ca8cb)
    excluded by 6 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_chat_paths.py::TestFeedbackRoundChatPath::test_handle_plan_marker_no_agent_name_preserves_none
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_chat_paths.py::TestFeedbackRoundChatPath::test_handle_plan_marker_round1_uses_plan_suffix_in_agent_name
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_chat_paths.py::TestFeedbackRoundChatPath::test_handle_plan_marker_round2_uses_round_suffix_in_agent_name
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_chat_paths.py::TestFeedbackRoundChatPath::test_handle_plan_marker_uses_distinct_agent_per_round
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_phase_worker_alias[large]
    failed in 20260810T163435Z-a9770ee1937e-1929556-full-run.json (head a9770ee1937e)
    excluded by 2 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_phase_worker_alias[xlarge]
    failed in 20260810T163435Z-a9770ee1937e-1929556-full-run.json (head a9770ee1937e)
    excluded by 2 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_helpers_commit_output.py::test_extract_step_output_surfaces_commit_results_list
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_phases_wait_chats.py::test_resolve_wait_chat_paths_resolves_indexed_template
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_runner_utils.py::test_finalize_axe_runner_handles_errors
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_runner_utils.py::test_finalize_axe_runner_no_matching_patch
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_runner_utils.py::test_finalize_axe_runner_success
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bare_git_workspace.py::TestResolveGitRef::test_changespec_name
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_bead_page_associations.py::test_builds_associations_with_one_store_read_and_history_walk
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_page_publication.py::test_published_pages_never_attribute_a_commit_to_a_sidecar_remote
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_page_publication.py::test_sidecar_publication_anchors_associations_and_commit_links_to_primary
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_pages_paths.py::test_lexical_root_agrees_with_the_stored_parent_chain
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_pages_paths.py::test_pages_dirname_can_never_shadow_a_bead_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_publication_verification.py::test_close_on_a_store_without_a_remote_stays_silent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_publication_verification.py::test_close_publishes_when_the_configured_push_policy_missed_the_checkout
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_publication_verification.py::test_fast_path_mutation_publishes_through_the_same_verification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_publication_verification.py::test_fast_path_mutation_reports_unpublished_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_bead_publication_verification.py::test_unpublishable_close_fails_loudly_instead_of_printing_closed
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph
    failed in 20260812T150608Z-2f1512c7cf52-3014224-full-run.json (head 2f1512c7cf52)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_claims.py::test_declined_wait_claim_leaves_in_progress_store_untouched
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims.py::test_retained_wait_claim_does_not_commit_preexisting_dirty_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_lifecycle.py::test_claim_publication_failures_warn_and_preserve_local_transitions
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_lifecycle.py::test_claim_reclaim_and_release_use_canonical_store_without_commit_churn
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_lifecycle.py::test_release_claim_distinguishes_nothing_to_release
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_lifecycle.py::test_wait_claim_release_and_launch_promotion_publish_to_remote
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_locking.py::test_launch_claim_holds_store_lock_from_materialization_through_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_claims_locking.py::test_wait_claim_holds_store_lock_from_materialization_through_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_invalid_bead_does_not_refresh
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_refresh_failure_falls_back_with_diagnostics[refresh]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_refresh_failure_falls_back_with_diagnostics[retry]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_refresh_off_falls_back_with_diagnostics
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_refreshes_once_and_retries_missing_epic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_bead_script.py::test_epic_summary_renders_markdown_progress_sizes_children_and_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_plan_script.py::test_plan_and_bead_failure_emit_diagnostics_and_safe_identity_fallback
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_plan_script.py::test_unusable_plan_reference_falls_back_to_legacy_bead_summary[invalid]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_plan_script.py::test_unusable_plan_reference_falls_back_to_legacy_bead_summary[missing]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_clan_summary_epic_plan_script.py::test_unusable_plan_reference_falls_back_to_legacy_bead_summary[unreadable]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_bead_create_in_separate_repo_writes_and_commits_workspace_local_clone
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_close_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_create_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_dep_add_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_open_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_rm_auto_commit_message_includes_all_requested_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_rm_missing_id_does_not_remove_or_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_update_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_handle_bead_update_multi_id_auto_commit_message_joins_changed_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_auto_commit.py::test_redundant_update_and_close_skip_auto_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_and_update_phase_size_persist
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_phase_rejects_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_phase_rejects_patch_metadata
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_changespec.py::test_create_plan_accepts_changespec_and_bug
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_plan_accepts_patch_alias
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_changespec.py::test_create_plan_accepts_patch_and_bug
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_changespec.py::test_create_plan_preserves_external_absolute_plan_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_rejects_bug_id_without_changespec
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_rejects_size_for_plan_bead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_create_with_model_persists
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_show_displays_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_show_displays_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_show_omits_model_when_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_show_phase_omits_parent_plan_when_parent_has_no_design
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_update_changes_model_value
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_update_clears_model_with_empty_string
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_changespec.py::test_update_rejects_size_for_plan_bead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_history.py::TestRowBadges::test_the_search_row_carries_both_badges
    failed in 20260809T123141Z-7c7de9c9feda-2636397-full-run.json (head 7c7de9c9feda)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_close_note.py::test_close_with_note_applies_to_each_explicit_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_note.py::test_close_with_note_defers_to_truthful_slow_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_note.py::test_close_with_note_uses_one_slow_path_commit_and_agent_attribution
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_note.py::test_force_close_with_note_only_notes_explicit_parent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_note.py::test_reclose_with_note_reports_both_outcomes_and_commits_note
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_close_selected_phases_leaves_epic_and_other_phases_open
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_force_close_renders_cascade_and_commits_only_requested_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_auto_commit_names_expanded_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_composes_with_note_reason_and_resolution
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_rejects_invalid_selector_without_writes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_rejects_missing_phase_without_writes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_rejects_non_epics_without_writes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_reports_a_missing_epic_without_writes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_reports_closed_and_already_closed_in_one_invocation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_phases.py::test_phase_close_requires_exactly_one_positional_target
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_resolution.py::test_close_resolution_round_trips_end_to_end
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_resolution.py::test_conflicting_reclose_is_rejected_without_changing_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_close_resolution.py::test_force_close_sweeps_unfinished_child_end_to_end
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_color_modes_override_non_tty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_empty_messages_are_successful
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_json_is_never_colored
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_limit_caps_store_wide_root_beads
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_rows_carry_the_bead_created_cell_separate_from_edge_provenance
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_compact_shows_both_directions_and_verdicts
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[in-BLOCKS (-DEPENDS ON]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_direction_filters_sections[out-DEPENDS ON-BLOCKS (]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_explicit_status_filters_endpoints
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_full_adds_provenance
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_scoped_json_uses_shared_resolved_reference_shape
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_compact_groups_and_prints_census
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_full_and_json_render
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_store_wide_status_default_filters_closed_sources
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_list.py::test_dep_list_unknown_id_exits_one
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_rm.py::test_dep_rm_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_rm.py::test_dep_rm_errors_are_nonzero_and_leave_the_batch_untouched
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_rm.py::test_dep_rm_removes_edge_reports_readiness_and_records_history
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_rm.py::test_dep_rm_reports_the_remaining_active_blocker
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_rm.py::test_mirror_rebuild_and_fallback_export_do_not_resurrect_removed_edge
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_cycle_terminates_and_prints_warning
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_both_renders_two_trees
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_direction_in_inverts_walk
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_json_node_shape_and_full_provenance
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_levels_marks_truncated_remainder
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_marks_diamond_repeat_instead_of_cycle
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_output_is_byte_identical_across_runs
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_renders_linear_chain_and_longest_chain
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_rows_end_with_the_bead_created_cell_after_graph_markers
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_dep_tree.py::test_dep_tree_store_wide_forest_selects_top_level_roots
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_doctor_omits_prefix_warning_for_correctly_prefixed_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_doctor_warns_about_leaked_key_prefix
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_rewrites_config_and_preserves_existing_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_fix_issue_prefix_with_nothing_to_repair
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_fix_projection_refuses_row_set_drift
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_doctor.py::test_fix_projection_repairs_expected_drift_and_second_run_is_noop
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_invalid_type]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[init]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_json]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_empty_no_fallback]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_default_limit]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_filters]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_full]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_limit]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_limit_zero]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_history.py::test_history_compact_lists_event_metadata_and_changed_fields
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_history_full_shows_reopen_clearing_closed_at
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_history_json_envelope_field_filter_and_newest_limit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_history_labels_redundant_duplicate_close_in_all_formats
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_history_unknown_id_exits_nonzero_with_clear_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_declined_confirmation_writes_nothing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_ignores_append_only_chain
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_reports_overwrites_in_stable_order_and_supports_scope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_restore_is_provenanced_and_idempotent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_restore_yes_skips_non_tty_confirmation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_history.py::test_lost_notes_unknown_scoped_id_exits_nonzero
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_create_update_close_and_remove_canonicalize_shorthand
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_dependency_and_reference_commands_accept_shorthand
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_pages_url_resolves_shorthand_before_building_url
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_show_and_history_accept_unique_shorthand
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_update_accepts_multiple_shorthand_ids_in_one_batch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_id_shorthand.py::test_work_task_dry_run_uses_canonical_id_for_shorthand
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_explicit_compact_matches_default
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_full_reuses_show_rendering
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_includes_snoozed_by_default
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_json_empty_store_is_valid_envelope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_json_limit_preserves_total
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_json_outputs_envelope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_handle_bead_list_json_reports_implicit_closed_without_notice
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_color_modes_override_non_tty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_created_cell_carries_the_shared_glyph_and_accent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_default_auto_is_colorless_under_pytest_capture
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_no_color_env_suppresses_escapes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_preserves_parent_suffix_and_separator
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_renders_type_glyph_only_per_type
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_list.py::test_list_compact_type_cells_share_equal_cell_width
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_no_push_still_commits
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_routes_explicit_cwd_to_commit_and_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_legacy_namespace_still_pushes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_no_push_commits_without_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_mutation_push.py::test_handle_bead_update_multi_id_commits_once_and_pushes_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_handle_bead_note_auto_commit_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_note_appends_to_empty_notes_with_explicit_author
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_note_appends_to_existing_notes_and_history_shows_revisions
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_note_defaults_author_from_agent_identity
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_note_defaults_author_from_store_owner_without_agent_identity
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_note.py::test_note_rejects_blank_entry_without_writing_or_committing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_open.py::test_handle_bead_open_missing_id_exits_with_update_style_error
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_closed_ancestors
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_open.py::test_handle_bead_open_reopens_issue
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_pages.py::test_url_prints_resolved_hosted_page
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_idempotent_retry_skips_commit_and_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_public_entry_dispatch_uses_current_agent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_rejects_non_task_without_mutation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[missing-Evidence-issue not found: missing]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_reports_missing_task_and_blank_evidence[unused-   -note cannot be empty or blank]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_plus_one.py::test_plus_one_uses_canonical_commit_and_deferred_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_primary_store_from_primary_workspace
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_subdirectory
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_read_single_store.py::test_read_commands_use_sibling_store_from_sibling_workspace
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_refs.py::test_ref_add_list_and_rm_round_trip_through_the_slow_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_refs.py::test_ref_add_reports_a_missing_issue_without_crashing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_refs.py::test_ref_list_resolve_json_returns_machine_readable_outcomes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_refs.py::test_show_renders_resolved_and_missing_references
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_refs.py::test_show_without_references_omits_refs_section
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_bead_list_keeps_schema_two_store_in_plans_sidecar
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_bead_list_materializes_missing_split_sidecar
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_get_project_opens_warm_store_without_materialization
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_isolated_fixture_resolves_store_below_pytest_sandbox
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_plain_checkout_sidecar_record_resolves_read_only_bead_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_plain_checkout_split_sidecar_record_resolves_root_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_resolution.py::test_split_sidecar_with_mismatched_origin_is_not_usable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_search.py::test_handle_bead_search_whitespace_query_exits_usage_error
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_child_epic_under_epic_has_full_lineage
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_child_epic_under_phase_has_lineage_and_own_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_childless_phase_omits_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_deep_nested_child_epic_has_complete_lineage
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_explicit_full_matches_default
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_full_prints_page_url_when_resolved
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_phase_displays_size_and_rootward_lineage
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_phase_lists_child_epics
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show.py::test_show_plan_splits_phases_from_child_epics
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_budget.py::test_show_full_reduces_the_bead_store_exactly_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_compact.py::test_show_compact_color_modes_override_non_tty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_compact.py::test_show_compact_matches_the_same_list_row
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_compact.py::test_show_compact_renders_the_type_column
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_contains_every_bead_id_from_full_output
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_includes_page_url_when_resolved
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_includes_resolved_dependencies_and_blockers
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_missing_id_exits_with_stderr_only
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_nested_phase_includes_nearest_first_lineage_and_parent_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_json_root_includes_children_and_self_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_json.py::test_show_renders_recorded_and_unrecorded_resolution
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_python_and_rust_renderers_agree_on_the_plan_section[plans:../escape.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_python_and_rust_renderers_agree_on_the_plan_section[plans:202606/durable.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_python_and_rust_renderers_agree_on_the_plan_section[plans:202607/durable.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_python_and_rust_renderers_agree_on_the_plan_section[plans:202607/gone.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_keeps_one_line_for_a_legacy_path_that_resolves_to_itself
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_marks_a_reference_resolved_through_month_drift
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_prints_the_reference_above_its_resolved_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_renders_the_parent_epic_reference_for_a_phase
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_reports_a_malformed_reference
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_reports_an_ambiguous_reference_instead_of_guessing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_plan_reference.py::test_show_says_plainly_when_a_reference_resolves_nowhere
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_style.py::test_compact_style_invariant_over_corpus[patch]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_json_format_ignores_style_over_corpus[patch]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_style_invariant_epic_with_phases_and_child_epics
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_style.py::test_style_invariant_over_corpus[patch]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_style_invariant_over_corpus_per_wrap_width[patch-120]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_style_invariant_over_corpus_per_wrap_width[patch-40]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_style_invariant_over_corpus_per_wrap_width[patch-none]
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_style.py::test_style_invariant_phase_with_parent_epic_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_absolute_iso_timestamp_is_stored_verbatim
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_an_unknown_id_in_a_batch_snoozes_nothing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_batch_snooze_commits_once_with_ids_in_argument_order
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_cancel_commits_under_its_own_wake_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields0]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields1]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields2]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields3]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields4]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_unusable_arguments_are_refused_before_any_mutation[fields5]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_snooze.py::test_update_refuses_the_status_shortcut_and_names_the_snooze_command
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_all_no_op_batch_makes_no_commit
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_invalid_field_value_leaves_every_target_unmodified
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_mixed_batch_commits_only_changed_ids_and_prints_unchanged_rows
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_multi_id_update_applies_same_field_and_returns_issues_in_argument_order
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_multi_id_update_commits_once_with_ids_in_argument_order
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_shorthand_and_full_form_of_same_bead_collapse_to_one_update
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_status_closed_rejects_batch_with_out_of_batch_descendant
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_status_closed_succeeds_across_parent_and_child_in_either_order[False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_status_closed_succeeds_across_parent_and_child_in_either_order[True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_update_bulk.py::test_unknown_id_in_the_middle_exits_without_writing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_cleanup_decline_aborts_before_wipe_or_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_fresh_epic_has_no_cleanup_prompt_and_yes_skips_launch_prompt
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_json_implies_yes_to_all_noninteractively
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_no_flags_confirm_cleanup_then_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_noninteractive_cleanup_refuses_with_yes_to_all_remedy
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_orphaned_clan_bundle_is_released_and_launch_proceeds
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_orphaned_family_bundle_is_released_and_launch_proceeds
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_yes_still_prompts_for_cleanup_but_skips_launch_prompt
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_yes_to_all_skips_both_prompts
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_code_swap_lock.py::test_bead_work_exits_before_plan_mutations_while_code_swap_writer_holds
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_dry_run_retry_filters_closed_phases_without_mutating
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_dry_run_warns_force_reuse_without_mutating
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_legacy_land_owner_and_launches
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_live_land_owner_and_launches
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_workflow_name_only_owner
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_passes_when_no_collisions
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_retry_allows_terminal_same_name_attempt
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_collisions.py::test_work_retry_force_reuses_live_phase_owner_and_launches
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 2 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_contention_regressions.py::test_task_launch_waits_for_overlapping_epic_launch_and_claims_task
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_checkpoint_epic_work_launch_reports_contention_timeout_with_resume_flags
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_async_config_is_upgraded_to_sync_prelaunch_push
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_invokes_push_when_config_flag_enabled
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_no_push_flag_overrides_config
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_no_push_rejects_detached_store_before_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_push_failure_stops_before_launch_and_preserves_checkpoint
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_retry_push_failure_preserves_existing_checkpoint
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_uses_sync_push_even_when_config_flag_disabled
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_matches_confirmed_launch_before_force_reuse_rewrite
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_never_mutates_or_launches
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_relaunches_from_stored_phase_sizes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_renders_model_directives
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_uses_custom_big_epic_threshold
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_dry_run_does_not_snapshot_epic_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_launch_snapshots_authoritative_plan_and_overwrites_on_relaunch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_prelaunch_visibility_failure_never_reaches_agent_launcher
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_snapshot_failure_warns_and_launches_without_snapshot_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_snapshot_source_resolution_uses_non_vc_bead_store_root[local-.sase/sdd/plans/202607/epic.md-plans/202607/epic.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_snapshot_source_resolution_uses_non_vc_bead_store_root[sidecar-sase/repos/plans/202607/epic.md-202607/epic.md]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch.py::test_work_launches_and_passes_rendered_multi_prompt
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_expected_name_container_conflict_aborts_before_mutation[land-clan-container]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_expected_name_container_conflict_aborts_before_mutation[phase-clan-container]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_family_cleanup_failure_aborts_before_mutation[member-wipe-errors]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_family_cleanup_failure_aborts_before_mutation[residual-family-reservation]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[name-still-reserved]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[wipe-raises]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[wipe-reports-errors]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_wrappers.py::test_work_dry_run_regular_epic_renders_vcs_launch_wrappers
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_launch_wrappers.py::test_work_dry_run_renders_changespec_launch_wrappers
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_rollback_kills_partially_launched_agents
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_allows_already_ready_epic_and_launches_remaining_phases
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_checkpoint_failure_rolls_back_before_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_retry_does_not_unmark_already_ready_epic_on_launch_failure
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_rollback_restores_prior_in_progress_status
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_rolls_back_on_launch_failure
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_interrupted_phase_family_is_wiped_before_retry
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_relaunch_after_failure_joins_existing_epic_clan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_retry_allows_legacy_epic_clan_container_skip
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_stale_owner_round_trip_wipes_and_rewrites
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_bead_id_launch_uses_epic_lock_and_reports_only_phase_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_changespec_epic_errors_without_project_context
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_missing_bead_json_error_is_one_envelope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_non_plan_bead_json_error_is_one_envelope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_plain_plan_tier_json_error_is_one_envelope
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_rejects_non_plan_bead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_epic_validation.py::test_work_rejects_plain_plan_tier
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_creates_hierarchical_child_epic_from_managed_parent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_archive_boundary_failure_is_actionable_end_to_end
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_persists_durable_stage_timing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_rejects_malformed_header_block_before_lock_or_archive
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_parent_override_and_force_top_level
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_preview.py::test_bead_id_mode_rejects_parent_override
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_preview.py::test_bead_id_mode_rejects_plan_file_only_linking_options_as_json[--artifacts-dir-/tmp/planner-artifacts]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_preview.py::test_bead_id_mode_rejects_plan_file_only_linking_options_as_json[--cl-name-demo]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_preview.py::test_bead_work_help_describes_both_targets_and_options
    failed in 20260814T190042Z-ee6f3c7d302e-1508433-full-run.json (head ee6f3c7d302e)
    excluded by 8 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_json_output_is_one_stable_object
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_launch_mode_keeps_legacy_sizeless_epic_resumable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_publication.py::test_detached_store_no_push_preserves_linked_graph_without_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_publication.py::test_plan_file_publishes_graph_before_launch_and_reconciles_afterward
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_publication.py::test_synchronous_graph_push_failure_preserves_state_and_stops_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_resume.py::test_plan_file_launch_failure_rolls_back_for_resume
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_resume.py::test_plan_file_rejects_missing_linked_bead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_resume.py::test_plan_file_resume_reuses_linked_epic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_resume.py::test_retrying_original_file_preserves_archived_bead_link
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_resume.py::test_zero_spawn_after_publication_commits_and_publishes_rollback
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_neutral_gate_plan_archives_under_original_stem
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_mode_archives_prompt_link_per_expect_prompt_snapshot[False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_mode_archives_prompt_link_per_expect_prompt_snapshot[True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_mode_forwards_expect_prompt_snapshot_to_archive[False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_mode_forwards_expect_prompt_snapshot_to_archive[True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_refuses_poisoned_sidecar_before_archive_or_bead_open
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_rejects_preserved_archive_identity_mismatch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_store_contention.py::test_epic_preclaim_exhaustion_rolls_back_the_ready_flag
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_store_contention.py::test_task_preclaim_exhaustion_reports_holder_and_claims_nothing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_store_contention.py::test_task_preclaim_retries_past_a_contended_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_in_progress_task_with_live_assignee_is_idempotent_success
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_invalid_task_status_is_rejected_without_mutation[Status.CLAIMED]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_invalid_task_status_is_rejected_without_mutation[Status.CLOSED]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_stale_in_progress_task_cleans_up_before_mutation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_checkpoint_commits_and_pushes_before_return
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_checkpoint_reports_contention_timeout_before_no_remote
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_is_read_only
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_normalizes_legacy_sizeless_task_to_small
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.LARGE-@large_phase_worker-True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.MEDIUM-@medium_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.SMALL-@small_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.XLARGE-@xlarge_phase_worker-True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.XSMALL-@xsmall_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_json_reports_task_launch_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[Status.OPEN]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[Status.READY]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_task_work_persists_durable_stage_timing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_yes_does_not_skip_destructive_cleanup_confirmation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_zero_spawn_failure_restores_prior_task_state[checkpoint]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_work_task.py::test_zero_spawn_failure_restores_prior_task_state[launch]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestJsonlPersistence::test_a_legacy_row_without_the_key_imports
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestJsonlPersistence::test_import_updates_close_history_on_an_existing_row
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestJsonlPersistence::test_round_trip_preserves_every_field
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestJsonlPersistence::test_the_key_is_omitted_for_beads_that_were_never_reopened
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestJsonlPersistence::test_the_key_sits_between_resolution_and_description
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestSqliteMirror::test_a_corrupt_column_value_reads_as_an_empty_history
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestSqliteMirror::test_a_pre_column_database_migrates_to_an_empty_history
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestSqliteMirror::test_stored_and_read_back
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_close_history_storage.py::TestSqliteMirror::test_the_column_json_matches_the_wire_encoding
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_config.py::test_init_beads_end_to_end_uses_project_display_name_prefix
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_conflict_probe_retries_through_a_stale_index_lock
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_failed_stage_read_does_not_silently_drop_one_side
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_prefixed_store_page_conflict_is_still_unsupported
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_resolution_leaves_untouched_streams_alone
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_resolution_preserves_non_ascii_bytes_in_untouched_streams
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_event_stream_conflict_is_mergeable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_mixed_conflicts_are_refused
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_mixed_page_and_store_conflicts_resolve
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_page_conflict_accepts_upstream_deletion
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_page_only_conflict_takes_upstream_without_store_merge
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_conflict_resolver.py::test_root_store_readme_conflict_is_not_a_bead_conflict
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCloseIssue::test_close_issue
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_child_without_parent_fails_db_constraint
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_child
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_epic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_phase_with_changespec_metadata_fails
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_phase_with_patch_metadata_fails
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_plan_with_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_create_plan_with_patch_metadata
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_db.py::TestCreateAndGet::test_extended_phase_sizes_round_trip[PhaseSize.XLARGE]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_extended_phase_sizes_round_trip[PhaseSize.XSMALL]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_get_issue
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_get_nonexistent_returns_none
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_plan_with_parent_succeeds
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_ready_task_with_size_round_trips
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestCreateAndGet::test_refs_round_trip
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDeleteIssue::test_delete_cascades_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDeleteIssue::test_delete_cascades_dependencies
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDeleteIssue::test_delete_existing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDeleteIssue::test_delete_nonexistent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDependencies::test_add_and_get
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestDependencies::test_duplicate_dependency_fails
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestEpicChildren::test_get_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestEpicChildren::test_no_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestIsReadyToWork::test_default_is_false
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestIsReadyToWork::test_jsonl_roundtrip
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestIsReadyToWork::test_mark_ready_to_work
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestListIssues::test_filter_by_status
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestListIssues::test_filter_by_type
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestListIssues::test_list_all
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestModelField::test_clear_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestModelField::test_create_and_get_with_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestModelField::test_default_model_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestModelField::test_update_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestReadyAndBlocked::test_blocked_by_open_dep
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestReadyAndBlocked::test_in_progress_not_ready
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestReadyAndBlocked::test_ready_no_deps
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestReadyAndBlocked::test_unblocked_after_close
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestStats::test_stats
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestUpdateIssue::test_update_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestUpdateIssue::test_update_nonexistent_returns_none
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestUpdateIssue::test_update_patch_metadata
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_db.py::TestUpdateIssue::test_update_status
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestUpdateIssue::test_update_title
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db.py::TestUpdateIssueRejectsNothingDB::test_db_update_can_set_is_ready_to_work
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestMigrationAddsColumn::test_pre_changespec_db_gets_migrated
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestMigrationAddsColumn::test_pre_column_db_gets_migrated
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestMigrationAddsColumn::test_pre_model_db_gets_migrated
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestMigrationAddsColumn::test_pre_refs_db_gets_empty_reference_list
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestMigrationAddsColumn::test_pre_resolution_db_gets_nullable_constrained_column
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestSizeConstraintMigration::test_pre_size_db_adds_column_without_rebuilding_table
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_db_migrations.py::TestStatusConstraintMigration::test_current_db_schema_is_unchanged_on_reopen
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_from_plan.py::test_invalid_plan_creates_nothing_and_does_not_launch
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_from_plan.py::test_valid_plan_runs_real_bead_work_wave_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_jit_claim_integration.py::test_closed_rendered_bead_fails_before_model_callback[epic]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_jit_claim_integration.py::test_closed_rendered_bead_fails_before_model_callback[phase]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_jit_claim_integration.py::test_rendered_epic_preclaims_make_runner_lifecycle_quiet_noops[generic-cwd]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_jit_claim_integration.py::test_rendered_epic_preclaims_make_runner_lifecycle_quiet_noops[planned]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_epic_jit_claim_integration.py::test_wait_claim_survives_publication_lag_and_holds_until_promotion
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestConcurrentWorkspaces::test_counter_isolation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestConcurrentWorkspaces::test_two_instances_interleaved
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestDependencyChains::test_chain_a_b_c
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestDependencyChains::test_diamond_dependency
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_close_already_closed
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_close_nonexistent_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_doctor_reports_healthy
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_empty_project
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_list_filter_combined
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_phase_requires_parent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_plan_with_parent_is_valid
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_show_nonexistent_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEdgeCases::test_update_multiple_fields
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestEpicLifecycle::test_full_lifecycle
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestGitSyncWorkflow::test_sync_is_clean_after_sync
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestGitSyncWorkflow::test_sync_no_op_when_clean
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestGitSyncWorkflow::test_sync_stages_bead_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestJsonlRoundTrip::test_delete_db_reconstruct_from_jsonl
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestJsonlRoundTrip::test_jsonl_format_is_valid_json
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_integration.py::TestJsonlRoundTrip::test_jsonl_sorted_by_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_default_model_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_empty_db
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_includes_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_includes_dependencies
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_includes_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_includes_patch_metadata
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_jsonl.py::TestExport::test_export_refs_only_when_nonempty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestExport::test_export_sorted_by_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_creates_issues
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_empty_file
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_missing_changespec_metadata_defaults_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_missing_file
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_missing_model_defaults_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_refs_and_tolerates_missing_field
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_skips_corrupt_lines
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestImport::test_import_uses_one_transaction_and_skips_invalid_dependency
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestRoundTrip::test_export_import_roundtrip
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestRoundTrip::test_export_import_roundtrip_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl.py::TestRoundTrip::test_upsert_updates_existing
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl_golden_fixtures.py::test_corrupt_jsonl_fixture_skips_bad_lines
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl_golden_fixtures.py::test_empty_and_missing_jsonl_fixtures_import_as_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl_golden_fixtures.py::test_pre_changespec_metadata_schema_defaults_metadata_empty
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl_golden_fixtures.py::test_pre_is_ready_to_work_schema_defaults_flag_false
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_jsonl_golden_fixtures.py::test_pre_patch_metadata_schema_defaults_metadata_empty
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_model.py::TestIssueValidation::test_bug_id_without_patch_name_raises
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_model.py::TestIssueValidation::test_phase_with_patch_metadata_raises
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_model.py::TestIssueValidation::test_plan_with_patch_bug_id_is_valid
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_model.py::TestIssueValidation::test_plan_with_patch_name_is_valid
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_model.py::TestIssueValidation::test_task_with_patch_metadata_raises
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_plus_one_contract.py::test_core_create_requires_size_but_legacy_sizeless_task_still_loads
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_plus_one_contract.py::test_project_plus_one_creator_and_repeat_are_noops
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_plus_one_contract.py::test_project_plus_one_promotes_and_round_trips_all_persistence
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_plus_one_contract.py::test_project_rejects_plus_one_on_non_task_without_writes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_prefix_mint_guard.py::test_bead_create_reports_auto_prefix_repair
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_prefix_mint_guard.py::test_child_create_does_not_repair_key_prefix
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_prefix_mint_guard.py::test_custom_prefix_create_is_untouched
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_prefix_mint_guard.py::test_doctor_prefix_warning_disappears_after_auto_repair
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_prefix_mint_guard.py::test_top_level_create_repairs_key_prefix_before_minting
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_add_dependency
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_blocked
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_multiple
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_not_found
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_plan_rejects_open_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_plan_skips_already_closed_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_single
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_with_reason
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_close_with_resolution
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_cold_large_jsonl_store_reads_without_building_mirror
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_counter_persists_across_instances
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_and_update_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_and_update_phase_size
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_child
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_child_rejects_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_child_uses_local_child_counter
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_defaults_is_ready_to_work_false
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_epic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_epic_with_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_keeps_local_counter_when_config_is_ahead
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_phase_inherits_created_by_from_parent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_plan_and_filter_by_tier
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_records_explicit_created_by
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_uses_local_counter_when_sibling_has_allocations
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_create_without_created_by_falls_back_to_owner
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_doctor_clean
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_doctor_detects_orphan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_force_close_plan_records_parent_in_child_reason
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_force_close_requires_reason_and_non_done_resolution
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_get_epic_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_init_already_exists
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_init_creates_beads_dir
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_jsonl_persisted_after_create
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_list_all
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_list_filter_status
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_list_filter_type
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_mark_ready_to_work_flips_flag
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_mark_ready_to_work_idempotency_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_mark_ready_to_work_persists_to_jsonl
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_mark_ready_to_work_rejects_phase
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_mark_ready_to_work_unknown_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_read_commands_do_not_open_compatibility_mirror
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_ready
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_many_deduplicates_overlapping_and_repeated_requests
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_many_missing_id_is_atomic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_not_found
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_phase
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_plan_cascades_children
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_remove_updates_jsonl
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_root_level_store_round_trip
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_show
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_show_not_found
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_stats
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update_changespec_metadata
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update_not_found
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update_rejects_bug_id_without_changespec
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update_rejects_bug_id_without_patch
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_project.py::test_update_rejects_is_ready_to_work
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project.py::test_update_status
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_claim_failure_does_not_refresh_compatibility_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_claim_for_agent_launch_delegates_and_refreshes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_create_delegates_to_rust_mutation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_preclaim_epic_work_returns_typed_rollback
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_remove_many_delegates_and_refreshes_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_search_delegates_to_rust_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_show_delegates_to_rust_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_show_returns_issue_with_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_update_many_delegates_and_refreshes_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_wait_claim_methods_return_mutation_state[claim_for_agent_wait-claim_for_agent_wait-Status.CLAIMED-True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_project_rust_delegation.py::test_bead_project_wait_claim_methods_return_mutation_state[release_agent_claim-release_agent_claim-Status.OPEN-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_close_regression.py::test_a_closed_snoozed_bead_survives_replay_from_its_event_stream
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_close_regression.py::test_cli_close_closes_a_snoozed_bead_and_leaves_the_store_readable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_close_regression.py::test_gate_close_closes_a_snoozed_bead_and_leaves_the_store_readable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_close_regression.py::test_gate_ready_wakes_a_snoozed_bead_and_leaves_the_store_readable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_close_regression.py::test_gate_resnooze_defers_a_woken_bead_and_leaves_the_store_readable
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_lifecycle.py::test_snoozing_rejects_past_wake_times_and_non_task_beads
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_lifecycle.py::test_update_refuses_the_snoozed_status_shortcut
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_storage.py::TestSnoozeJsonlProjection::test_row_round_trips_and_omits_the_key_when_absent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_storage.py::TestSnoozeSqliteMirror::test_a_pre_snooze_mirror_migrates_without_losing_close_history
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_storage.py::TestSnoozeSqliteMirror::test_a_snoozed_row_survives_a_write_and_read
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_snooze_storage.py::TestSnoozeSqliteMirror::test_the_mirror_refuses_a_snoozed_row_without_a_record
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync.py::test_rebuild_from_jsonl_creates_db
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_claims.py::test_bead_sync_diagnostics_reports_recovery_residue_and_local_commits
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_claims.py::test_concurrent_claim_soak_preserves_commits_without_recovery
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_clean_rebase_repairs_stale_manifest_and_repeated_sync_is_noop
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_clean_rebase_with_invalid_stream_resets_completed_integration
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_concurrently_minted_bead_id_relocates_instead_of_wedging_sync
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_managed_sync_worker_invalid_stream_restores_exact_starting_state[corrupt]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_managed_sync_worker_invalid_stream_restores_exact_starting_state[rewrite]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_recovery.py::test_mixed_bead_and_non_bead_conflicts_abort_exactly
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_replay.py::test_generic_sdd_push_reconciles_same_stream_and_derived_files
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_replay.py::test_managed_sync_worker_converges_in_opposite_replay_directions
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_conflict_replay.py::test_managed_sync_worker_replays_deep_multi_commit_divergence
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[plans-embedded]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[repo-root]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_sync_workspace_prepare_regressions.py::test_push_bead_work_launch_publishes_root_layout_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_phase_inherits_parent_creator
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_plan_prefers_frontmatter_proposer
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_task_accepts_size_and_prints_type
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_task_records_acting_agent
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_task_requires_size
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_create_task_without_agent_records_store_owner
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_jsonl_round_trip_preserves_ready_task_size
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_ready_handler_uses_task_specific_empty_message
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_beads.py::test_ready_stats_and_detail_handlers_render_task_semantics
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_task_gate_actions.py::test_task_triage_launch_executes_real_command_translates_and_persists_task_id
    failed in 20260813T230047Z-c1b2724a1fc4-1799266-full-run.json (head c1b2724a1fc4)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_task_triage_lookup.py
    failed in 20260807T031144Z-0f7960d0853a-2671768-full-run.json (head 0f7960d0853a)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_task_triage_lookup.py::test_close_ready_task_persists_close_and_cancels_pending_gate
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestClosedBlockers::test_closed_blocker_is_rendered_as_a_bead_only_wait
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestClosedBlockers::test_in_epic_closed_blocker_does_not_gate
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestClosedBlockers::test_in_progress_phase_is_included
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestClosedBlockers::test_mixed_closed_and_non_closed_phases_render_only_remaining
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestClosedBlockers::test_out_of_epic_closed_blocker_is_accepted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestCrossEpicBlockerRejected::test_open_out_of_epic_blocker_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestCycleDetection::test_cycle_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestDelegatedPhases::test_land_waits_on_closed_delegated_and_launched_phase_beads
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestDelegatedPhases::test_retry_keeps_delegated_phase_as_bead_only_blocker
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestDiamond::test_diamond_render_snapshot
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestDiamond::test_three_waves_land_on_all_phases
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestEpicValidation::test_missing_epic_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestEpicValidation::test_no_open_phases_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestEpicValidation::test_phase_target_raises
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestIndependentFanOut::test_single_wave_land_waits_on_all
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestLinearChain::test_parent_plan_does_not_change_epic_launch_tag
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestLinearChain::test_three_waves_land_on_all_phases
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestMixedDAG::test_land_waits_on_earlier_parallel_phases_too
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestModelAndSizePropagationFromPayload::test_epic_model_flows_into_land_model
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestModelAndSizePropagationFromPayload::test_phase_model_flows_into_assignment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_epic_plan.py::TestModelAndSizePropagationFromPayload::test_phase_size_flows_into_assignment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_epic_work_segment_env_exports_snapshot_to_every_segment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_epic_work_segment_env_tracks_phase_then_land_bead_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_phase_agent_name_uses_bead_id
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_user_override_xprompt_names_propagate
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_vcs_and_changespec_wrappers_preserve_identical_bead_waits
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_vcs_and_patch_wrappers_preserve_identical_bead_waits
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_vcs_context_prefixes_every_regular_epic_segment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_changespec.py::TestChangeSpecRendering::test_bug_id_uses_keyword_pr_syntax
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_changespec.py::TestChangeSpecRendering::test_dependency_chain_wraps_only_first_phase_with_pr
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_changespec.py::TestChangeSpecRendering::test_independent_phases_only_first_gets_pr
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_changespec.py::TestChangeSpecRendering::test_single_phase_wraps_phase_and_land
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_changespec.py::TestPatchRendering::test_bug_id_uses_keyword_pr_syntax
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_rendering_changespec.py::TestPatchRendering::test_dependency_chain_wraps_only_first_phase_with_pr
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_rendering_changespec.py::TestPatchRendering::test_independent_phases_only_first_gets_pr
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_rendering_changespec.py::TestPatchRendering::test_single_phase_wraps_phase_and_land
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_big_epic_directive_resolves_configured_target
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_closed_phases_still_select_big_epic_lander_on_resume
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_epic_land_model_emits_on_land_segment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_land_model_wins_for_large_epic
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[large]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[legacy]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[medium]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 4 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[small]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[xlarge]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_explicit_model_wins_for_every_phase_size[xsmall]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[custom-above]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[custom-below]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[custom-exact]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[default-above]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[default-below]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_implicit_land_alias_uses_authored_phase_threshold[default-exact]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_mixed_phase_models_only_decorate_set_phases
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_model_does_not_inject_extra_directives
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_no_model_only_adds_role_alias_directives_over_baseline
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 4 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_model_emits_after_clan_and_tribe_before_plan
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_model_empty_renders_small_phase_worker_directive
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[None-@small_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[PhaseSize.LARGE-@large_phase_worker-True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[PhaseSize.MEDIUM-@medium_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[PhaseSize.SMALL-@small_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[PhaseSize.XLARGE-@xlarge_phase_worker-True]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_work_rendering_models.py::TestModelDirective::test_phase_size_controls_model_and_planning_handoff[PhaseSize.XSMALL-@xsmall_phase_worker-False]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_workspace_sidecar_bead_eviction.py::test_eviction_proceeds_for_a_fully_published_sidecar_bead_clone
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_workspace_sidecar_bead_eviction.py::test_eviction_refuses_to_trash_unpublished_sidecar_bead_commits
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead_statuses_for_project.py::test_bead_statuses_for_project_reads_requested_ids_from_canonical_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead_time_surface_coverage.py::test_cli_search_compact_row_carries_created_cell
    failed in 20260809T123141Z-7c7de9c9feda-2636397-full-run.json (head 7c7de9c9feda)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead_xprompt_tags.py::test_bead_worker_builtin_xprompts_do_not_author_wait_directives[bd/work_task-Can you complete the work for task bead {{ bead_id }}]
    failed in 20260808T164713Z-125b5c31b23a-23762-full-run.json (head 125b5c31b23a)
    excluded by 4 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead_xprompt_tags.py::test_bead_worker_builtin_xprompts_do_not_author_wait_directives[bd/work_task-Can you complete the work for the {{ bead_id }} sase task bead]
    failed in 20260808T172951Z-92f0ff3774ca-737391-full-run.json (head 92f0ff3774ca)
    excluded by 5 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead_xprompt_tags.py::test_builtin_task_prompt_routes_distinct_follow_ups_through_skill
    failed in 20260808T164713Z-125b5c31b23a-23762-full-run.json (head 125b5c31b23a)
    excluded by 4 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bug_links.py::test_find_bug_links_empty_id_never_matches_blank_fields
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bug_links.py::test_find_bug_links_filters_to_epics_and_matching_patches
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_changespec_refs_persistence.py::test_section_order_places_refs_between_status_and_commits
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_archives_closed_non_terminal_spec
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Archived (proj_1)]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Archived]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Reverted (proj_1)]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Reverted]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Submitted (proj_1)]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_closed_terminal_status_is_noop[Submitted]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_exit_zero_still_submits
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_other_nonzero_exit_is_noop[19]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_other_nonzero_exit_is_noop[1]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_other_nonzero_exit_is_noop[21]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_handle_cl_submitted_completion_other_nonzero_exit_is_noop[2]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_checks_runner.py::test_process_pending_checks_for_archives_on_closed_exit_code
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_chop_sdk.py::test_hook_builtin_uses_shared_runner_and_emits_noop_result
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_clipboard_format.py
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_agents.py::test_bulk_change_status_is_changespec_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_agents.py::test_jump_to_agent_changespec_requires_resolution
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_accept_proposal_requires_proposed_entry
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_agent_run_log_leader_command_requires_selected_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_app_edit_query_is_available_on_patches_stitches_plans_and_axe
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_changespecs.py::test_app_edit_query_is_available_on_prs_commits_plans_and_axe
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_changespecs.py::test_artifacts_copy_commands_follow_the_active_subtab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 4 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_changespecs.py::test_bug_commands_only_available_on_bugs_subtab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_clear_marks_only_when_marks_exist
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_copy_changespecs_pr_number_requires_pr
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_mail_visible_only_for_ready_status
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_plans_filter_command_is_available_only_on_plans
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 3 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_changespecs.py::test_rename_cl_hidden_for_reverted_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_reword_hidden_for_submitted_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_saved_query_picker_and_slots_are_pr_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_saved_query_slot_mode_command_is_pr_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_show_diff_hidden_when_changespec_has_no_pr_number
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_show_diff_hidden_when_no_cl_selected
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_changespecs.py::test_show_diff_visible_with_pr_number
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_scope.py::test_direct_fold_palette_commands_follow_active_context_scale
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_scope.py::test_fold_palette_commands_are_scoped_by_fold_surface
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_scope.py::test_metadata_sections_are_agents_only_and_forward_jump_is_all_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_availability_scope.py::test_show_help_palette_entry_is_available_across_tabs_and_artifacts
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_add_tag_command_is_contextual_wait_on_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_app_command_spec_uses_configured_key
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_bulk_change_status_command_is_changespec_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_copy_mode_commands_per_tab_scope
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_fold_mode_commands_cover_every_subkey
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_jump_commands_use_back_and_forward_defaults_on_every_tab
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_last_vcs_xprompt_editor_command_is_all_tab_agent_command
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_restore_prompt_stash_command_is_all_tab_at_keymap
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_run_workflow_command_is_contextual_retry_on_agents
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_show_help_command_is_global_question_mark_keymap
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_start_agent_from_changespec_command_uses_ctrl_space
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog.py::test_start_agent_home_command_uses_bare_space
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_agent_from_cl_leader_command_uses_space
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_agent_home_leader_command_uses_h
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_agent_run_log_leader_command_is_cl_only
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_build_command_catalog_includes_all_buckets
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_command_specs_are_well_formed
    failed in 20260814T213608Z-d3c5254ca8cb-2839258-full-run.json (head d3c5254ca8cb)
    excluded by 6 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_catalog_build.py::test_logs_command_is_keyless_and_global
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_models_panel_leader_command_uses_m
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_projects_command_is_keyless_and_global
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_prompt_history_edit_first_leader_command_uses_ctrl_g
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_repeat_last_leader_command_is_global
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_review_mentors_leader_command_uses_uppercase_c
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_tasks_command_is_keyless_and_global
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_update_sase_leader_command_uses_uppercase_u
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_build.py::test_visible_agent_folds_use_contextual_app_command
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_guards.py::test_every_builtin_mode_subkey_has_a_command_spec
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_guards.py::test_open_command_palette_command_is_always_present
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_catalog_guards.py::test_tree_navigation_command_tab_scopes
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_context_extraction.py::test_extract_context_changespecs_tab_handles_empty_list
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_context_extraction.py::test_extract_context_changespecs_tab_picks_selected_cs
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_palette_modal.py::test_modal_renders_nonempty_applicable_list
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_palette_wiring.py::test_extract_command_context_smoke_against_real_app
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_command_palette_wiring.py::test_palette_omits_inapplicable_axe_only_command_on_cls_tab
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_marker_repo_metadata.py::TestWriteResultMarkerRepoMetadata::test_persists_patch_without_diff_path
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_marker_repo_metadata.py::TestWriteResultMarkerRepoMetadata::test_persists_primary_commit_metadata_without_graph_relationships
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_marker_repo_metadata.py::TestWriteResultMarkerRepoMetadata::test_primary_commit_metadata_skips_noop_rewrite
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_result_marker.py::TestWriteResultMarker::test_resolver_failure_still_writes_complete_marker
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_result_marker.py::TestWriteResultMarker::test_writes_marker_with_all_fields
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_legacy_meta_new_cl
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_legacy_meta_new_pr_with_changespec
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_meta_changespec_direct
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_meta_changespec_strips_whitespace
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_returns_none_for_empty_output
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commit_workflow_changespec.py::TestGetMetaChangespecName::test_returns_none_for_none_output
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_commits_multiline_body.py
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_config_inventory.py::test_inventory_diagnoses_glossary_outside_project_local_config
    failed in 20260808T234629Z-65f82ccd9f52-1443127-full-run.json (head 65f82ccd9f52)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_agent_meta_wait_priority_scan_preserves_explicit_and_legacy_values
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_bounded_newest_first_limits_completed_without_hiding_incomplete
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_disable_prompt_step_markers
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_disable_raw_prompt_snippet
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_include_project_states_filters_scanner_projects
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_max_prompt_snippet_bytes_truncates
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_missing_root_returns_empty_snapshot
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_only_workflow_dirs_filters_records
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_options_round_trip_through_snapshot
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_scan_agent_artifact_dirs_honors_project_and_workflow_filters
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_scan_agent_artifact_dirs_reads_exact_unique_dirs
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_selective_marker_options_skip_payloads_but_keep_done_presence
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_snapshot_serializes_to_json
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_unreadable_artifact_dir_is_counted
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_unsupported_workflow_dirs_are_skipped
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_waiting_runner_slot_fields_match_filesystem_marker
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_records_are_sorted_deterministically
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_scan_returns_one_record_per_artifact_dir
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_stats_count_decode_errors
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_done_record_parses_done_marker
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_failed_record_carries_error_and_traceback
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_mentor_dir_is_walked
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_non_repeat_done_record_defaults_repeat_stop_fields
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_repeat_stopped_record_carries_repeat_stop_fields
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_retried_records_link_via_lineage_fields
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_errors.py::test_malformed_agent_meta_is_skipped
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_errors.py::test_waiting_marker_decode_error_does_not_crash
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_index.py::test_bounded_source_clan_context_reconciles_through_index
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_index.py::test_index_query_honors_project_filters
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_agent_meta
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_auto_approve_plan_action
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_clan_attributes_through_scan_and_index
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_commit_diff_path_through_scan_and_index
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_output_variables_through_scan_and_index
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_wait_completed_at
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_linked_repos_survive_scan_index_and_enrichment
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_prefers_canonical_agent_meta_tribe
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_scalar_plan_submitted_at_is_preserved
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_home_running_record_has_running_marker
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_workflow_root_record_has_state_and_steps
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_workflow_state_hidden_is_parsed
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_bead_mutation.py::test_append_note_facade_returns_issue_and_repairs_projection
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_claim_for_agent_launch_converts_issue_and_reassigns
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_claim_for_agent_launch_maps_missing_and_preserves_specific_failures
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_mutation_facade_jsonl_matches_python_after_each_operation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_mutation_facade_writes_events_and_repairs_jsonl_projection
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_preclaim_epic_work_converts_batch_and_returns_prior_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_ready_to_work_errors_map_to_python_exceptions
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_remove_many_facade_returns_unique_expanded_removals
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_mutation.py::test_wait_claim_facade_claims_idempotently_and_releases
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_bead_read.py::test_doctor_reads_jsonl_without_requiring_sqlite
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_core_facade/test_parser.py::test_parse_project_bytes_returns_wire_records
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 5 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_parser.py::test_parse_project_bytes_uses_rust_binding
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 5 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_against_python_golden
    failed in 20260809T053910Z-a4a340679580-1820642-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260809T051421Z-a4a340679580-1489822.json (head a4a340679580)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_calls_rust_binding
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_missing_binding_raises
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_missing_extension_raises
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_real_extension_parity
    failed in 20260809T053910Z-a4a340679580-1820642-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260809T051421Z-a4a340679580-1489822.json (head a4a340679580)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_plan_status_transition_rust_error_surfaces
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_status.py::test_transition_patch_status_uses_planner_facade
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_golden.py::test_archive_corpus_wire_json_snapshot
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_golden.py::test_patch_wire_json_snapshot
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_notification_store.py::test_fixture_generator_matches_committed_contract_fixture
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_archive_action_from_archive_under_no_validate
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_archive_action_none_within_archive_class
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_archive_action_none_within_main_class
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_archive_action_to_archive_on_submitted
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_archived_terminal_no_further_transitions
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_build_status_transition_request_reads_parent_status
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_draft_to_ready_no_suffix_no_strip_clears_mentors
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_draft_to_ready_with_suffix_strips_and_clears_mentors
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_invalid_transition_validate_false_allows
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_invalid_transition_validate_true_rejects
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_legacy_ready_to_mail_suffix_stripped
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_parent_constraint_skipped_for_reverted_branch
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_parent_ready_does_not_block_mailed
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_parent_wip_blocks_child_to_mailed
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_ready_to_draft_appends_suffix_and_sets_mentor_draft
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_ready_to_draft_blocked_by_invalid_children
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_ready_to_draft_picks_lowest_free_suffix
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_request_round_trips_through_json
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_reverted_terminal_no_further_transitions
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_status_field_read_wire_constructs
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_status_field_update_wire_constructs
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_submitted_terminal_no_further_transitions
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_unknown_status_rejected_under_validation
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_wip_to_draft_no_suffix_no_mentor
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_wip_to_ready_blocked_by_sibling_unreverted_children
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_wip_to_ready_with_suffix_strips_and_reverts_siblings
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_status_wire.py::test_workspace_suffix_does_not_block_validation
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_wire.py::test_empty_patch_collections_become_empty_lists
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_wire.py::test_patch_to_wire_full_round_trip
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_wire.py::test_patch_wire_from_dict_treats_missing_lists_as_empty
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_deltas_parsing.py::test_deltas_round_trip_parse_then_format
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_deltas_parsing.py::test_parse_deltas_all_three_change_types
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_deltas_persistence.py
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_directives_split_models.py::test_split_prompt_for_models_preserves_alias_kwargs_per_alt_branch
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dismissed_agent_lifecycle.py::test_full_lifecycle_dismiss_then_revive_named_agent
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dismissed_agent_lifecycle.py::test_same_day_two_named_foo_get_unique_dismissed_names_then_revive
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dismissed_bundle_index.py::test_dismissed_bundle_index_legacy_summary_fields
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_dismissal_merge.py::test_load_agents_async_merges_external_dismissals_before_snapshot
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_external_dismissal_merge.py::test_load_agents_async_merges_post_history_tier1_in_worker
    failed in 20260807T184430Z-b473a10d0989-713771-full-run.json (head b473a10d0989)
    excluded by 1 scoped run(s), first 20260807T190738Z-b473a10d0989-1067870.json (head b473a10d0989)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_external_mirror_issues.py::test_mirrored_status_round_trip_records_each_transition
    failed in 20260812T171555Z-59967cc062a7-1769253-full-run.json (head 59967cc062a7)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_mirror_issues.py::test_status_transitions_are_limited_by_note_budget_and_converge
    failed in 20260812T171555Z-59967cc062a7-1769253-full-run.json (head 59967cc062a7)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_mirror_issues.py::test_upstream_close_appends_exactly_one_note_across_three_passes
    failed in 20260812T171555Z-59967cc062a7-1769253-full-run.json (head 59967cc062a7)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_mirror_issues.py::test_upstream_reopen_reopens_mirrored_bead
    failed in 20260812T171555Z-59967cc062a7-1769253-full-run.json (head 59967cc062a7)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_classifier_parity.py::test_external_pr_classifier_python_rust_parity
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_author_globs_narrows_adoption_case_insensitively
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_budget_exhaustion_defers_without_advancing_cursor
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_closed_unmerged_pr_maps_local_patch_to_archived
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_default_head_ref_filters_drop_release_bot_prs
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_dry_run_reports_refresh_without_writing
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_dry_run_writes_nothing_and_does_not_advance_cursor
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_empty_filters_by_default_adopt_every_author
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_filter_change_forces_full_pass_even_when_incremental_otherwise
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_malformed_provider_pr_defers_cursor_and_writes_nothing
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_open_external_patch_becomes_submitted_and_archived_on_merge
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_external_pr_sync.py::test_refresh_mutation_budget_defers_without_advancing_cursor
    failed in 20260812T174656Z-688eec2bda77-2715983-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260811T123619Z-c388b560cfc3-2937495.json (head c388b560cfc3)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_followup_prompt_helpers.py::test_with_feedback_unknown_parent_errors
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_completed_clan_fork_expands_during_post_wait_runner_setup
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_clan_fork_injects_prompts_without_member_replies
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_family_fork_injects_each_completed_member_reply_once
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_tribe_fork_dispatches_to_clan_context_builder
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_gate_cli_answer.py::test_secret_input_reaches_the_command_and_is_redacted_in_json
    failed in 20260808T043435Z-20752def224e-1477226-full-run.json (head 20752def224e)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_gate_e2e_smoke.py::test_e2e_epic_plan_retains_single_approve_control
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_gate_e2e_smoke.py::test_e2e_tale_plan_gate_structure_and_branches
    failed in 20260812T174517Z-688eec2bda77-2649306-full-run.json (head 688eec2bda77)
    excluded by 1 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_hooks_kill.py::test_kill_and_persist_with_running_agents
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_hooks_kill.py::test_kill_and_persist_with_running_hooks
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 10 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_hooks_reset_dollar.py::test_log_fn_receives_messages
    failed in 20260809T031429Z-2634fb4759db-242185-full-run.json (head 2634fb4759db)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_hooks_reset_dollar.py::test_mix_dollar_and_non_dollar_hooks
    failed in 20260809T031429Z-2634fb4759db-242185-full-run.json (head 2634fb4759db)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_hypothesis_property.py
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_app_bindings.py::test_build_app_bindings_number_artifacts_and_prefix_saved_queries
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_app_bindings.py::test_build_app_bindings_priority
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_keymaps_app_bindings.py::test_build_app_bindings_uses_config_keys
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_keymaps_app_bindings.py::test_build_app_bindings_uses_ctrl_space_agent_binding
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_keymaps_app_bindings.py::test_fallback_bindings_match_numbered_artifacts_and_saved_query_picker
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_defaults.py::test_pr_facing_binding_meta_uses_pr_labels
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_keymaps_defaults.py::test_zoom_and_agents_fold_defaults_are_in_sync_with_help
    failed in 20260810T182947Z-b67a8420f22d-159966-full-run.json (head b67a8420f22d)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_display_help.py::test_help_copy_sections_advertise_copy_as_palette
    failed in 20260811T133657Z-050264c7c98f-4052985-full-run.json (head 050264c7c98f)
    excluded by 1 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_e2e.py::test_ctrl_at_dispatches_repeat_agent_binding_not_home_space
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_keymaps_e2e.py::test_default_query_shortcuts_follow_the_context_matrix
    failed in 20260810T203904Z-64ddea98a879-2986364-full-run.json (head 64ddea98a879)
    excluded by 2 scoped run(s), first 20260810T172630Z-3eddffba9232-3254141.json (head 3eddffba9232)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_e2e.py::test_leader_space_dispatches_current_selection_and_h_dispatches_home
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result0-4-No agent found]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result1-5-already completed]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result2-5-Could not find PID]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result3-6-Permission denied]
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_gate_option_inputs.py::test_execute_mobile_gate_action_secret_field_is_redacted_in_response
    failed in 20260808T043435Z-20752def224e-1477226-full-run.json (head 20752def224e)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_gateway.py::test_parser_accepts_mobile_helper_bridge_patch_tags
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_helper_beads.py::test_beads_bridge_returns_resolved_plan_path_when_available
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_all_known_projects_ignores_disabled_projects
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_all_known_projects_ignores_orphan_bead_dirs
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_filters_explicit_project_status_type_and_tier
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_lists_ready_task_beads_by_default_and_by_filter
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_uses_only_first_canonical_project_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_uses_remembered_device_project_context
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_show_bridge_does_not_search_extra_project_stores
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_show_bridge_omits_refs_for_a_bead_without_any
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_show_bridge_returns_detail
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_show_bridge_returns_not_found_exit_code
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_beads.py::test_beads_show_bridge_returns_stored_references_it_cannot_resolve
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_mobile_helper_changespec_tags.py::test_patch_tags_bridge_projects_wire_shape_and_limit
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_helper_changespec_tags.py::test_patch_tags_bridge_rejects_invalid_limit
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_helper_changespec_tags.py::test_patch_tags_bridge_returns_skipped_structurally
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_helpers.py::test_xprompt_catalog_bridge_returns_structured_projection
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_notifications_bridge.py::test_execute_mobile_task_triage_reports_registered_action_kind
    failed in 20260813T230047Z-c1b2724a1fc4-1799266-full-run.json (head c1b2724a1fc4)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_alias_rendering.py::test_state_tag_implicit_concrete_size_worker
    failed in 20260810T165146Z-47b2a74aa305-2364658-full-run.json (head 47b2a74aa305)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_alias_rendering.py::test_state_tag_implicit_role
    failed in 20260810T165146Z-47b2a74aa305-2364658-full-run.json (head 47b2a74aa305)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_gates.py::test_gate_presentation_color_reaches_the_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_clamps_out_of_range_index
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_copies_current_attachment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_shortens_home_path
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_uses_recoverable_delivery_policy
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_warns_without_files
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_action_bindings.py::test_copy_file_path_warns_without_highlighted_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_bulk_dismiss_persists_once_removes_rows_and_rebuilds_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_cancel_dismiss_notification_clears_pending
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_confirm_dismiss_notification_dismisses_pending_item
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_final_visible_notification_highlights_previous_visual_row
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_last_tab_row_highlights_first_row_after_tab_fallback
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_notification_direct_for_non_plan_question
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_notification_requires_confirmation_for_launch_approval
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_notification_requires_confirmation_for_plan_question
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_dismiss_actions.py::test_dismiss_notification_requires_confirmation_for_task_triage
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_apostrophe_back_highlights_previous_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_apostrophe_without_history_highlights_first_visual
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_dispatches_uppercase_hint_character_without_dismiss
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_escape_cancels_without_dismiss
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_invalid_key_cancels_without_changing_highlight
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_on_key_stops_valid_hint_without_dismiss
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_pilot_keeps_modal_open_and_moves_highlight
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_resets_file_index_and_refreshes_preview
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_jump_then_enter_activates_highlighted_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_jump.py::test_notification_two_character_hint_waits_and_cleans_up
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_cancel_clears_bulk_pending
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_dismiss_last_row_in_active_tag_falls_back_to_nearest_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_marked_row_label_has_marker_prefix
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_next_prev_tag_tab_cycles_without_general_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_panel_and_hyphenated_tag_labels_are_humanized
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_switching_tag_tabs_clears_marks_and_pending_confirms
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_toggle_mark_adds_id_to_marked_set
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_toggle_mark_removes_id_when_already_marked
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_x_with_marks_bulk_dismisses_all_marked
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_x_with_marks_including_plan_question_requires_confirmation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mark_and_tabs.py::test_x_without_marks_unchanged_behavior
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_agent_completion_label_omits_redundant_sender_and_action_badge
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_bulk_completion_after_modal_close_does_no_widget_work
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_bulk_state_task_failure_leaves_modal_state_untouched
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_bulk_state_task_rejects_overlapping_mutation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_error_label_keeps_sender_and_error_badge
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_press_s_pushes_snooze_picker_and_passes_callback
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_single_snooze_stale_row_does_not_show_false_success
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_single_snooze_submits_tracked_background_write
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_snooze_callback_none_is_cancellation
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_snooze_callback_with_datetime_uses_until_label
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_snooze_callback_with_timedelta_calls_mark_snoozed
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_snooze_with_marks_cancellation_keeps_marks_and_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_snooze_with_marks_uses_one_picker_and_bulk_call
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_styled_label_includes_snooze_badge_when_snoozed
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_styled_label_uses_asterisk_for_unread_unmuted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_styled_label_uses_tilde_prefix_for_muted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_moves_row_to_muted_tab_and_highlights_replacement
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_prunes_stale_marks_and_falls_back_to_highlight
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_sets_muted_and_rebuilds
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_unmutes_when_already_muted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_with_marks_bulk_mutes_marked_rows_once
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_with_marks_unmutes_and_cancels_snoozes
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_toggle_mute_with_mixed_marks_converges_to_muted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_unmute_from_muted_tab_highlights_remaining_muted_row
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_mute_snooze.py::test_unmute_on_snoozed_clears_snooze_and_toasts
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_question_pane.py::test_awaiting_question_pane_contains_identity_prompt_and_options
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_notification_modal_question_pane.py::test_display_file_dispatches_question_before_empty_attachment_state
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_question_pane.py::test_question_highlight_uses_answer_focused_footer
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_active_tab_renders_flat_newest_first_without_section_rows
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_active_tag_filters_rows_but_preserves_original_option_ids
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_all_tagged_notifications_open_on_first_tag_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_compat_sectioned_options_wrapper_matches_flat_options
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_declared_panel_routes_task_triage_out_of_hitl
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_declared_panels_sort_after_hitl_and_before_other_tabs
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_dismiss_no_ops_when_no_notification_is_selected
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_equal_timestamps_preserve_insertion_order
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_error_notifications_share_errors_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_general_tab_excludes_tagged_notifications
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_get_selected_index_returns_none_for_legacy_header_like_option
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_hitl_actions_share_hitl_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_invalid_stored_panel_falls_back_to_existing_routing[]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_invalid_stored_panel_falls_back_to_existing_routing[__internal]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_invalid_stored_panel_falls_back_to_existing_routing[bad panel!]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_invalid_stored_panel_falls_back_to_existing_routing[errors]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_jump_hints_render_on_notification_rows_in_visual_order
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_literal_muted_tag_does_not_collide_with_synthetic_muted_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_malformed_timestamp_does_not_crash_and_sinks
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_mixed_tab_order_places_muted_last
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_multi_tag_notification_is_owned_by_its_first_tag_only
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_muted_declared_panel_routes_only_to_muted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_muted_error_notification_appears_only_in_muted_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_muted_hitl_notification_appears_only_in_muted_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_muted_tagged_notification_appears_only_in_muted_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_panel_and_tag_collision_is_counted_once_and_sorted_as_panel
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_resurfaced_row_sorts_as_recent_activity
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_snoozed_gate_leaves_its_declared_panel_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_snoozed_notification_appears_in_snoozed_tab_with_badge
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_snoozed_tab_carries_the_next_wake_time
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_styled_label_includes_compact_tag_badges
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_synthetic_tabs_take_precedence_over_stored_tags
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_tag_strip_click_posts_selected_tag
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_tag_tabs_order_counts_and_capitalized_labels
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_toggle_mute_no_ops_when_no_notification_is_selected
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sections.py::test_visual_notification_index_order_matches_flat_render
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sent_at.py::TestCyclingAttachmentsLeavesSentAtLineUnchanged::test_next_file_changes_title_not_sent_line
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sent_at.py::TestDisplayFileUpdatesSentAtLine::test_no_files_attached
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sent_at.py::TestDisplayFileUpdatesSentAtLine::test_question_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sent_at.py::TestDisplayFileUpdatesSentAtLine::test_report_notification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_sent_at.py::TestDisplayFileUpdatesSentAtLine::test_text_attachment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_a_snoozed_gate_leaves_its_declared_panel_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_a_two_tag_row_owns_exactly_one_tab
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_a_wake_time_splits_snoozed_out_of_muted
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_every_row_lands_in_exactly_one_of_the_built_tabs
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_modal_tabs_match_the_snapshot_tabs
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_snapshot_tab_counts_agree_with_the_legacy_counters
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_modal_tags.py::test_the_pure_tab_key_agrees_with_the_core_classification
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_notification_toasts.py::TestFormatNotificationToast::test_jump_to_changespec_failure
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_parallel_agent_family_metadata.py::test_clan_wait_and_fork_resolve_only_after_every_member_completes
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_reference_resolver_integration.py::test_local_archive_plan_resolves_identically_across_surfaces
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_reference_resolver_integration.py::test_store_plan_resolves_identically_across_surfaces[absolute]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_reference_resolver_integration.py::test_store_plan_resolves_identically_across_surfaces[month-relative]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_reference_resolver_integration.py::test_store_plan_resolves_identically_across_surfaces[sdd]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_reference_resolver_integration.py::test_store_plan_resolves_identically_across_surfaces[sidecar]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_reference_resolver_integration.py::test_store_plan_resolves_identically_across_surfaces[typed]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_plan_validate_diagnostics.py::test_cli_passes_through_every_core_diagnostic_family[epic----\ntier: epic\ngoal: outcome\ntitle: 42\npatch: ''\nbug_id: nope\nphases: []\n---\nbody\n-expected_codes8-1]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_validate_diagnostics.py::test_cli_passes_through_every_core_diagnostic_family[tale----\ntier: tale\ngoal: Small outcome\ntitle: Ignored\nphases: nonsense\npatch: ''\nbug_id: nope\n---\nbody\n-expected_codes7-0]
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_pr_report_diff_path.py::TestPrReportStep::test_emits_diff_path_and_pr_metadata
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_pr_status.py::test_is_parent_submitted_parent_not_submitted
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_procs_facade.py::test_resolve_proc_ref_handles_unique_short_unknown_and_ambiguous
    failed in 20260814T003238Z-62fb94129662-3549628-full-run.json (head 62fb94129662)
    excluded by 2 scoped run(s), first 20260810T222227Z-0ccd7f844731-800799.json (head 0ccd7f844731)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_reasoning_effort_metadata_enrichment.py::test_rust_scan_projects_reasoning_effort
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_list_reverted_patches
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_diff_not_found
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_hg_import_fails
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_sase_commit_fails
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_sase_hg_update_fails
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_success
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_restore.py::test_restore_patch_with_parent
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_calls_kill_and_persist
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_fails_on_diff_error
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_fails_on_prune_error
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_fails_with_children
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_fails_with_nonexistent_workspace
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_fails_without_workspace_dir
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_succeeds_without_cl
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_changespec_success
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_calls_kill_and_persist
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_fails_on_diff_error
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_fails_on_prune_error
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_fails_with_children
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_fails_with_nonexistent_workspace
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_fails_without_workspace_dir
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_succeeds_without_cl
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revert.py::test_revert_patch_success
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_run_agent_runner_bead.py::test_claim_helper_claims_in_tree_store_and_refreshes_projection
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_commits_managed_store_and_allows_reassignment
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_leaves_schema_two_sidecar_layout_unchanged
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_materializes_cold_split_beads_store
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_routes_split_store_commit_and_publish_to_beads_sidecar
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_wraps_bead_mutation_errors[closed]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_wraps_bead_mutation_errors[missing]
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_agent_runner_bead.py::test_claim_helper_wraps_store_and_commit_failures
    failed in 20260807T142035Z-57a045cfc6a7-3676976-full-run.json (head 57a045cfc6a7)
    excluded by 1 scoped run(s), first 20260807T143139Z-57a045cfc6a7-3788989.json (head 57a045cfc6a7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_run_workflow_visibility.py::test_write_workflow_state_is_visible_to_tier1_loader
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_carries_done_metadata
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_includes_done_and_failed
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_per_project_cap
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_skips_noop_outcome
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_empty_when_processes_dead
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_filters_done_and_dead
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_reports_waiting_marker
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_skips_appears_as_agent_false
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_skips_non_parallel_parent_timestamp_followups
    failed in 20260813T182030Z-a7433cfe70a4-626513-full-run.json (head a7433cfe70a4)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root
    failed in 20260807T153249Z-64922e12acef-1077169-full-run.json (head 64922e12acef)
    excluded by 5 scoped run(s), first 20260806T072850Z-531138373fc4-767279.json (head 531138373fc4)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_sdd_file_writes.py::test_write_sdd_files_uses_local_sase_sdd_relative_links
    failed in 20260807T153249Z-64922e12acef-1077169-full-run.json (head 64922e12acef)
    excluded by 5 scoped run(s), first 20260806T072850Z-531138373fc4-767279.json (head 531138373fc4)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_sdd_file_writes.py::test_write_sdd_files_uses_sdd_relative_links
    failed in 20260807T153249Z-64922e12acef-1077169-full-run.json (head 64922e12acef)
    excluded by 5 scoped run(s), first 20260806T072850Z-531138373fc4-767279.json (head 531138373fc4)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_select_tests_tool.py::test_json_format_prints_the_manifest
    failed in 20260806T201818Z-48bd0009ebdc-1524219-full-run.json (head 48bd0009ebdc)
    excluded by 3 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: contract-set-always, contract-set-only
  tests/test_select_tests_tool.py::test_manifest_destination_is_overridable
    failed in 20260806T201818Z-48bd0009ebdc-1524219-full-run.json (head 48bd0009ebdc)
    excluded by 3 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: contract-set-always, contract-set-only
  tests/test_sidecar_ref_config.py::test_effective_sidecar_ref_policies_apply_document_defaults_and_overrides
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_sidecar_ref_config.py::test_sidecar_ref_deprecated_path_globs_alias_is_reported
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_sidecar_ref_config.py::test_sidecar_ref_use_and_equivalent_inline_normalize_identically
    failed in 20260813T134648Z-dc9da557631a-591508-full-run.json (head dc9da557631a)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_status_state_machine_field_updates.py::test_transition_to_draft_blocked_when_child_is_ready
    failed in 20260809T031429Z-2634fb4759db-242185-full-run.json (head 2634fb4759db)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_status_state_machine_transitions.py::test_draft_to_ready_blocked_when_sibling_has_children
    failed in 20260809T031429Z-2634fb4759db-242185-full-run.json (head 2634fb4759db)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suffix_github_safe.py::test_suffix_append_rekeys_alias_for_immutable_branch
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suffix_github_safe.py::test_suffix_append_renames_for_mutable_branch
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suffix_github_safe.py::test_suffix_strip_renames_for_mutable_branch
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suffix_github_safe.py::test_suffix_strip_writes_alias_for_immutable_branch
    failed in 20260809T071856Z-50f8961ac7cb-2988223-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suffix_transform_persistence.py
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_over_budget_selection_escalates_rather_than_queueing_for_a_lease
    failed in 20260807T224841Z-0c084068cfa7-3855043-full-run.json (head 0c084068cfa7)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_over_budget_selection_runs_at_a_leased_width_and_releases_it
    failed in 20260807T224841Z-0c084068cfa7-3855043-full-run.json (head 0c084068cfa7)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_scoped_run_takes_no_token_while_the_pool_is_exhausted
    failed in 20260806T201818Z-48bd0009ebdc-1524219-full-run.json (head 48bd0009ebdc)
    excluded by 6 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_temporary_llm_override_agent_meta.py::test_launch_alias_overrides_persist_to_meta_and_process_env
    failed in 20260810T140825Z-354d8c19f9aa-3085874-full-run.json (head 354d8c19f9aa)
    excluded by 3 scoped run(s), first 20260806T185529Z-8fcc2520fb17-132917.json (head 8fcc2520fb17)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_cost.py::test_committed_cost_budgets_are_valid
    failed in 20260812T114646Z-9b5bff5bd310-700082-full-run.json (head 9b5bff5bd310)
    excluded by 4 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_cost.py::test_committed_cost_budgets_cover_calibration_ci_run
    failed in 20260812T114646Z-9b5bff5bd310-700082-full-run.json (head 9b5bff5bd310)
    excluded by 4 scoped run(s), first 20260806T110049Z-5458d839236a-1841807.json (head 5458d839236a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_timezone_display_artifacts.py::test_files_rows_and_groups_use_configured_timezone
    failed in 20260812T130622Z-62951abcb4a2-1701111-full-run.json (head 62951abcb4a2)
    excluded by 1 scoped run(s), first 20260809T151355Z-3ec02513e7da-2018448.json (head 3ec02513e7da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_timezone_runtime_consistency.py::test_by_date_changespec_grouping_reference_uses_configured_tz
    failed in 20260808T232939Z-bcf5748b6bf7-1051423-full-run.json (head bcf5748b6bf7)
    excluded by 2 scoped run(s), first 20260806T163604Z-a15f409dd113-2188655.json (head a15f409dd113)
    distinct change sets: 1
    rules across those runs: contract-set-always
  tests/test_vcs_log_filter_query.py::test_canonical_query_round_trip_property
    failed in 20260813T131922Z-d04e8cfcccef-24337-full-run.json (head d04e8cfcccef)
    excluded by 6 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_provider_hookspec.py::TestHookspecMethodsExist::test_all_provider_methods_have_hookspecs
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_provider_hookspec.py::TestHookspecRegistration::test_hookspecs_are_firstresult
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_provider_hookspec.py::TestHookspecSignatures::test_parameter_names_match
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_provider_plugin_manager.py::TestNonTrivialDefaults::test_resolve_revision_delegates_when_handled
    failed in 20260809T071148Z-50f8961ac7cb-2889475-full-run.json (head 50f8961ac7cb)
    excluded by 3 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_xprompt_mru.py::test_load_launchable_drops_refs_that_no_longer_resolve
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_xprompt_mru.py::test_load_launchable_keeps_entries_when_resolution_index_unavailable
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 4 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/workflows/test_commit_add.py
    failed in 20260809T051800Z-a4a340679580-1523202-full-run.json (head a4a340679580)
    excluded by 2 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_color_output_uses_shared_role_styles
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_definition_unknown_is_explicit_placeholder
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_empty_sections_are_omitted
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_non_skill_omits_the_slash_row
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_plain_layout_covers_every_xprompt_section
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_skill_shows_both_the_reference_and_the_slash_name
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_render.py::test_workflow_steps_render_bodies_and_explicit_elision
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_config_raw_is_exact_entry_span_with_crlf
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_hosted_resolver_failure_is_a_warning
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_lookup_miss_suggests_copyable_reference_markers
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_markdown_raw_and_body_line_are_exact
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_memory_record_projects_kind_and_type
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_record_json_projection_is_complete_and_serializable
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_references_are_resolved_and_deduplicated_in_document_order
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_step_record_reuses_shared_type_and_output_schema
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_unreadable_definition_degrades_to_warning
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_cli_show_resolve.py::test_workflow_wins_over_shadowed_xprompt
    failed in 20260808T201835Z-25be8cc68334-703639-full-run.json (head 25be8cc68334)
    excluded by 1 scoped run(s), first 20260808T004614Z-7bbd82a47ed7-1287209.json (head 7bbd82a47ed7)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost

  Known flakes are already excluded from this count (see
  flake-suppressed below); a non-zero count here means the selection
  heuristic itself is unsound as tuned. Raise SASE_TEST_SELECTION_DEPTH
  to 3 or add the missed tests to tests/contract_manifest.txt, then
  re-measure.

flake-suppressed: 367 (6197 scoped run/failure matches)
  Excluded from false negatives above: each failed across unrelated
  change sets and had an independent full-run pass between failures.
  See reproducible_flake_nodeids in tests/_test_selection_health.py.
  tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_anchors_pdf_markdown_source_path
  tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion
  tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
  tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_reappears_after_last_visible_agent_disappears
  tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_visible_after_empty_load_direct_agents_tab
  tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_visible_after_empty_load_tab_switch
  tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_visible_for_hidden_only_workflow
  tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
  tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
  tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version
  tests/ace/tui/test_artifacts_beads_navigation.py::test_detail_scroll_reserves_its_gutter_so_the_width_never_oscillates
  tests/ace/tui/test_artifacts_list_navigation.py::test_bugs_fast_navigation_restores_issue_focus_and_ignores_links
  tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
  tests/ace/tui/test_artifacts_list_navigation.py::test_non_pr_jump_history_is_isolated_and_model_changes_cancel_hints
  tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
  tests/ace/tui/test_artifacts_plans_loading.py::test_snapshot_reads_beads_only_to_partition_plan_documents
  tests/ace/tui/test_artifacts_scaffold.py::test_first_artifacts_entry_activates_default_without_hidden_collection
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_ignores_saved_query_cache_invalidates
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_reappears_after_last_patch_disappears
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_after_empty_startup
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_saved_queries_exist
  tests/ace/tui/test_changespecs_onboarding.py::test_patches_onboarding_visible_when_specs_are_filtered_out
  tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[ace-query]
  tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[configured]
  tests/ace/tui/test_commits_config.py::test_known_startup_project_is_displayed_before_first_collection[inferred]
  tests/ace/tui/test_commits_pane_filters.py::test_commits_negative_repo_reconciles_before_collection_and_persists
  tests/ace/tui/test_commits_pane_rendering.py::test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints
  tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state
  tests/ace/tui/test_family_member_relaunch.py::test_completed_family_member_relaunch_dismisses_only_selected_child
  tests/ace/tui/test_footer_visibility.py::test_custom_footer_status_visible_in_normal_one_line_state
  tests/ace/tui/test_footer_visibility.py::test_leader_footer_final_grid_row_visible
  tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked
  tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes
  tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_loads_grouped_incoming_commits
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_renders_components_and_shortens_home
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_renders_partial_repository_failure
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_scrolls_incoming_commits[size0]
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_scrolls_overflowing_preview
  tests/ace/tui/test_plugin_action_confirm_modal.py::test_plugin_action_modal_summarizes_long_grouped_incoming_commits
  tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py::test_all_clis_history_groups_runs_and_collapses_nonexecuted_entries
  tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py::test_history_trigger_badges[admin_center-A]
  tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py::test_history_trigger_badges[cli-CLI]
  tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py::test_history_trigger_badges[comprehensive-,U]
  tests/ace/tui/test_plugins_browser_pane_agent_clis_history.py::test_history_trigger_badges[unknown-\u2014]
  tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_detail_shows_lazy_incoming_commits
  tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_core_panel_shows_incoming_commits
  tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_core_panel_shows_versions_and_update_status
  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_dev_update_shows_all_commit_groups
  tests/ace/tui/test_plugins_browser_pane_update.py::test_plugins_pane_editable_update_uses_dev_preview_and_restart
  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_directory_key_spelling_also_resolves
  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_offers_project_local_xprompts_by_canonical_name
  tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
  tests/ace/tui/test_task_mirror.py::test_mirror_counts_global_detached_and_this_sessions_command_tasks
  tests/ace/tui/test_task_mirror.py::test_mirror_counts_global_detached_tasks_without_a_tui_session
  tests/ace/tui/test_task_mirror.py::test_mirror_flushes_only_new_log_lines
  tests/ace/tui/test_task_mirror.py::test_mirror_tick_reconciles_and_mirrors_progress
  tests/ace/tui/test_task_mirror.py::test_mirror_writes_row_log_and_terminal_update
  tests/ace/tui/test_task_mirror.py::test_progress_tick_does_not_terminalize_before_finish
  tests/ace/tui/test_tasks_pane_store.py::test_following_a_live_store_row_bypasses_the_mtime_cache[success-True]
  tests/ace/tui/test_tasks_store_rows.py::test_all_sessions_scope_marks_dead_sessions
  tests/ace/tui/test_tasks_store_rows.py::test_default_scope_keeps_detached_rows_globally
  tests/ace/tui/test_tasks_store_rows.py::test_default_scope_keeps_this_session_and_unattributed_rows
  tests/ace/tui/test_tasks_store_rows.py::test_only_the_detail_row_loads_its_log_tail
  tests/ace/tui/test_tasks_store_rows.py::test_unchanged_store_is_reported_without_rereading_rows
  tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent
  tests/ace/tui/widgets/test_agent_display_xprompt.py::TestAgentXPromptRendering::test_agent_xprompt_highlights_warm_catalog_skills
  tests/ace/tui/widgets/test_prompt_at_prefix_completion.py::TestAtPrefixIntegration::test_at_prefix_directory_drilldown
  tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_k_on_glossary_term_pushes_glossary_preview_card
  tests/ace/tui/widgets/test_prompt_panel_header.py::test_family_header_renders_followup_role_attribution
  tests/ace/tui/widgets/test_prompt_panel_header.py::test_header_renders_skill_uses_without_memory_reads
  tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles
  tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_ctrl_space_action_is_gated_only_while_prompt_is_mounted
  tests/agents_sync/test_committed_plan_header.py::test_committed_plan_header_refresh_is_idempotent
  tests/artifact_refs/test_context.py::test_context_assembles_dynamic_document_role_and_namespaces
  tests/fakey/test_retry_pipeline_e2e.py::test_kill_during_retry_wait_stops_before_another_subprocess
  tests/fakey/test_retry_pipeline_e2e.py::test_retryable_failure_then_success_records_lifecycle_and_nudge
  tests/fakey/test_runner_slots_e2e.py::test_child_is_exempt_while_repeat_roots_stay_capped
  tests/gate_conformance/test_gate_conformance.py::test_gate_conformance[ace-legacy_shared_input]
  tests/gate_conformance/test_gate_conformance.py::test_gate_conformance[cli-legacy_shared_input]
  tests/main/test_agent_prompts_handler.py::test_prompt_show_prints_whole_archive_document
  tests/main/test_agents_tribe_handler.py::test_agents_show_reports_project_for_sharded_agent
  tests/main/test_artifact_cli_lifecycle.py::test_prune_dry_run_writes_nothing_and_apply_trashes_only_plan
  tests/main/test_init_memory_glossary.py::test_memory_plan_generates_project_glossary_before_agents
  tests/main/test_plan_show_render.py::test_color_never_has_no_ansi_and_always_does
  tests/main/test_project_handler_list_show.py::TestListAndShow::test_project_handler_imports_in_fresh_interpreter
  tests/main/test_task_handler_kill.py::test_kill_reports_bad_task_references
  tests/main/test_task_handler_kill.py::test_kill_resolves_prefix_and_marks_active_task_killed
  tests/main/test_task_handler_kill.py::test_kill_terminal_task_is_a_json_noop
  tests/main/test_task_handler_list.py::test_bare_task_command_announces_the_list_delegation
  tests/main/test_task_handler_list.py::test_list_all_includes_other_sessions_with_a_dead_chip
  tests/main/test_task_handler_list.py::test_list_applies_status_project_tag_query_and_limit
  tests/main/test_task_handler_list.py::test_list_empty_store_renders_the_run_hint
  tests/main/test_task_handler_list.py::test_list_filters_by_repeated_kind_and_detached_shorthand
  tests/main/test_task_handler_list.py::test_list_json_envelope_is_stable
  tests/main/test_task_handler_list.py::test_list_keeps_detached_tasks_global_even_for_an_explicit_session
  tests/main/test_task_handler_list.py::test_list_reconciles_a_supervisor_that_never_reported
  tests/main/test_task_handler_list.py::test_list_renders_a_row_and_glyph_for_every_status
  tests/main/test_task_handler_list.py::test_list_running_filter_matches_pending_and_running
  tests/main/test_task_handler_list.py::test_list_scopes_to_this_session_and_unattributed
  tests/main/test_task_handler_run.py::test_run_attributes_the_task_to_the_resolved_session
  tests/main/test_task_handler_run.py::test_run_derives_a_label_from_the_command
  tests/main/test_task_handler_run.py::test_run_detached_creates_a_global_detached_kind
  tests/main/test_task_handler_run.py::test_run_json_emits_the_created_task
  tests/main/test_task_handler_run.py::test_run_prints_the_id_and_the_follow_hint
  tests/main/test_task_handler_run.py::test_run_quiet_prints_only_the_task_id
  tests/main/test_task_handler_run.py::test_run_session_none_leaves_the_task_unattributed
  tests/main/test_task_handler_run.py::test_run_truncates_a_very_long_derived_label
  tests/main/test_task_handler_run.py::test_run_wait_json_keeps_stdout_parseable
  tests/main/test_task_handler_run.py::test_run_wait_json_quiet_still_emits_only_the_envelope
  tests/main/test_task_handler_run.py::test_run_wait_reports_a_signalled_command_like_a_shell
  tests/main/test_task_handler_run.py::test_run_wait_streams_output_and_propagates_the_exit_code[raise SystemExit(0)-0]
  tests/main/test_task_handler_run.py::test_run_wait_streams_output_and_propagates_the_exit_code[raise SystemExit(3)-3]
  tests/main/test_task_handler_show.py::test_show_follow_json_waits_for_the_finished_task
  tests/main/test_task_handler_show.py::test_show_follow_on_a_terminal_task_returns_immediately
  tests/main/test_task_handler_show.py::test_show_json_includes_the_task_and_log
  tests/main/test_task_handler_show.py::test_show_names_detached_global_ownership
  tests/main/test_task_handler_show.py::test_show_output_only_prints_the_log_without_chrome
  tests/main/test_task_handler_show.py::test_show_renders_detail_and_log_tail
  tests/main/test_task_handler_show.py::test_show_reports_unknown_short_and_ambiguous_references
  tests/main/test_update_command_dev.py::test_dev_update_runs_backend_and_restarts_axe
  tests/main/test_update_command_mode_switch.py::test_mode_switch_same_target_is_friendly_noop
  tests/main/test_update_command_upgrade.py::test_upgrade_quiet_prints_one_line
  tests/main/test_update_command_upgrade.py::test_upgrade_runs_expected_argv_and_renders
  tests/main/test_update_command_upgrade.py::test_upgrade_tolerates_missing_receipt
  tests/main/test_var_handler.py::test_var_list_renders_canonical_block_form
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_attaches_to_the_lane_and_transfers_the_claim
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_omits_the_fork_prefix_when_the_starter_never_settles
  tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_completes_when_grandchild_holds_stdout
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_kills_the_whole_process_group_on_timeout
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_child_closes_stdio
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_continuous_output
  tests/notification_store/test_snooze_e2e_matrix.py::TestSnoozeStateMatrix::test_resnooze_replaces_the_single_scheduled_deadline
  tests/notification_store/test_state_updates.py::TestMarkTabRead::test_empty_store
  tests/notification_store/test_state_updates.py::TestMarkTabRead::test_general_tab_uses_untagged_rows
  tests/notification_store/test_state_updates.py::TestMarkTabRead::test_marks_only_targeted_tab
  tests/notification_store/test_state_updates.py::TestMarkTabRead::test_skips_already_read_and_is_idempotent
  tests/notification_store/test_state_updates.py::TestMarkTabRead::test_uses_metadata_only_update
  tests/plan_show/test_load.py::test_canonical_reference_present_in_root_and_none_outside
  tests/plan_show/test_load.py::test_load_ambiguity_candidate_builds_lightweight_row
  tests/plan_show/test_resolve.py::test_miss_carries_close_match_suggestions
  tests/plan_show/test_resolve.py::test_rung_ref_resolves_plans_reference
  tests/sdd/test_hosted_links.py::test_plan_url_accepts_legacy_repo_relative_reference
  tests/sdd/test_hosted_links.py::test_plan_url_resolves_logical_reference_to_blob_url
  tests/sdd/test_hosted_links.py::test_resolution_is_cached_across_many_plans
  tests/sdd/test_plan_archive.py::test_archive_rebases_authored_parent_for_destination
  tests/sdd/test_plan_associations.py::test_artifact_metadata_paths_collapse_to_one_plan_key
  tests/sdd/test_plan_associations.py::test_builds_sorted_rendering_records_from_one_history_walk
  tests/sdd/test_plan_associations.py::test_epic_rollup_ignores_parent_cycles
  tests/sdd/test_plan_associations.py::test_epic_rollup_reads_bullets_and_legacy_parent_without_changing_tales
  tests/sdd/test_plan_associations.py::test_family_members_collapse_to_one_lane_with_member_link_hint
  tests/sdd/test_plan_associations.py::test_history_failure_keeps_artifact_results_and_reports_diagnostic
  tests/sdd/test_plan_associations.py::test_legacy_member_tag_uses_its_recorded_destination
  tests/sdd/test_plan_links_refresh.py::test_refresh_dry_run_write_and_second_write_are_idempotent
  tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_declare_lifecycle_coverage
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations
  tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
  tests/test_agent_group_revival_e2e.py
  tests/test_agent_group_revival_e2e.py::test_lowercase_s_dispatches_by_active_tab
  tests/test_agent_group_revival_e2e.py::test_mark_save_preview_and_revive_saved_agent_group
  tests/test_agent_group_revival_e2e.py::test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader
  tests/test_agents_index_cli.py::test_index_unknown_subcommand_prints_maintenance_usage
  tests/test_axe_cli.py::test_handle_axe_lumberjack_list_prints_descriptions
  tests/test_axe_cli.py::test_handle_axe_lumberjack_list_prints_only_configured_wait_runners
  tests/test_axe_cli.py::test_handle_axe_lumberjack_list_verbose_controls_description_body[False]
  tests/test_axe_cli.py::test_handle_axe_lumberjack_list_verbose_controls_description_body[True]
  tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_worker_alias[large]
  tests/test_axe_run_agent_exec_plan_followup_model_selection.py::TestPlanFollowupModelSelection::test_coder_followup_uses_tale_size_worker_alias[xlarge]
  tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  tests/test_bead/test_cli_changespec.py::test_create_plan_stores_sibling_workspace_plan_path_relative_to_primary
  tests/test_bead/test_cli_doctor.py::test_confirmed_fix_uses_update_events_and_one_aggregate_commit
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_full]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_json]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json]
  tests/test_bead/test_cli_plus_one.py::test_plus_one_accepts_shorthand_refs_and_promotes_draft_task
  tests/test_bead/test_cli_plus_one.py::test_plus_one_repeat_is_noop_with_note_guidance
  tests/test_bead/test_cli_plus_one.py::test_plus_one_verified_after_close_reopens_and_clears_assignee
  tests/test_bead/test_cli_plus_one.py::test_plus_one_withheld_reopen_reports_and_leaves_bead_closed
  tests/test_bead/test_cli_resolution.py::test_find_beads_location_split_sidecar_uses_repository_root
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_appends_the_bead_created_cell
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_colors_type_glyphs
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_renders_aligned_type_glyphs
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_snippet_uses_matching_line
  tests/test_bead/test_cli_search.py::test_handle_bead_search_full_reuses_show_rendering
  tests/test_bead/test_cli_search.py::test_handle_bead_search_json_outputs_envelope
  tests/test_bead/test_cli_search.py::test_handle_bead_search_no_matches_is_success
  tests/test_bead/test_cli_show_json.py::test_search_json_keeps_phase_size_in_machine_output
  tests/test_bead/test_cli_snooze.py::test_cancel_returns_the_bead_to_ready
  tests/test_bead/test_cli_snooze.py::test_plus_ones_and_reason_are_recorded_and_summarized
  tests/test_bead/test_cli_snooze.py::test_relative_duration_snoozes_and_reports_the_resolved_wake_time
  tests/test_bead/test_cli_work_contention_regressions.py::test_bead_mutation_lock_wait_honors_a_short_configured_deadline
  tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout
  tests/test_bead/test_cli_work_epic_summary.py::TestEpicSummarySmokeExercises::test_epic_work_clan_panel_renders_persisted_summary
  tests/test_bead/test_cli_work_epic_summary.py::TestEpicSummarySmokeExercises::test_epic_work_launch_uses_snapshot_without_refreshing_stale_clone
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_creates_links_and_launches_in_tree
  tests/test_bead/test_cli_work_from_plan.py::test_plan_file_parent_dry_run_previews_id_and_missing_parent_has_remedy
  tests/test_bead/test_cli_work_from_plan_concurrency.py::test_concurrent_plan_file_launches_serialize_through_terminal_push
  tests/test_bead/test_cli_work_from_plan_concurrency.py::test_plan_link_write_and_commit_exclude_recovery_writer
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_dry_run_is_pure_and_previews_waves
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[custom-above]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[custom-below]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[custom-exact]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[default-above]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[default-below]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[default-exact]
  tests/test_bead/test_cli_work_from_plan_preview.py::test_plan_file_preview_matches_threshold_aware_land_model[explicit-model]
  tests/test_bead/test_cli_work_from_plan_publication.py::test_git_sidecar_fresh_clone_sees_complete_graph_before_launch
  tests/test_bead/test_cli_work_from_plan_store.py::test_plan_file_mode_uses_sidecar_store
  tests/test_bead/test_close_history_cli_integration.py::test_history_reports_the_close_history_field_transition
  tests/test_bead/test_close_history_cli_integration.py::test_search_finds_an_archived_close_reason_end_to_end
  tests/test_bead/test_close_history_end_to_end.py::test_a_plus_one_reopen_archives_the_close_reason
  tests/test_bead/test_db_migrations.py::TestSizeConstraintMigration::test_legacy_three_size_db_is_relaxed_and_idempotent
  tests/test_bead/test_db_migrations.py::TestStatusConstraintMigration::test_pre_task_ready_db_is_migrated_and_idempotent
  tests/test_bead/test_design_ref_repair.py::test_repair_planner_migrates_resolving_legacy_and_keeps_canonical
  tests/test_bead/test_design_ref_repair.py::test_repair_planner_recovers_malformed_canonical_by_basename
  tests/test_bead/test_design_ref_repair.py::test_repair_planner_uses_owner_then_root_order
  tests/test_bead/test_epic_from_plan.py::test_bead_link_write_projects_prompt_section_when_snapshot_is_expected_but_absent
  tests/test_bead/test_epic_from_plan.py::test_bead_link_write_reprojects_prompt_section
  tests/test_bead/test_epic_from_plan.py::test_create_and_launch_maps_frontmatter_in_order
  tests/test_bead/test_epic_from_plan.py::test_creation_failure_removes_epic_and_restores_plan
  tests/test_bead/test_epic_from_plan.py::test_epic_and_phases_share_resolved_plan_creator[acting-agent-fallback]
  tests/test_bead/test_epic_from_plan.py::test_epic_and_phases_share_resolved_plan_creator[recorded-proposer]
  tests/test_bead/test_epic_from_plan.py::test_epic_and_phases_share_resolved_plan_creator[store-owner-fallback]
  tests/test_bead/test_epic_from_plan.py::test_epic_creation_rollback_respects_runner_spawn_boundary[partial-spawn]
  tests/test_bead/test_epic_from_plan.py::test_epic_creation_rollback_respects_runner_spawn_boundary[post-launch-commit]
  tests/test_bead/test_epic_from_plan.py::test_epic_creation_rollback_respects_runner_spawn_boundary[zero-spawn]
  tests/test_bead/test_epic_from_plan.py::test_existing_bead_link_refuses_duplicate_creation
  tests/test_bead/test_epic_from_plan.py::test_failed_forward_plan_commit_removes_graph_without_launch
  tests/test_bead/test_jsonl_golden_fixtures.py::test_current_schema_fixture_imports_hierarchy_dependencies_and_metadata
  tests/test_bead/test_plus_one_presentation.py::test_plus_one_badge_evidence_search_stats_and_json_agree
  tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree
  tests/test_bead/test_prefix_mint_guard.py::test_plan_file_work_repairs_prefix_and_reports_it
  tests/test_bead/test_snooze_gate.py::test_bead_snooze_gate_preview_carries_the_real_snooze_note
  tests/test_bead/test_snooze_lifecycle.py::test_cancel_snooze_returns_the_bead_to_ready
  tests/test_bead/test_snooze_lifecycle.py::test_plus_one_target_wakes_the_bead_with_the_preset_note
  tests/test_bead/test_snooze_lifecycle.py::test_snooze_round_trips_through_every_persistence_surface
  tests/test_bead_sync_external_cli.py::test_dry_run_prints_planned_creations_and_mutates_nothing
  tests/test_bead_sync_external_cli.py::test_dry_run_prints_planned_status_transitions
  tests/test_bead_sync_external_cli.py::test_output_shows_closed_and_reopened_counts_when_nonzero
  tests/test_bead_sync_external_cli.py::test_output_shows_filtered_count_when_nonzero
  tests/test_clan_summary_persistence.py::test_plan_race_refresh_replaces_identity_fallback_with_complete_plan
  tests/test_clan_summary_script_execution.py::test_generic_plan_summary_entry_point_uses_epic_environment_fallback
  tests/test_command_context_extraction.py
  tests/test_command_palette_e2e.py
  tests/test_command_palette_wiring.py
  tests/test_commit_hooks.py::test_run_commit_hook_prints_phase_specific_output_tail
  tests/test_commit_workflow_publication.py::test_publication_warning_names_drop_command_for_retired_backlog
  tests/test_commit_workflow_publication.py::test_publication_warning_names_quarantined_backlog
  tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical
  tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom
  tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget
  tests/test_core_facade/test_notification_store.py::test_real_extension_mark_tab_read_scopes_to_one_tab
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: automatic-Details\n\nSASE_TYPE=sase init]
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: legacy-Details\n\nSASE_AGENT=sase-1]
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: tracked-Details\n\nSASE_TYPE=stitch\nSASE_BEAD=sase-1]
  tests/test_core_vcs_log.py::test_parse_computes_auto_origin_from_footer
  tests/test_core_vcs_log.py::test_parse_computes_origin_from_footer
  tests/test_external_mirror_issues.py::test_creation_budget_defers_then_converges_next_pass
  tests/test_external_pr_mirror.py
  tests/test_file_hook_cli.py::test_file_hook_list_empty_state
  tests/test_file_hook_cli.py::test_file_hook_list_renders_all_fields
  tests/test_followup_prompt_helpers.py::test_with_feedback_parent_default_is_multi_prompt_segment_local
  tests/test_followup_prompt_helpers.py::test_with_feedback_xprompt_defaults_parent_from_family_attach
  tests/test_followup_prompt_helpers.py::test_with_feedback_xprompt_expands_from_parent_artifacts
  tests/test_fork_workflow.py::test_embedded_bare_resume_loads_resolved_chat_path
  tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork(planner, coder)]
  tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork:planner,coder]
  tests/test_fork_workflow.py::test_embedded_single_parent_fork_keeps_legacy_envelope
  tests/test_fork_workflow.py::test_inline_deferred_fork_survives_workspace_removal_and_late_preprocessing
  tests/test_gate_cli_show.py::test_show_json_reports_declared_inputs_branches_and_actions
  tests/test_gate_cli_show.py::test_show_prints_a_readable_summary_of_the_decision_surface
  tests/test_gate_cli_show.py::test_show_reports_a_cancelled_gate
  tests/test_gate_cli_show.py::test_show_reports_the_terminal_status_of_an_answered_gate
  tests/test_incoming_commits.py::test_incoming_commits_renderer_states
  tests/test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit
  tests/test_keymaps_registry_loading.py::test_stitches_action_override_wins_over_legacy_commits_alias
  tests/test_mobile_helper_beads.py::test_beads_list_bridge_lists_known_project_beads
  tests/test_mobile_helper_bridge_smoke.py::test_mobile_helper_bridge_smoke_all_helpers_with_temp_project_and_update
  tests/test_notification_gate_cli.py::test_gate_wait_prints_stable_answered_json_and_human_summary
  tests/test_output.py::test_escape_markup_in_log_fn
  tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor
  tests/test_plan_approve_cli.py::test_plan_approve_cli_prints_monitor_follow_hint
  tests/test_plan_command_handler.py::test_plan_command_rejects_invalid_or_auto_mismatched_plan_without_side_effects[# Plan\n\nbody\n-None-tale-frontmatter-missing]
  tests/test_plan_command_handler.py::test_plan_command_rejects_invalid_or_auto_mismatched_plan_without_side_effects[---\ntier: epic\ntitle: Empty epic\ngoal: Deliver it\nphases: []\n---\n# Plan\n-None-epic-phases-empty]
  tests/test_plan_command_handler.py::test_plan_command_rejects_invalid_or_auto_mismatched_plan_without_side_effects[---\ntier: tale\ngoal: '   '\n---\n# Plan\n-None-tale-value-empty]
  tests/test_plan_command_handler.py::test_plan_command_rejects_legacy_sizeless_tale_in_authoring_mode
  tests/test_plan_search_render.py::test_color_auto_on_non_tty_has_no_ansi
  tests/test_plan_search_render.py::test_color_never_strips_ansi
  tests/test_plan_search_render.py::test_compact_shows_highlighted_snippet_line
  tests/test_plan_search_render.py::test_compact_single_source_footer_omits_breakdown
  tests/test_plan_validate.py::test_cli_rejects_malformed_header_block_with_location_bearing_diagnostic
  tests/test_plan_validate.py::test_explain_precedes_human_results_for_both_tiers_on_success_and_failure[---\ntier: epic\ntitle: Strict plan validation\ngoal: Plans are validated before execution\nparent_bead: sase-parent.2\nphases:\n  - id: core\n    title: Core validator\n    depends_on: []\n    description: "core: build the shared validation engine."\n    size: medium\n  - id: cli\n    title: CLI integration\n    depends_on: [core]\n    description: "cli: wire the validator into the command."\n    size: large\n---\n# Plan\n\nImplement it.\n-An epic requires a title and a non-empty ordered phase list:\n\n```yaml\n---\ntier: epic\ntitle: Workspace GC rewrite\ngoal: >\n  Stale workspace checkouts are garbage-collected safely, and reclaim progress is visible.\nphases:\n  - id: core\n    title: GC planner and safety checks\n    depends_on: []\n    size: medium\n    description: "core: implement workspace selection and safety guards."\n  - id: cli\n    title: sase workspace gc command\n    depends_on: [core]\n    size: small\n    description: "cli: add the CLI flow and progress reporting."\n  - id: smoke\n    title: End-to-end GC smoke exercises\n    depends_on: [cli]\n    size: xsmall\n    description: "smoke: exercise successful and guarded cleanup."\n---\n# Plan: Descriptive title\n\nDescribe the implementation.\n```\n\nPhase IDs must be unique slugs. Dependencies may only name earlier-listed phases; do not use self, duplicate, unknown,\nor forward references. Give every phase a `description` that starts with that phase's own `id` followed by `: `, then\nbriefly summarizes the phase's section of the plan body. Do not quote or repeat the section title \u2014 the phase's `title`\nalready names that section \u2014 and do not reference the plan file itself because `sase bead show` already displays it.\nEvery phase must declare `size: xsmall | small | medium | large | xlarge`. Choose it after reading\n`sase/memory/sase_sizes.md` with the `/sase_memory_read` skill; that note owns the size meanings, plan-first behavior,\nand model routing rules.\n\nA phase's `model` is optional. Set it explicitly only when the user's prompt requested a specific model. For a phase\nwith no requested model, omit it so size-derived routing can choose the default. The optional top-level `model` selects\nthe tale follow-up or the epic's land agent.\n\nSASE owns the plan's provenance header block; do not author it. SASE writes and reconciles\nthe leading `PROMPT`, `PARENT`, `BEAD`, `AGENTS`, and `COMMITS` Markdown bullets itself, and `sase plan links refresh`\nkeeps them current. A hand-authored bullet that deviates from the canonical form is a validation error, not a style\nchoice: a link-shaped section (`PLAN`, `PROMPT`, `PARENT`, `BEAD`) must be a bolded key followed by exactly one\nMarkdown link and nothing else, and a list-shaped section (`AGENTS`, `ARTIFACTS`, `COMMITS`) must be a bare bolded key\nwhose entries are indented bullets.\nIn particular, name a parent plan through the `PARENT` bullet SASE writes, never through a `parent:` frontmatter\nproperty: that property is deprecated and is migrated into the bullet.-False]
  tests/test_plan_validate.py::test_explain_precedes_human_results_for_both_tiers_on_success_and_failure[---\ntier: epic\ntitle: Strict plan validation\ngoal: Plans are validated before execution\nparent_bead: sase-parent.2\nphases:\n  - id: core\n    title: Core validator\n    depends_on: []\n    description: "core: build the shared validation engine."\n    size: medium\n  - id: cli\n    title: CLI integration\n    depends_on: [core]\n    description: "cli: wire the validator into the command."\n    size: large\n---\n# Plan\n\nImplement it.\n-An epic requires a title and a non-empty ordered phase list:\n\n```yaml\n---\ntier: epic\ntitle: Workspace GC rewrite\ngoal: >\n  Stale workspace checkouts are garbage-collected safely, and reclaim progress is visible.\nphases:\n  - id: core\n    title: GC planner and safety checks\n    depends_on: []\n    size: medium\n    description: "core: implement workspace selection and safety guards."\n  - id: cli\n    title: sase workspace gc command\n    depends_on: [core]\n    size: small\n    description: "cli: add the CLI flow and progress reporting."\n  - id: smoke\n    title: End-to-end GC smoke exercises\n    depends_on: [cli]\n    size: xsmall\n    description: "smoke: exercise successful and guarded cleanup."\n---\n# Plan: Descriptive title\n\nDescribe the implementation.\n```\n\nPhase IDs must be unique slugs. Dependencies may only name earlier-listed phases; do not use self, duplicate, unknown,\nor forward references. Give every phase a `description` that starts with that phase's own `id` followed by `: `, then\nbriefly summarizes the phase's section of the plan body. Do not quote or repeat the section title \u2014 the phase's `title`\nalready names that section \u2014 and do not reference the plan file itself because `sase bead show` already displays it.\nEvery phase must declare `size: xsmall | small | medium | large | xlarge`. Choose it after reading\n`sase/memory/sase_sizes.md` with the `/sase_memory_read` skill; that note owns the size meanings, plan-first behavior,\nand model routing rules.\n\nA phase's `model` is optional. Set it explicitly only when the user's prompt requested a specific model. For a phase\nwith no requested model, omit it so size-derived routing can choose the default. The optional top-level `model` selects\nthe tale follow-up or the epic's land agent.\n\nSASE owns the plan's provenance header block; do not author it. SASE writes and reconciles\nthe leading `PROMPT`, `PARENT`, `BEAD`, `AGENTS`, and `COMMITS` Markdown bullets itself, and `sase plan links refresh`\nkeeps them current. A hand-authored bullet that deviates from the canonical form is a validation error, not a style\nchoice: a link-shaped section (`PLAN`, `PROMPT`, `PARENT`, `BEAD`) must be a bolded key followed by exactly one\nMarkdown link and nothing else, and a list-shaped section (`AGENTS`, `ARTIFACTS`, `COMMITS`) must be a bare bolded key\nwhose entries are indented bullets.\nIn particular, name a parent plan through the `PARENT` bullet SASE writes, never through a `parent:` frontmatter\nproperty: that property is deprecated and is migrated into the bullet.-True]
  tests/test_plan_validate.py::test_explain_precedes_human_results_for_both_tiers_on_success_and_failure[---\ntier: tale\ntitle: Strict plan validation\ngoal: Ship strict plan validation\nsize: small\n---\n# Plan\n\nImplement it.\n-A tale requires this frontmatter shape:\n\n```yaml\n---\ntier: tale\ntitle: Focused capability rollout\ngoal: Describe the outcome this plan will achieve.\nsize: medium\n---\n# Plan: Descriptive title\n\nDescribe the implementation.\n```\n\nEvery tale must declare `size`. Read `sase/memory/sase_sizes.md` with the `/sase_memory_read` skill before choosing it;\nthat note owns the size meanings, plan-first behavior, and model routing rules. Set `model` explicitly only when the\nuser's prompt requested a specific model.\n\nSASE owns the plan's provenance header block; do not author it. SASE writes and reconciles\nthe leading `PROMPT`, `PARENT`, `BEAD`, `AGENTS`, and `COMMITS` Markdown bullets itself, and `sase plan links refresh`\nkeeps them current. A hand-authored bullet that deviates from the canonical form is a validation error, not a style\nchoice: a link-shaped section (`PLAN`, `PROMPT`, `PARENT`, `BEAD`) must be a bolded key followed by exactly one\nMarkdown link and nothing else, and a list-shaped section (`AGENTS`, `ARTIFACTS`, `COMMITS`) must be a bare bolded key\nwhose entries are indented bullets.\nIn particular, name a parent plan through the `PARENT` bullet SASE writes, never through a `parent:` frontmatter\nproperty: that property is deprecated and is migrated into the bullet.-False]
  tests/test_plan_validate.py::test_explain_precedes_human_results_for_both_tiers_on_success_and_failure[---\ntier: tale\ntitle: Strict plan validation\ngoal: Ship strict plan validation\nsize: small\n---\n# Plan\n\nImplement it.\n-A tale requires this frontmatter shape:\n\n```yaml\n---\ntier: tale\ntitle: Focused capability rollout\ngoal: Describe the outcome this plan will achieve.\nsize: medium\n---\n# Plan: Descriptive title\n\nDescribe the implementation.\n```\n\nEvery tale must declare `size`. Read `sase/memory/sase_sizes.md` with the `/sase_memory_read` skill before choosing it;\nthat note owns the size meanings, plan-first behavior, and model routing rules. Set `model` explicitly only when the\nuser's prompt requested a specific model.\n\nSASE owns the plan's provenance header block; do not author it. SASE writes and reconciles\nthe leading `PROMPT`, `PARENT`, `BEAD`, `AGENTS`, and `COMMITS` Markdown bullets itself, and `sase plan links refresh`\nkeeps them current. A hand-authored bullet that deviates from the canonical form is a validation error, not a style\nchoice: a link-shaped section (`PLAN`, `PROMPT`, `PARENT`, `BEAD`) must be a bolded key followed by exactly one\nMarkdown link and nothing else, and a list-shaped section (`AGENTS`, `ARTIFACTS`, `COMMITS`) must be a bare bolded key\nwhose entries are indented bullets.\nIn particular, name a parent plan through the `PARENT` bullet SASE writes, never through a `parent:` frontmatter\nproperty: that property is deprecated and is migrated into the bullet.-True]
  tests/test_plan_validate.py::test_failure_human_output_is_location_bearing_and_self_teaching
  tests/test_plan_validate.py::test_plan_validate_rejects_legacy_sizeless_tale_in_authoring_mode
  tests/test_plan_validate.py::test_valid_human_output_and_quiet_mode
  tests/test_plan_validate_diagnostics.py::test_missing_and_non_utf8_files_are_validation_failures
  tests/test_plugin_cli_install.py::test_install_runs_full_set_plus_new_plugin
  tests/test_plugin_cli_list.py::test_render_editable_update_available_uses_dev_versions_and_sase_update
  tests/test_plugin_cli_list.py::test_render_marks_update_available_with_transition_and_cta
  tests/test_plugin_cli_show.py::test_show_builtin_renders_official_detail
  tests/test_plugin_cli_uninstall.py::test_uninstall_already_absent_is_noop_success
  tests/test_plugin_cli_uninstall.py::test_uninstall_runs_full_set_minus_plugin
  tests/test_plugin_cli_update.py::test_update_all_upgrades_every_injected_plugin
  tests/test_plugin_cli_update.py::test_update_known_but_not_installed_suggests_install
  tests/test_plugin_cli_update.py::test_update_single_runs_upgrade_package_argv
  tests/test_reasoning_effort_metadata_display.py::test_agent_show_cli_renders_effort_suffix
  tests/test_reasoning_effort_metadata_display.py::test_agent_show_cli_renders_model_alias_chip
  tests/test_sdd_file_writes.py::test_write_sdd_files_rebases_seeded_parent_section
  tests/test_tasks_facade.py::test_kind_filter_selects_one_or_many_task_kinds
  tests/test_tasks_facade.py::test_retention_and_pruning_delete_corresponding_logs
  tests/test_tasks_facade.py::test_rust_facade_round_trip_update_and_get
  tests/test_tasks_runner.py::test_detached_submit_is_owned_by_no_session
  tests/test_tasks_runner.py::test_detached_submit_validates_argv_and_cwd
  tests/test_tasks_runner.py::test_kill_task_terminates_a_detached_task
  tests/test_tasks_runner.py::test_kill_task_terminates_the_supervised_process_group
  tests/test_tasks_runner.py::test_killed_supervisor_is_reconciled_to_terminal_error
  tests/test_tasks_runner.py::test_reconcile_leaves_a_just_submitted_row_alone
  tests/test_tasks_runner.py::test_reconcile_leaves_live_mirrored_tui_rows_alone
  tests/test_tasks_runner.py::test_reconcile_marks_missing_supervisors_error
  tests/test_tasks_runner.py::test_reconcile_owns_stale_pidless_detached_rows
  tests/test_tasks_runner.py::test_reconcile_terminalizes_mirrored_tui_rows_after_owner_exit
  tests/test_tasks_runner.py::test_store_kill_rejects_a_reused_supervisor_pid
  tests/test_tasks_runner.py::test_store_kill_rejects_tui_owned_tasks
  tests/test_tasks_runner.py::test_submit_supervisor_captures_output_and_task_environment
  tests/test_tasks_runner.py::test_submit_validation_and_supervisor_spawn_failure_stay_visible
  tests/test_tasks_runner.py::test_supervisor_records_nonzero_and_unspawnable_commands
  tests/test_vcs_log_progress.py::test_noninteractive_fetch_progress_is_a_durable_stderr_line
  tests/test_vcs_log_render_compact.py::test_linked_tag_rendering_uses_label_and_omits_reference_definition
  tests/test_vcs_log_render_full.py::test_full_format_marks_merge_and_lists_all_parents
  tests/test_vcs_log_render_full.py::test_full_format_shows_body_and_metadata
  tests/test_vcs_log_render_full.py::test_full_tags_line_and_footer_cleanup
  tests/test_vcs_log_render_pretty.py::test_compact_timeline_row_is_one_line_and_ellipsizes
  tests/test_vcs_log_render_pretty.py::test_pretty_day_groups_labels_and_order
  tests/test_vcs_log_render_pretty.py::test_pretty_keeps_raw_merge_subject_when_summary_is_not_safe
  tests/test_vcs_log_render_pretty.py::test_pretty_keeps_raw_pull_request_subject_without_headline
  tests/test_vcs_log_render_pretty.py::test_pretty_marks_merges_and_condenses_pull_request_headline
  tests/test_vcs_log_render_pretty.py::test_pretty_merge_free_output_keeps_existing_spacing
  tests/test_vcs_log_render_pretty.py::test_pretty_origin_legend_is_adaptive
  tests/test_vcs_log_render_pretty.py::test_pretty_tags_suffix_before_author
  tests/test_vcs_provider_vcs_log.py::test_remote_log_ops_fetch_partition_and_union_log
  tests/test_workflow_output_handler.py::TestOnParallelComplete::test_success
  tests/test_workflow_output_handler.py::TestOnParallelComplete::test_with_errors
  tests/test_workflow_output_handler.py::TestOnParallelStart::test_shows_parallel_info
  tests/test_workflow_output_handler.py::TestOnRepeatIteration::test_shows_iteration
  tests/test_workflow_output_handler.py::TestOnStepComplete::test_shows_completion
  tests/test_workflow_output_handler.py::TestOnStepIteration::test_displays_iteration_info
  tests/test_workflow_output_handler.py::TestOnStepStart::test_basic_step
  tests/test_workflow_output_handler.py::TestOnStepStart::test_with_condition
  tests/test_workflow_output_handler.py::TestOnStepStart::test_with_loop_info
  tests/test_workflow_output_handler.py::TestOnStepStart::test_with_parent_step_context
  tests/test_workflow_output_handler.py::TestPrintLoopInfo::test_for_loop
  tests/uv_tool/test_render.py::test_render_result_pluralizes_plugins
  tests/uv_tool/test_render.py::test_render_result_quiet_is_one_line
  tests/uv_tool/test_render.py::test_render_result_quiet_up_to_date
  tests/uv_tool/test_render.py::test_render_result_shows_transitions_and_summary
flake baseline gate: 16 reproducible flake(s) exceed tests/reproducible_flake_baseline.txt (records after 2026-08-10T23:36:35Z, at most 5 failures per run):
  tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion
  tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state
  tests/ace/tui/widgets/test_prompt_panel_header.py::test_family_header_renders_followup_role_attribution
  tests/ace/tui/widgets/test_prompt_panel_header.py::test_header_renders_skill_uses_without_memory_reads
  tests/main/test_project_handler_list_show.py::TestListAndShow::test_project_handler_imports_in_fresh_interpreter
  tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_kills_the_whole_process_group_on_timeout
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
  tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: automatic-Details\n\nSASE_TYPE=sase init]
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: legacy-Details\n\nSASE_AGENT=sase-1]
  tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[fix: tracked-Details\n\nSASE_TYPE=stitch\nSASE_BEAD=sase-1]
  tests/test_core_vcs_log.py::test_parse_computes_auto_origin_from_footer
  tests/test_core_vcs_log.py::test_parse_computes_origin_from_footer
Additions require a filed bead; fix or file the node before landing.
flake baseline gate: 1 recorded node ID(s) no longer collectable (renamed or deleted test); excluded as stale rather than gated as a live flake:
  tests/test_external_mirror_issues.py::test_creation_budget_defers_then_converges_next_pass
error: recipe `selection-health` failed on line 554 with exit code 1
error: recipe `check-full` failed on line 619 with exit code 1

