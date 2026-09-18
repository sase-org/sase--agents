# Chat History - ace-run (0mi--mon-4)

- **TIMESTAMP:** 2026-09-18 01:04:26 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 0mi--mon-4

## Prompt

sase monitor start --command 'just check-full' --reason 'Run required final just check-full after clean just check for the approved hold launch arming closure plan'

## Response

.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✓ test cost
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260918T050356Z-3659262.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] total_file_wall_seconds: actual 5859.181 exceeds budget 4700.000 + 15% tolerance (5405.000) (cpu=3352.136s)
- [advisory] causes.ace_page_enter: actual 1079.399 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=1081.339s, count=763)
- [advisory] causes.ace_settle_pilot: actual 549.245 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=471.203s, count=8782)
- [advisory] causes.parser_create: actual 74.624 exceeds budget 52.000 + 15% tolerance (59.800) (cpu=74.439s, count=2015)
- [advisory] causes.pilot_pause_delay: actual 449.435 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=413.989s, count=17953)
- [advisory] causes.textual_app_run_test_enter: actual 843.535 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=845.752s, count=3995)
- [advisory] causes.yaml_load: actual 25.056 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=24.998s, count=59466)
✗ flake baseline
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just selection-health         │
└───────────────────────────────────────────────────────┘
store: /home/bryan/.sase/test-selection/gh_sase-org__sase
retention: 30 days

Diff-scoped test selection health

scoped runs recorded:   2171
  escalated to full:    1448 (66.7%)
  median selected:      188 (4.7% of 3974)
  p90 selected:         925 (23.3% of 3974)
  median duration:      142.3s
  p75 duration:         378.2s
  p90 duration:         708.7s
  max duration:         3778.5s
full-lane runs recorded: 1993

worker-seconds avoided vs. running the full suite instead: 1,994,262 (~33,238 worker-minutes, at 3,650s per full run)

broadening rules fired:
   754  context-baseline-stale
   362  context-selection
   754  contract-set-always
   173  contract-set-only
  1049  core-identity-changed
    14  directory-conftest
   386  justfile
   754  no-baseline-depth-boost
   150  packaging-config
   132  rename-or-delete
    27  root-conftest
    29  selection-tooling
   403  serial-budget-exceeded
   301  src-data-asset

scoped run outcomes:
  1448  escalated
   164  failed
   559  passed

scoped runs slower than the full lane (444.0s): 152 of 2171
  1448 escalated run(s) not counted here: cost not measured (handed off to the full lane before the runner could time it)
  20260908T193533Z-3f9c7b451655-3261351.json: 3778.5s at 2 workers, 2435 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260907T030738Z-09c93253dc76-198199.json: 2256.4s at 2 workers, 1024 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T201156Z-3f9c7b451655-608970.json: 1798.3s at 4 workers, 2435 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260827T175230Z-2f8bc9abb4e9-2915760.json: 1783.7s at 2 workers, 1589 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T172822Z-2f8bc9abb4e9-2475691.json: 1690.8s at 2 workers, 1133 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260828T140606Z-de491c710dda-1284393.json: 1639.4s at 4 workers, 3246 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T185426Z-43ddcf15f5a7-4019880.json: 1427.4s at 2 workers, 749 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T205326Z-02fc83e11ad3-1899493.json: 1383.3s at 4 workers, 1581 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T161235Z-dffd6de576ed-347603.json: 1304.5s at 4 workers, 1979 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260907T185512Z-7ca1654a2175-351567.json: 1289.3s at 4 workers, 1902 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T192916Z-7636fe03b8c3-3944906.json: 1247.4s at 4 workers, 1456 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T142734Z-5620b5b2de52-419948.json: 1194.5s at 4 workers, 1120 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T211610Z-ace9e2cd468f-2213183.json: 1184.2s at 4 workers, 1862 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260913T141237Z-897147eac21d-1498604.json: 1147.0s at 4 workers, 2140 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260819T154447Z-5057a264ed6d-714378.json: 1097.3s at 4 workers, 1095 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260913T133854Z-21cdb658b052-975875.json: 1065.2s at 4 workers, 2139 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260914T210101Z-bfd22d8df3f1-849197.json: 1056.2s at 4 workers, 1343 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T182452Z-7636fe03b8c3-2302295.json: 1032.8s at 4 workers, 1198 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T190229Z-f72ff9f38564-3934799.json: 1023.2s at 4 workers, 626 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T163703Z-dffd6de576ed-939054.json: 1021.7s at 4 workers, 1979 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260914T192245Z-dd672fd6cbd3-2979769.json: 1020.8s at 4 workers, 1285 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T104652Z-47b65d464834-3681227.json: 1017.8s at 4 workers, 1578 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T190726Z-e17d4e0c0a28-3521107.json: 1000.8s at 4 workers, 1198 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T011903Z-58e5a8310e26-490105.json: 981.7s at 4 workers, 1495 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T181302Z-2f8bc9abb4e9-3364565.json: 978.4s at 4 workers, 1589 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T224221Z-affc43a6fef7-1448286.json: 966.1s at 4 workers, 1485 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T200733Z-3f9c7b451655-823986.json: 960.5s at 3 workers, 457 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T192029Z-43ddcf15f5a7-226887.json: 942.7s at 3 workers, 749 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260829T152732Z-fbd37ca3da3b-1730354.json: 927.7s at 4 workers, 1531 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260825T003723Z-eb1aea8af182-1643826.json: 920.2s at 4 workers, 1638 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260918T045542Z-cc6d51d2db99-3657441.json: 916.7s at 4 workers, 971 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T073726Z-297e6122b041-130746.json: 894.4s at 4 workers, 1644 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260913T161815Z-db6fd25182db-3801613.json: 889.5s at 4 workers, 1503 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260911T193805Z-121896776f4b-2089010.json: 868.8s at 4 workers, 1911 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260915T235334Z-f421051fdda8-3244261.json: 857.1s at 4 workers, 1211 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T110428Z-47b65d464834-4019806.json: 857.0s at 4 workers, 1578 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T224815Z-f07abbec800e-4123899.json: 843.6s at 4 workers, 1394 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T001147Z-f421051fdda8-3497662.json: 837.5s at 4 workers, 1211 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T195807Z-b69b07bc97a2-1418093.json: 832.3s at 4 workers, 1216 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260910T050216Z-71c3df748fac-1628232.json: 829.4s at 4 workers, 1065 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T200949Z-6687426783e2-1634234.json: 823.8s at 4 workers, 1550 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T201440Z-b69b07bc97a2-1721303.json: 810.1s at 4 workers, 1216 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260916T031411Z-768e7763013f-3201614.json: 805.7s at 4 workers, 543 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260910T052146Z-71c3df748fac-1912847.json: 803.1s at 4 workers, 1065 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T204312Z-b69b07bc97a2-2201516.json: 802.1s at 4 workers, 1216 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260824T190659Z-cbea4f23b255-4124361.json: 799.7s at 4 workers, 511 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T025533Z-768e7763013f-2804656.json: 796.2s at 4 workers, 543 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T032101Z-ea358dace46d-3401389.json: 788.1s at 4 workers, 551 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T221405Z-46fc307d83f7-315854.json: 786.5s at 4 workers, 728 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T030151Z-ea358dace46d-2942866.json: 780.5s at 4 workers, 551 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260822T113309Z-3ab0c52dea38-573580.json: 776.4s at 4 workers, 909 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T223136Z-155aeee2efe6-296735.json: 774.1s at 2 workers, 610 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260823T132855Z-db4aecacb884-1995689.json: 773.3s at 4 workers, 1492 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260821T164739Z-41f9a5a29b48-4184484.json: 772.6s at 3 workers, 774 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T114038Z-6ca6e798ed22-255585.json: 757.5s at 4 workers, 1348 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T123723Z-b52341b5506a-1478178.json: 752.7s at 4 workers, 747 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T181441Z-43ddcf15f5a7-3686799.json: 750.8s at 2 workers, 208 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T150703Z-1907346f8e41-3343447.json: 750.5s at 4 workers, 1209 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260822T222158Z-5c9fb7d07b43-3482068.json: 745.9s at 4 workers, 1505 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260823T010158Z-0f00becd749b-761732.json: 743.8s at 4 workers, 1478 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T114336Z-a7b702863fe5-479718.json: 741.8s at 4 workers, 1568 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T211009Z-3fd2b5e2ff70-2221497.json: 738.4s at 4 workers, 480 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T124245Z-b0f6f4f112b8-4076251.json: 737.7s at 4 workers, 540 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260913T104912Z-9429544b531f-2936920.json: 734.9s at 4 workers, 799 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260913T103313Z-9429544b531f-2836840.json: 733.7s at 4 workers, 799 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T150620Z-de491c710dda-2873892.json: 727.7s at 4 workers, 1306 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260821T211903Z-b8b3a69a74cf-841913.json: 724.3s at 4 workers, 1677 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T223128Z-46fc307d83f7-744445.json: 719.2s at 4 workers, 728 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T094804Z-e391b1a28354-4090184.json: 713.6s at 4 workers, 726 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260822T220603Z-5c9fb7d07b43-3368337.json: 711.5s at 4 workers, 1505 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260912T050338Z-9202146ca413-4064806.json: 711.4s at 4 workers, 1143 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260912T091850Z-56ceab3f9995-2014082.json: 709.9s at 4 workers, 800 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260821T164435Z-41f9a5a29b48-4147534.json: 709.6s at 4 workers, 893 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T231930Z-7015c7938d98-1590943.json: 705.1s at 4 workers, 709 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260910T153754Z-7da379ea28e8-3435138.json: 700.6s at 4 workers, 746 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T114308Z-7d2cac73b6d8-2456936.json: 699.9s at 4 workers, 1528 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T100320Z-e391b1a28354-104367.json: 698.9s at 4 workers, 726 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T104732Z-e391b1a28354-761442.json: 697.7s at 4 workers, 726 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T171333Z-9fb3a1805e3c-2996111.json: 695.5s at 4 workers, 602 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T144541Z-30f384324343-5094.json: 694.7s at 4 workers, 1270 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T103117Z-e391b1a28354-518013.json: 693.8s at 4 workers, 726 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T050125Z-d07028050cb8-3770055.json: 689.4s at 4 workers, 640 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T042525Z-d07028050cb8-3424103.json: 687.1s at 4 workers, 701 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T190740Z-a1343b97be6c-689852.json: 677.8s at 4 workers, 963 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260821T210513Z-b8b3a69a74cf-529786.json: 677.5s at 4 workers, 929 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T230327Z-7015c7938d98-1342299.json: 666.4s at 4 workers, 709 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T044224Z-d07028050cb8-3561776.json: 658.2s at 4 workers, 701 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T061349Z-66c0a0d5cb04-1090433.json: 654.5s at 4 workers, 797 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T114615Z-bac22b9680cc-338525.json: 654.0s at 4 workers, 682 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T012221Z-66c0a0d5cb04-2400389.json: 648.9s at 4 workers, 757 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T123017Z-a7b702863fe5-1353524.json: 648.8s at 4 workers, 1323 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260829T064722Z-49d6c4188d1a-1377157.json: 648.5s at 4 workers, 475 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T162755Z-a1e029c65739-2147461.json: 647.0s at 4 workers, 412 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T025047Z-66c0a0d5cb04-3481160.json: 646.6s at 4 workers, 779 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T053224Z-66c0a0d5cb04-753382.json: 642.5s at 4 workers, 797 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T063414Z-5d1841c6f301-1291165.json: 641.2s at 4 workers, 778 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260917T133710Z-88175f34fc8b-522062.json: 636.5s at 4 workers, 751 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260829T070326Z-49d6c4188d1a-1502061.json: 627.5s at 4 workers, 477 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T020804Z-66c0a0d5cb04-2950289.json: 621.9s at 4 workers, 779 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T202418Z-4fcd56796af0-2129825.json: 613.9s at 4 workers, 303 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260907T173810Z-51445642c373-3535550.json: 601.6s at 4 workers, 953 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T141428Z-a2e9f2e145b7-3628334.json: 601.5s at 4 workers, 475 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260828T193548Z-22f7221684a6-2591351.json: 592.7s at 4 workers, 719 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T141452Z-222a11ea0d19-3558647.json: 592.0s at 4 workers, 494 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260912T221958Z-f609668b7276-1308537.json: 591.3s at 4 workers, 575 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T231440Z-a805b0da2f23-376520.json: 588.9s at 4 workers, 449 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260826T140126Z-a2e9f2e145b7-3506902.json: 588.3s at 4 workers, 475 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260826T144942Z-a2e9f2e145b7-4129017.json: 585.7s at 4 workers, 475 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260820T194643Z-eadc7389ccee-2722809.json: 582.0s at 4 workers, 438 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T175737Z-44f4c441706f-1879073.json: 578.6s at 4 workers, 348 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260824T115954Z-bac22b9680cc-682567.json: 576.6s at 4 workers, 682 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260907T113822Z-45b41b78a7f0-2225528.json: 567.0s at 4 workers, 307 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T150325Z-30f384324343-448427.json: 565.6s at 4 workers, 1270 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T132823Z-222a11ea0d19-2416418.json: 564.0s at 4 workers, 467 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T155727Z-a36ff57c9d46-3083317.json: 559.3s at 4 workers, 596 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T142014Z-de491c710dda-2004400.json: 558.9s at 4 workers, 1285 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T161110Z-a36ff57c9d46-3397909.json: 554.6s at 4 workers, 596 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T115850Z-a7b702863fe5-848441.json: 549.0s at 4 workers, 1319 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T161549Z-de491c710dda-3869549.json: 547.4s at 4 workers, 1306 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260828T155051Z-de491c710dda-3646838.json: 546.6s at 4 workers, 1306 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260822T023934Z-e1a03db1fbd4-592905.json: 535.3s at 4 workers, 657 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T020605Z-72abf3729015-1275965.json: 533.2s at 4 workers, 1053 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T163917Z-01c32d51c26b-1955412.json: 533.0s at 4 workers, 846 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T125541Z-b0f6f4f112b8-148118.json: 530.0s at 4 workers, 540 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260829T161911Z-0e47ef648293-2510441.json: 528.0s at 4 workers, 698 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T171908Z-79a95eea9ee1-833839.json: 526.7s at 4 workers, 620 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260819T175406Z-1a0d8e867184-3646680.json: 526.0s at 4 workers, 282 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260820T114337Z-6d87cf2270b8-3601593.json: 525.3s at 4 workers, 454 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260827T021912Z-72abf3729015-1544289.json: 523.5s at 4 workers, 1053 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260819T180332Z-1a0d8e867184-3823417.json: 511.3s at 4 workers, 282 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260819T210045Z-351a3308402a-3105446.json: 508.8s at 4 workers, 302 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260915T183427Z-53035c96715c-1890034.json: 496.4s at 4 workers, 672 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260918T043204Z-1d14218a3c29-3308475.json: 494.7s at 4 workers, 480 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260825T122758Z-51f6369b34bc-1041559.json: 494.3s at 4 workers, 740 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260914T010504Z-f0fb9c8843c5-3431848.json: 492.3s at 4 workers, 718 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260908T130813Z-b0f6f4f112b8-488479.json: 489.7s at 4 workers, 540 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260829T163254Z-0e47ef648293-2698037.json: 489.6s at 4 workers, 698 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260915T155402Z-df87d68dcbc6-1980166.json: 483.2s at 4 workers, 741 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260830T144709Z-18fa499a3af9-3891706.json: 479.2s at 4 workers, 654 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260909T055221Z-7e84441582f7-3508727.json: 478.9s, 335 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260908T204810Z-3fd2b5e2ff70-1954594.json: 473.3s at 4 workers, 938 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260912T063655Z-01a9bd3390bf-913045.json: 472.6s at 4 workers, 853 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260909T071753Z-4de990b3611a-4003761.json: 468.4s, 249 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  20260825T141443Z-bd26194672f7-3616117.json: 468.3s at 4 workers, 273 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260820T113118Z-6d87cf2270b8-3477723.json: 467.0s at 4 workers, 454 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T235356Z-d0c9201bce43-1096074.json: 461.8s at 4 workers, 676 file(s) selected, rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260915T180035Z-0d5afc77397d-1047095.json: 461.3s at 4 workers, 474 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260915T185507Z-53035c96715c-2418668.json: 457.2s at 4 workers, 883 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260916T155632Z-b9c28f25e880-3099302.json: 454.5s at 4 workers, 843 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260822T122121Z-8c1acbfa5056-1482679.json: 452.5s at 4 workers, 413 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, rename-or-delete, serial-budget-exceeded
  20260915T154111Z-df87d68dcbc6-1654335.json: 446.2s at 4 workers, 741 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  20260910T003313Z-bc4566dfbf2d-1343213.json: 444.1s at 4 workers, 774 file(s) selected, rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded

middle gear: 372 run(s) leased a bounded width, 31 refused and escalated instead
  timed runs by width: 351 at 1 worker, 8 at 2 workers, 4 at 3 workers, 360 at 4 workers
  the durations above pool these widths; a wide run's wall clock is not a serial one's

coverage contexts:
  runs that consulted it: 754 of 2171 (1417 escalated before it mattered)
  runs with a baseline:  754 of 754
  runs without one:      0 (static closure alone)
  runs on a stale one:   754
  test files contributed: 23026 (cumulative)

false negatives: 1257 (3283 scoped run/failure matches)
  matching rule: a scoped run is charged with a full-run failure only when
  both records name the same workspace, the scoped run's HEAD is an ancestor
  of the full run's, and the full run's change set covers the scoped run's.
  tests/ace/test_revert_agent_repos.py
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 1 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_accepts_expected_deleted_exact_dir
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_marks_missing_exact_dir_for_broad_fallback
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_artifact_delta_loader.py::test_delta_loader_normalizes_exact_artifact_dirs_without_broad_load
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_failed_plan_family_without_live_retry_remains_terminal[False-True]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_failed_plan_family_without_live_retry_remains_terminal[True-False]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_agent_hints.py::test_immediate_agent_hint_submission_waits_for_rendered_mapping
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_commits.py::test_commit_hint_editor_suffix_opens_raw_diff_path
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_commits.py::test_multiple_commit_hint_editor_suffix_opens_raw_diff_paths
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_commits.py::test_rendered_clan_commit_hint_editor_suffix_opens_raw_diff
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_pager_contract.py::test_ace_built_document_follows_a_linked_capture_source
    failed in 20260913T144855Z-654335d5551d-2325358-full-run.json (head 654335d5551d)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_reports.py::test_memory_report_hint_is_materialized_for_clipboard
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/actions/test_view_files_reports.py::test_memory_report_hint_is_materialized_for_editor
    failed in 20260827T191137Z-1e8cd69ef4f6-547187-full-run.json (head 1e8cd69ef4f6)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix
    failed in 20260827T020035Z-72abf3729015-1336267-full-run.json (head 72abf3729015)
    excluded by 12 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/modals/test_glossary_panel_chips.py::test_filter_input_keeps_prefix_and_digits_as_text
    failed in 20260821T141345Z-e9d3521f4a9f-833000-full-run.json (head e9d3521f4a9f)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_mini_xprompt_name_modal.py::test_new_name_returns_create_target
    failed in 20260822T201405Z-50534e4f8132-2040255-full-run.json (head 50534e4f8132)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_numbered_link_keys.py::test_filter_input_keeps_prefix_and_digits_as_text
    failed in 20260821T141249Z-e9d3521f4a9f-826494-full-run.json (head e9d3521f4a9f)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_numbered_link_keys.py::test_non_digit_cancels_and_passthrough_keeps_other_actions
    failed in 20260821T141249Z-e9d3521f4a9f-826494-full-run.json (head e9d3521f4a9f)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_numbered_link_keys.py::test_pending_prefix_clears_when_hidden
    failed in 20260821T141249Z-e9d3521f4a9f-826494-full-run.json (head e9d3521f4a9f)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion
    failed in 20260820T185648Z-b7bdd3185a07-1785563-full-run.json (head b7bdd3185a07)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_xprompt_browser_helpers.py::test_browser_labels_and_previews_memory_entries
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/modals/test_xprompt_select_modal.py::test_xprompt_select_labels_and_previews_memory_entries
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_loader_executor_shutdown.py::test_loader_consumers_return_empty_during_executor_shutdown[executor0]
    failed in 20260827T201054Z-9ea6f043167c-1896532-full-run.json (head 9ea6f043167c)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_loader_executor_shutdown.py::test_loader_consumers_return_empty_during_executor_shutdown[executor1]
    failed in 20260827T201054Z-9ea6f043167c-1896532-full-run.json (head 9ea6f043167c)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/models/test_monitor_family_root_projection.py::test_nested_monitor_family_lane_counts_running_without_extra_agent
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agent_cleanup_panel_clan_members_e2e.py::test_cleanup_panel_kill_and_dismiss_includes_clan_members
    failed in 20260907T020730Z-09c93253dc76-3875603-full-run.json (head 09c93253dc76)
    excluded by 8 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agent_display_diff.py::test_by_machine_badge_only_change_patches_after_finalize
    failed in 20260910T223826Z-12f01fbc1c7a-2472624-full-run.json (head 12f01fbc1c7a)
    excluded by 19 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agent_notification_status_overrides.py::test_telegram_gate_resolution_dismisses_and_finalizes_pending_tale_override
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agent_panel_collapse_isolation.py::test_panel_switch_skips_config_collapsed_panel
    failed in 20260916T111948Z-7d2cac73b6d8-2285667-full-run.json (head 7d2cac73b6d8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agent_wait_resume_dispatch.py::test_run_workflow_on_agents_dispatches_retry_edit_and_does_not_fork
    failed in 20260910T104750Z-eb7560fd5e3c-2181850-full-run.json (head eb7560fd5e3c)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_agents_bead_warmup.py::test_apply_wait_bead_status_results_keeps_singleton_id_and_adds_warm_glyph
    failed in 20260910T115930Z-0afe85be4758-3715752-full-run.json (head 0afe85be4758)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifact_tab_discovery.py::test_discovery_failure_keeps_a_degraded_plan_tab
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifact_tab_icons.py::test_fixed_artifact_pane_descriptors_carry_builtin_icons
    failed in 20260828T014953Z-66c0a0d5cb04-2870134-full-run.json (head 66c0a0d5cb04)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_agents_revival.py::test_family_row_with_many_revivable_members_seeds_narrow_query
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_agents_revival.py::test_marked_rows_revive_only_revivable_visible_targets
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_agents_revival.py::test_seed_query_filters_revivable_dismissed_rows
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_agents_revival.py::test_single_revivable_selected_row_revives_directly
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_files_loading.py::test_request_entry_target_defers_until_a_matching_snapshot_loads
    failed in 20260827T031429Z-48e019af82f2-2555764-full-run.json (head 48e019af82f2)
    excluded by 10 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_query_bar_invariant.py::test_degraded_resolved_subtab_mounts_no_query_bar
    failed in 20260826T150409Z-a792f5dc7eef-315632-full-run.json (head a792f5dc7eef)
    excluded by 3 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_relation_collapse.py::test_dot_collapses_and_expands_on_each_relations_pane
    failed in 20260827T113820Z-a7b702863fe5-604771-full-run.json (head a7b702863fe5)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_artifacts_relation_collapse.py::test_expanded_link_row_renders_edge_metadata
    failed in 20260827T113820Z-a7b702863fe5-604771-full-run.json (head a7b702863fe5)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_chop_output_edit.py::test_edit_panel_on_axe_chop_with_no_runs_warns
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_chop_output_edit.py::test_edit_panel_on_axe_missing_log_warns
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_chop_output_edit.py::test_edit_panel_on_axe_non_chop_row_warns_without_crashing
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_chop_run_nav.py::test_footer_surfaces_chop_run_keys_when_multiple_runs
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_config_actions.py::test_edit_seed_maps_exact_scopes_contributions_and_provenance
    failed in 20260915T202816Z-5ca8a60d2d73-4188134-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_config_actions.py::test_new_entry_seed_marks_only_intentional_initial_values
    failed in 20260915T202816Z-5ca8a60d2d73-4188134-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_axe_entry_editor_modal.py::test_bundled_lumberjack_and_chop_friendly_field_order
    failed in 20260915T202816Z-5ca8a60d2d73-4188134-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_bead_close_modal.py::test_force_selects_non_done_resolution_and_returns_close_contract
    failed in 20260916T150352Z-64b87df9ce48-1878747-full-run.json (head 64b87df9ce48)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_commits_pane_collection.py::test_sidecar_filter_and_compatibility_toggle_share_collection_scope
    failed in 20260918T035519Z-f90c6b549f6e-2814658-full-run.json (head f90c6b549f6e)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_center_tabs.py::test_importing_lightweight_modal_does_not_import_concrete_panes
    failed in 20260915T230410Z-f421051fdda8-2643123-full-run.json (head f421051fdda8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_edit_modal_editors_widget.py::test_bool_toggle_and_write
    failed in 20260916T060522Z-2ff78b16868e-3043702-full-run.json (head 2ff78b16868e)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_edit_modal_editors_widget.py::test_edit_string_writes_to_target
    failed in 20260916T060522Z-2ff78b16868e-3043702-full-run.json (head 2ff78b16868e)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_edit_modal_validation_widget.py::test_reset_to_default_plans_unset
    failed in 20260916T060522Z-2ff78b16868e-3043702-full-run.json (head 2ff78b16868e)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_hub_pane_launch_flags.py::test_config_hub_strip_thresholds_grow_for_seven_labels
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_hub_pane_launch_flags.py::test_flags_off_prefix_keeps_six_child_numbering
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_hub_pane_navigation.py::test_config_prefix_repeats_out_of_range_and_non_digit_cancel
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_hub_pane_navigation.py::test_configured_config_prefix_selects_subtab
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_config_transaction_widget.py::test_apply_conflict_preserves_draft_and_returns_to_replan
    failed in 20260916T060522Z-2ff78b16868e-3043702-full-run.json (head 2ff78b16868e)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_nav_gate.py::test_countdown_tick_catches_up_after_prompt_typing_quiets
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_nav_gate.py::test_countdown_tick_defers_agent_work_while_prompt_bar_mounted
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_dedupes_defer_timers_during_prompt_input
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_deferred_reschedules_while_prompt_still_active
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_defers_refresh_work_during_prompt_input
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py::test_artifact_change_preserves_deferred_paths_during_prompt_input
    failed in 20260911T234411Z-0b653f0a2b1c-613713-full-run.json (head 0b653f0a2b1c)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_fleet_agents.py::test_project_fleet_agents_carries_remote_queue_weight_without_local_charge
    failed in 20260910T161307Z-54d9c112af8c-223785-full-run.json (head 54d9c112af8c)
    excluded by 4 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_fleet_setup_guidance.py::test_setup_agent_machine_opens_machines_pane
    failed in 20260910T112321Z-66773a2b3cb0-2854661-full-run.json (head 66773a2b3cb0)
    excluded by 8 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_help_modal_filter.py::test_filter_then_clear_restores_byte_identical_columns
    failed in 20260907T024601Z-09c93253dc76-609412-full-run.json (head 09c93253dc76)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_agent_demotes_clan_declaration
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_agent_forces_name_reuse_for_done_agent
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_agent_keeps_prompt_when_it_has_no_id
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_agent_replaces_template_with_concrete_name
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_clan_member_preserves_hood
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_family_phase_forces_exact_member_attachment
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_kill_and_edit_agent_name.py::test_kill_and_edit_family_root_keeps_clan_identity
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_launch_records.py::test_failed_proc_marks_record_failed_but_keeps_successful_results
    failed in 20260906T160421Z-58f16fe6878c-1789355-full-run.json (head 58f16fe6878c)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_lazy_imports.py::test_patch_loading_import_stays_off_unittest_mock
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 1 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked
    failed in 20260917T230327Z-f1616c505e35-1420555-full-run.json (head f1616c505e35)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_plan_gate.py::test_neutral_plan_submission_executes_actual_modal_choice[tale-True-expected_option_ids1-TALE APPROVED]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_plan_gate.py::test_neutral_plan_submission_forwards_modal_wait_spec
    failed in 20260830T133440Z-15be5ac470ca-3234507-full-run.json (head 15be5ac470ca)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_plan_gate.py::test_neutral_tale_submission_merges_shared_and_per_option_inputs
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_sudo.py::test_sudo_deny_uses_headless_durable_gate_executor
    failed in 20260915T124315Z-7420b829868e-1587225-full-run.json (head 7420b829868e)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_sudo.py::test_sudo_notification_loader_projects_verified_manifest
    failed in 20260915T124315Z-7420b829868e-1587225-full-run.json (head 7420b829868e)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_notification_sudo.py::test_sudo_run_uses_terminal_handoff_not_durable_proc
    failed in 20260915T124315Z-7420b829868e-1587225-full-run.json (head 7420b829868e)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest
    failed in 20260825T060926Z-882ba36f5ae8-1265587-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_cancel_is_non_mutating
    failed in 20260912T183126Z-2eb520541192-4074856-full-run.json (head 2eb520541192)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_plugins_catalog_scale_fixture.py::test_scale_catalog_fixture_filters_and_marks_at_n10
    failed in 20260907T185026Z-a9f95ca5e645-642293-full-run.json (head a9f95ca5e645)
    excluded by 1 scoped run(s), first 20260907T192016Z-a9f95ca5e645-1303167.json (head a9f95ca5e645)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast
    failed in 20260909T200519Z-3feb023119bf-407531-full-run.json (head 3feb023119bf)
    excluded by 1 scoped run(s), first 20260909T202738Z-3feb023119bf-786607.json (head 3feb023119bf)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
    failed in 20260823T002806Z-0f00becd749b-570774-full-run.json (head 0f00becd749b)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_procs_pane_filter.py::test_dismiss_restores_the_query_active_when_the_session_opened
    failed in 20260909T200519Z-3feb023119bf-407531-full-run.json (head 3feb023119bf)
    excluded by 1 scoped run(s), first 20260909T202738Z-3feb023119bf-786607.json (head 3feb023119bf)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_statistics_view_number_select.py::test_configured_prefix_arms_the_same_number_selection
    failed in 20260906T210207Z-8efecdd7390a-2387153-full-run.json (head 8efecdd7390a)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_feedback_submitted_at
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_index_query_picks_up_appended_plan_submitted_at
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_tier1_index_meta_self_heal.py::test_tier1_loader_agent_plan_times_reflects_mid_run_update
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds
    failed in 20260907T052700Z-e44e39a288f2-3671420-full-run.json (head e44e39a288f2)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
    failed in 20260909T120631Z-4068437a2c23-3846815-full-run.json (head 4068437a2c23)
    excluded by 1 scoped run(s), first 20260909T123510Z-4068437a2c23-169972.json (head 4068437a2c23)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/ace/tui/test_xprompt_browser_load_keymap.py::test_brackets_cycle_config_subtabs_from_xprompt_filter
    failed in 20260821T150428Z-abf598be5c09-1788468-full-run.json (head abf598be5c09)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_records_pump_stall_stack_and_recovery
    failed in 20260917T160804Z-44e697c7145d-694575-full-run.json (head 44e697c7145d)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/artifacts/test_agents_query.py::test_agents_query_index_filters_artifact_link_facets
    failed in 20260825T224618Z-7015c7938d98-1286225-full-run.json (head 7015c7938d98)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/artifacts/test_agents_query.py::test_agents_query_index_maps_catalog_fields_and_project_display_name
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/artifacts/test_agents_query.py::test_agents_query_limit_is_applied_after_full_membership
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/artifacts/test_agents_query.py::test_agents_query_rejects_cached_result_from_stale_generation
    failed in 20260825T175008Z-b85cdffd3de6-3914126-full-run.json (head b85cdffd3de6)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_header_enrichment_hints_async.py::test_cold_family_hint_render_stays_active_and_gains_enriched_mapping
    failed in 20260823T002806Z-0f00becd749b-570774-full-run.json (head 0f00becd749b)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_model_fields.py::TestLoaderFollowupPopulation::test_coder_attached_to_parent
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_model_fields.py::TestLoaderFollowupPopulation::test_feedback_attached
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_model_fields.py::TestLoaderFollowupPopulation::test_sorted_chronologically
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_model_fields.py::TestLoaderFollowupPopulation::test_workflow_child_not_attached
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_display_output_variables.py::test_filesystem_and_wire_output_variables_render_identically
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_agent_list_status_indicators.py::TestAgentListFleetMarker::test_remote_rows_use_star_shape_for_follow_state
    failed in 20260910T141943Z-7da379ea28e8-1989192-full-run.json (head 7da379ea28e8)
    excluded by 12 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_axe_onboarding.py::test_axe_onboarding_content_describes_axe_chops_bgcmds_and_docs
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_history_word_completion_delete.py::test_smart_mode_ctrl_d_persists_canonical_word_for_uppercase_prefix
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_mode_applies_typed_shout_case_and_auto_accepts
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_mode_case_variants_collapse_to_one_auto_accept_row
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_mode_preserves_intrinsic_casing
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_mode_shared_extension_uses_typed_case
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py::test_artifact_ref_kind_cache_warms_off_thread
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_multi_pane_hint_entries_include_nav_and_stash
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_multi_pane_without_stash_hides_load_and_restore
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_single_pane_hint_entries_hide_multi_pane_and_stash_actions
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_single_pane_with_pin_includes_update_pin_on_bare_and_ctrl_g
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_single_pane_with_stash_hides_open_stash_on_bare_g
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py::test_single_pane_with_stash_includes_open_stash_on_ctrl_g
    failed in 20260910T112232Z-eb7560fd5e3c-2845973-full-run.json (head eb7560fd5e3c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_glossary_request_carries_term_under_cursor
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_stack_height_accounts_for_visible_frontmatter_panel
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py::test_initial_xprompt_markdown_lifts_frontmatter_and_splits
    failed in 20260829T105917Z-ca7692ee3329-3042367-full-run.json (head ca7692ee3329)
    excluded by 7 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py::test_load_stack_from_xprompt_markdown_clears_frontmatter_panel
    failed in 20260820T202329Z-f55b0b80f94d-3797525-full-run.json (head f55b0b80f94d)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_todo_highlight.py::test_todo_background_yields_to_selection_search_yank_and_cursor
    failed in 20260906T152844Z-58f16fe6878c-1416787-full-run.json (head 58f16fe6878c)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles
    failed in 20260916T021731Z-ea358dace46d-2074180-full-run.json (head ea358dace46d)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agent/test_pending_handoff.py::test_pending_handoff_markers_are_named_constants
    failed in 20260826T213016Z-1cb772d9c38e-1205759-full-run.json (head 1cb772d9c38e)
    excluded by 14 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_commit_publication.py::test_push_failure_is_queued_and_next_commit_drains_idempotently
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_commit_publication_queue.py::test_mixed_queue_publishes_good_items_and_quarantines_only_bad_item
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_clears_stale_index_lock_before_recovery
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_failure_after_payload_write_restores_clean_tree
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_recovers_dirty_payload_before_pull
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_reuses_one_name_registry_load_session
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_full_sync_transaction_commits_and_pushes_only_payload
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_git_sync.py::test_non_fast_forward_recomputes_and_retries_push_once
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/agents_sync/test_prompt_archive_validation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_links/test_link_suggest.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_document_source_resolution.py::test_home_source_path_is_binding_validation_not_repository_search
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/artifact_refs/test_preprocessing_effects.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/completion/test_build.py::test_suppressed_option_is_kept_and_flagged_hidden
    failed in 20260823T151928Z-2e0ac0f37c0d-523299-full-run.json (head 2e0ac0f37c0d)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree[sbd show --for-sbd show --format ]
    failed in 20260917T124153Z-02f0fd3893f5-3560781-full-run.json (head 02f0fd3893f5)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
    failed in 20260910T161137Z-cceed09a993f-197348-full-run.json (head cceed09a993f)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/continuation/test_capture.py
    failed in 20260912T003214Z-a694708f4592-1313213-full-run.json (head a694708f4592)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_agent_artifact_run_retention.py::test_apply_refuses_when_continuation_closure_fails
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 7 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_agent_artifact_run_retention.py::test_binding_preserves_empty_referenced_run_during_empty_cleanup
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 7 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_agent_artifact_run_retention.py::test_binding_preserves_run_reached_through_symlinked_ancestor
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 7 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_artifact_ref_files_index.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_artifact_row_resolution_facade.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/core/test_disk_footprint.py::test_managed_tmp_reap_step_reports_age_only_bytes
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/dispatch/test_machine_service.py::test_add_machine_stores_only_credential_ref_in_config
    failed in 20260907T000248Z-4093493a4c50-1661875-full-run.json (head 4093493a4c50)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/dispatch/test_machine_service.py::test_list_machines_is_offline
    failed in 20260907T000248Z-4093493a4c50-1661875-full-run.json (head 4093493a4c50)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/dispatch/test_machine_service.py::test_status_quarantines_installation_mismatch
    failed in 20260907T000248Z-4093493a4c50-1661875-full-run.json (head 4093493a4c50)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_file_hooks.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_config_notification_tabs.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/doctor/test_checks_dispatch.py::test_dispatch_credentials_reports_missing_local_ref
    failed in 20260907T000248Z-4093493a4c50-1661875-full-run.json (head 4093493a4c50)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_cli.py::test_non_retryable_marker_channel_and_exit_code
    failed in 20260912T101137Z-00d5c40a8195-2729853-full-run.json (head 00d5c40a8195)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_crashed_fakey_runner_frees_slot_without_done_marker
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_fakey_drain_barrier_waits_for_later_eligible_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_killing_parked_fakey_agent_keeps_queue_healthy
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/fakey/test_runner_slots_e2e.py::test_live_config_raise_releases_fakey_waiter_without_axe
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_conformance/test_gate_shell_conformance.py::test_shell_gate_settles_identically_across_every_surface
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_fork_family_targets_the_agent_family
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_fork_none_omits_the_fork_prefix
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_fork_prefix_is_dropped_when_the_creator_never_settles
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_fork_shell_targets_the_gate_shells_own_member_name
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_inherit_workspace_transfers_from_the_creator_claim_pid
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_raw_prompt_omits_wrapper_and_inherited_model_prefix
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_release_workspace_passes_no_transfer_pid
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_followup_launch.py::test_spawn_failure_records_the_error_and_stashes_the_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_transaction_gate_intent.py::test_auto_resolved_gate_clears_intent_marker
    failed in 20260916T171634Z-44f4c441706f-928165-full-run.json (head 44f4c441706f)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_transaction_gate_intent.py::test_clean_gate_error_clears_intent_marker
    failed in 20260916T171634Z-44f4c441706f-928165-full-run.json (head 44f4c441706f)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_transaction_gate_intent.py::test_clean_lane_error_clears_intent_marker
    failed in 20260916T171634Z-44f4c441706f-928165-full-run.json (head 44f4c441706f)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_transaction_gate_intent.py::test_keyboard_interrupt_leaves_intent_marker
    failed in 20260916T171634Z-44f4c441706f-928165-full-run.json (head 44f4c441706f)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/gate_shell/test_transaction_gate_intent.py::test_non_terminal_creation_keeps_intent_for_handoff
    failed in 20260916T171634Z-44f4c441706f-928165-full-run.json (head 44f4c441706f)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_catalog.py::test_resolve_agent_falls_back_to_meta_chat_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_catalog.py::test_resolve_agent_via_done_response_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_resume_refs.py::test_template_resume_ref_resolves_latest_concrete_agent_chat
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/history/test_chat_resume_refs.py::test_template_suffix_resume_ref_resolves_latest_concrete_agent_chat
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_claude_usage.py::test_passive_context_hashes_auth_identity
    failed in 20260908T155615Z-8c4f8fd22ae9-4191825-full-run.json (head 8c4f8fd22ae9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_executor_accepts_artifact_link_auto_commit_against_existing_marker
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_executor_commits_mixed_report_after_artifact_link_auto_commit
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_executor_rejects_artifact_link_auto_commit_without_new_marker
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_malformed_candidates_remain_dirty
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_mixed_unrelated_dirt_is_left_for_the_declaration
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_multiple_sidecars_commit_once_each
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_pre_existing_dirty_index_is_not_auto_committed
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_artifact_links.py::test_publication_failure_is_recoverable
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_sibling_done_status_change_uses_provider_path
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_dirty_repo_dedupe.py::test_repo_reachable_as_both_external_and_sdd_sidecar_prefers_sdd_kind
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_effort.py::test_finalizer_follow_up_preserves_reasoning_effort
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_external_repos.py::test_dirty_external_repo_triggers_correctly_labeled_follow_up
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_linked_repos_compat.py::test_dirty_configured_linked_env_triggers_follow_up_turn
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_siblings.py::test_dirty_configured_sibling_triggers_follow_up_turn
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_siblings.py::test_multiple_dirty_configured_siblings_are_listed_and_rechecked
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_commit_finalizer_siblings.py::test_opened_dirty_sibling_uses_recorded_path_when_config_omits_it
    failed in 20260820T215024Z-8f82eb99205c-1075192-full-run.json (head 8f82eb99205c)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_eligibility.py::TestEligibleUsageProvidersCodexNvmFallback::test_codex_is_eligible_through_nvm_fallback_when_path_is_empty
    failed in 20260912T110822Z-9c2eb4a356b0-3495810-full-run.json (head 9c2eb4a356b0)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_eligibility.py::TestEligibleUsageProvidersExclusionRules::test_collection_disabled_provider_is_excluded_even_when_referenced
    failed in 20260912T110822Z-9c2eb4a356b0-3495810-full-run.json (head 9c2eb4a356b0)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_eligibility.py::TestEligibleUsageProvidersExclusionRules::test_explicit_enablement_includes_an_unreferenced_provider
    failed in 20260912T110822Z-9c2eb4a356b0-3495810-full-run.json (head 9c2eb4a356b0)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_peek.py::test_codex_nvm_weekly_window_reaches_header_through_real_pipeline
    failed in 20260912T110822Z-9c2eb4a356b0-3495810-full-run.json (head 9c2eb4a356b0)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_presentation.py::test_json_payload_filters_and_reports_missing_requested_providers
    failed in 20260908T143500Z-a0ac015e0bda-2534657-full-run.json (head a0ac015e0bda)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_presentation.py::test_plain_window_records_include_core_remaining_text
    failed in 20260908T143500Z-a0ac015e0bda-2534657-full-run.json (head a0ac015e0bda)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh.py::test_due_refresh_with_no_eligible_providers_is_empty
    failed in 20260908T121711Z-b0f6f4f112b8-3828771-full-run.json (head b0f6f4f112b8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh.py::test_flag_and_config_opt_out_do_not_submit
    failed in 20260908T121711Z-b0f6f4f112b8-3828771-full-run.json (head b0f6f4f112b8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh.py::test_joining_one_provider_does_not_drop_a_new_peer
    failed in 20260908T121711Z-b0f6f4f112b8-3828771-full-run.json (head b0f6f4f112b8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh.py::test_limit_event_trigger_marks_due_and_submits
    failed in 20260908T121711Z-b0f6f4f112b8-3828771-full-run.json (head b0f6f4f112b8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh.py::test_submit_coalesces_overlapping_provider_subsets
    failed in 20260908T121711Z-b0f6f4f112b8-3828771-full-run.json (head b0f6f4f112b8)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_refresh_runner.py::test_runner_collects_synthetic_provider
    failed in 20260908T155615Z-8c4f8fd22ae9-4191825-full-run.json (head 8c4f8fd22ae9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/llm_provider/test_usage_transport.py::test_jsonline_descendant_cleanup
    failed in 20260917T155830Z-797feeb62dcb-451385-full-run.json (head 797feeb62dcb)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/logs/test_revive_log.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/logs/test_workspace_claim_ledger.py::TestRecordRunningFieldMutation::test_appends_success_record_with_before_after_occupancy
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_lifecycle.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link.py::test_add_and_rm_work_without_feature_override
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link.py::test_add_list_rm_round_trip
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link.py::test_list_reads_rows_without_feature_override
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link.py::test_list_without_reference_merges_in_projected_rows
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link_commit.py::test_add_commits_one_sidecar_for_two_indexes
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link_commit.py::test_bead_to_document_commits_document_and_bead_store
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link_commit.py::test_document_endpoints_across_two_sidecars_commit_each_once
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link_commit.py::test_noop_add_creates_zero_commits
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_link_commit.py::test_relation_removal_commits_once
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_path.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_read.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_show.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_cli_stats.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_link_outbox.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_artifact_pane.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_bead_fast_path_context.py::test_fast_path_routes_write_commands_for_non_vc_store
    failed in 20260915T181212Z-53035c96715c-1479629-full-run.json (head 53035c96715c)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_chat_handler_show.py::test_show_agent_via_done_response_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_agent_docs.py::test_init_memory_does_not_migrate_single_custom_provider_file
    failed in 20260824T215247Z-f6c146722531-2981447-full-run.json (head f6c146722531)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_agent_docs.py::test_init_memory_overwrites_multiple_custom_provider_files
    failed in 20260824T215247Z-f6c146722531-2981447-full-run.json (head f6c146722531)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_agents_templates.py::test_project_template_override_renders_and_round_trips
    failed in 20260824T215247Z-f6c146722531-2981447-full-run.json (head f6c146722531)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_bead_note.py::test_home_root_omits_bead_memory_note
    failed in 20260826T222517Z-5a8284733de9-2114568-full-run.json (head 5a8284733de9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_glossary.py::test_memory_plan_generates_glossary_note_in_tier1
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_glossary.py::test_memory_plan_numbers_glossary_in_tier1_and_notes_in_tier2
    failed in 20260824T215247Z-f6c146722531-2981447-full-run.json (head f6c146722531)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_handler_outputs.py::test_init_memory_renders_data_driven_readme_and_asset
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_managed_agents.py::test_init_memory_migrates_legacy_memory_note_types_idempotently
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_managed_agents_descriptions.py::test_init_memory_allows_fenced_hash_in_long_memory_description
    failed in 20260830T140825Z-18fa499a3af9-3474395-full-run.json (head 18fa499a3af9)
    excluded by 17 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_memory_managed_agents_descriptions.py::test_init_memory_managed_agents_renders_block_long_memory_descriptions
    failed in 20260830T140825Z-18fa499a3af9-3474395-full-run.json (head 18fa499a3af9)
    excluded by 17 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_memory_managed_agents_frontmatter.py::test_tier2_section_heading_keeps_top_level_long_note_reachable
    failed in 20260830T140825Z-18fa499a3af9-3474395-full-run.json (head 18fa499a3af9)
    excluded by 17 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_memory_markdown_templates.py::test_custom_sase_template_round_trips_into_agents
    failed in 20260824T215247Z-f6c146722531-2981447-full-run.json (head f6c146722531)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_plan.py::test_memory_init_blocks_nonidentical_canonical_and_legacy_trees
    failed in 20260824T211258Z-b3e0cc0e48d7-2430159-full-run.json (head b3e0cc0e48d7)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_memory_plan.py::test_memory_plan_missing_tree_reports_create_actions_without_writing
    failed in 20260830T140825Z-18fa499a3af9-3474395-full-run.json (head 18fa499a3af9)
    excluded by 17 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_memory_validation.py::test_init_memory_registry_runs_after_config
    failed in 20260907T001907Z-4093493a4c50-1932444-full-run.json (head 4093493a4c50)
    excluded by 8 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_onboarding_memory.py::test_bare_init_yes_repairs_unreferenced_long_memory
    failed in 20260830T140825Z-18fa499a3af9-3474395-full-run.json (head 18fa499a3af9)
    excluded by 16 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_onboarding_parser.py::test_init_help_lists_existing_subcommands
    failed in 20260905T213004Z-302875cbc6d8-215604-full-run.json (head 302875cbc6d8)
    excluded by 30 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_onboarding_parser.py::test_registry_order_is_config_memory_repo_skills
    failed in 20260907T001907Z-4093493a4c50-1932444-full-run.json (head 4093493a4c50)
    excluded by 8 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_init_skills_source_content.py::test_commit_skill_sources_do_not_reference_legacy_bead_flag[sase_hg_commit]
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 3 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_skills_source_content.py::test_commit_skill_sources_reject_legacy_sase_commit_cli[sase_hg_commit]
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 3 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_skills_source_content.py::test_hg_commit_skill_invokes_stitch_create
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 3 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_skills_sources.py::test_docs_xprompt_bundled_skills_table_matches_packaged_sources
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 3 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_monitor-expected_phrases7]
    failed in 20260828T175629Z-7bc0c0d98e4a-1051921-full-run.json (head 7bc0c0d98e4a)
    excluded by 8 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_cli_show.py::test_show_json_payload_includes_note_and_children
    failed in 20260826T222517Z-5a8284733de9-2114568-full-run.json (head 5a8284733de9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_cli_show.py::test_show_prints_body_and_children_without_audit_log
    failed in 20260826T222517Z-5a8284733de9-2114568-full-run.json (head 5a8284733de9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_cli_show.py::test_show_rich_format_renders_path_type_and_children
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 10 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_cli_show.py::test_show_stdout_matches_read_stdout
    failed in 20260826T222517Z-5a8284733de9-2114568-full-run.json (head 5a8284733de9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_log.py::test_memory_log_include_proposals_json_adds_proposal_events
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_log.py::test_memory_log_include_proposals_rich_output
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_parser_handler.py::test_parser_registers_memory_namespace
    failed in 20260829T145515Z-fbd37ca3da3b-1420141-full-run.json (head fbd37ca3da3b)
    excluded by 6 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_memory_read_list.py::test_memory_read_appends_children_section
    failed in 20260826T222517Z-5a8284733de9-2114568-full-run.json (head 5a8284733de9)
    excluded by 7 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_all_includes_finished_monitors
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_does_not_flag_a_cleanly_launched_followup
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_empty_active_result_renders_the_all_hint
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_filters_by_status_and_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_flags_a_degraded_followup_in_table_and_markdown
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_flags_a_dropped_followup_in_table_and_markdown
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_json_envelope_carries_followup_disposition
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_json_envelope_is_stable
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_lane_flag_is_a_deprecated_alias_for_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_limit_trims_the_newest_first_result
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_markdown_format_renders_a_pipe_table
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_list.py::test_list_shows_only_active_monitors_by_default
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_follow_streams_new_output_until_terminal
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_includes_followup_model_in_detail_and_json
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_json_envelope_is_stable
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_output_only_suppresses_the_detail_panel
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_output_reads_rotated_and_active_logs
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_renders_a_degraded_followup_reason
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_renders_a_dropped_followup_error
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_renders_detail_panel_and_output_tail
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_resolves_by_owning_agent_and_member_agent_name
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_show.py::test_show_unknown_ref_is_a_usage_error
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_stop.py::test_stop_already_terminal_reports_nothing_to_do
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_stop.py::test_stop_json_envelope_is_stable
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_monitor_handler_stop.py::test_stop_signals_the_supervisor_and_reports_success
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_ops_commands.py::test_bead_apply_status_success_and_failure
    failed in 20260915T163713Z-4e98613a1fbb-3265843-full-run.json (head 4e98613a1fbb)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_machine.py::test_init_machine_check_alias_does_not_discover
    failed in 20260907T000248Z-4093493a4c50-1661875-full-run.json (head 4093493a4c50)
    excluded by 4 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_monitor.py::test_monitor_group_help_lists_sorted_visible_subcommands
    failed in 20260912T084840Z-56ceab3f9995-1719213-full-run.json (head 56ceab3f9995)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_parser_root_help.py::test_root_help_renders_compact_help
    failed in 20260907T001907Z-4093493a4c50-1932444-full-run.json (head 4093493a4c50)
    excluded by 8 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_repo_init_plan.py::test_init_registry_uses_repo_runner
    failed in 20260907T001907Z-4093493a4c50-1932444-full-run.json (head 4093493a4c50)
    excluded by 8 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_stitch_glossary_source.py::test_stitch_glossary_identifies_stitch_create
    failed in 20260825T015742Z-f22f11307a7b-3069598-full-run.json (head f22f11307a7b)
    excluded by 3 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_usage_command.py::test_list_json_filters_cached_snapshot
    failed in 20260908T143500Z-a0ac015e0bda-2534657-full-run.json (head a0ac015e0bda)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_var_get_snapshot.py::test_get_known_agent_without_variables_is_empty_success
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_var_get_snapshot.py::test_get_named_agent_repeatable_project_filter_and_unknown_error
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_var_get_snapshot.py::test_get_named_agent_uses_newest_visible_artifact
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_var_get_snapshot.py::test_get_preserves_dotted_hyphenated_and_digit_snapshot_names
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/main/test_var_get_snapshot.py::test_get_wrapped_snapshot_is_not_selector_envelope
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/memory/test_memory_selector_render.py::test_inline_note_outputs_preserve_unread_grandchild_listing
    failed in 20260918T041308Z-cc6d51d2db99-3119688-full-run.json (head cc6d51d2db99)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/memory/test_mutation_validate.py::test_validate_rejects_invalid_type_and_empty_long_description
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_falls_back_to_fresh_claim_after_transfer_failure
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_falls_back_to_primary_when_meta_pairing_is_unresolvable
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_falls_back_to_workspace_zero_when_workspace_taken
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_records_the_error_and_returns_false_on_failure
    failed in 20260911T154318Z-64360feed600-4082286-full-run.json (head 64360feed600)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_repairs_a_meta_workspace_num_mismatch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_proc_facade.py::test_historical_legacy_monitor_is_not_adopted_into_a_proc_row
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_proc_settlement.py::test_settle_monitor_followup_persists_stopped_at_after_wait
    failed in 20260913T214754Z-5be4f6ae32e1-549073-full-run.json (head 5be4f6ae32e1)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_proc_settlement.py::test_settle_monitor_followup_sets_missing_stopped_at_on_resume
    failed in 20260913T214754Z-5be4f6ae32e1-549073-full-run.json (head 5be4f6ae32e1)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_resume.py::test_resume_dispatch_real_preprocess_adopt_budget_and_provider_invoke_combine
    failed in 20260913T214754Z-5be4f6ae32e1-549073-full-run.json (head 5be4f6ae32e1)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store.py::test_has_any_monitor_ignores_false_positive_role_only_rows
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store.py::test_list_monitors_defaults_to_every_project_newest_first
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store.py::test_list_monitors_scopes_to_one_project
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store.py::test_list_monitors_skips_legacy_false_positive_monitor_rows
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store_reconcile.py::test_list_monitors_reconciles_dead_supervisors
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store_reconcile.py::test_reconcile_dead_supervisors_leaves_healthy_running_monitors_unchanged
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store_reconcile_proc_store.py::test_list_monitors_proc_store_reads_do_not_scale_with_record_count
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store_reconcile_proc_store.py::test_reconcile_dead_supervisors_reads_proc_store_once
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_store_reconcile_queries.py::test_list_monitors_keeps_full_history_listing_query
    failed in 20260912T084840Z-56ceab3f9995-1719213-full-run.json (head 56ceab3f9995)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child
    failed in 20260822T153624Z-a22ca4d61b43-1497782-full-run.json (head a22ca4d61b43)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_bead_live_links.py::test_pager_follows_bead_links_and_preserves_trail
    failed in 20260912T172336Z-ecea389efd48-2481720-full-run.json (head ecea389efd48)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_copy_owned.py::test_copy_owned_home_path_uses_filesystem_resolution
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_labels.py::test_render_section_with_labels_keeps_dangling_label_dim_without_background
    failed in 20260828T110812Z-30b495e66613-3088091-full-run.json (head 30b495e66613)
    excluded by 1 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_labels.py::test_render_section_with_labels_limits_matching_capsule_to_hint
    failed in 20260828T110812Z-30b495e66613-3088091-full-run.json (head 30b495e66613)
    excluded by 1 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_labels.py::test_render_section_with_labels_paints_capsules_and_kind_glyphs
    failed in 20260828T110812Z-30b495e66613-3088091-full-run.json (head 30b495e66613)
    excluded by 1 scoped run(s), first 20260825T155054Z-2fa772b93d3e-1599208.json (head 2fa772b93d3e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_rail_parity.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_refresh_provider.py::test_r_coalesces_overlapping_refresh_requests
    failed in 20260914T043517Z-1dd9160fdb98-2027413-full-run.json (head 1dd9160fdb98)
    excluded by 1 scoped run(s), first 20260914T042939Z-1dd9160fdb98-1892680.json (head 1dd9160fdb98)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/pager/test_rendered_link_contract.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_rendered_link_contract.py::test_screenshot_plan_and_capture_paths_follow_through_real_labels
    failed in 20260917T124153Z-02f0fd3893f5-3560781-full-run.json (head 02f0fd3893f5)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_rendered_link_failures.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_rendered_link_failures.py::test_copy_of_a_missing_path_keeps_the_logical_token
    failed in 20260910T145620Z-7da379ea28e8-2857595-full-run.json (head 7da379ea28e8)
    excluded by 1 scoped run(s), first 20260910T153754Z-7da379ea28e8-3435138.json (head 7da379ea28e8)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/pager/test_rendered_link_navigation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_rendered_link_navigation.py::test_follow_several_hops_then_back_and_forward_restore_the_trail
    failed in 20260910T041643Z-0dc3536782a3-1173227-full-run.json (head 0dc3536782a3)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_resolve_paths.py::test_owned_home_directory_keeps_directory_landing
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_resolve_paths.py::test_owned_home_path_falls_back_to_filesystem_resolution
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/pager/test_resolve_paths.py::test_owned_missing_home_path_reports_plain_missing_path
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/perf/test_agent_disk_load_ops_regression.py::test_current_disk_load_operation_counts_match_baseline
    failed in 20260823T002806Z-0f00becd749b-570774-full-run.json (head 0f00becd749b)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/perf/test_view_hints_regression.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/plan_chain_golden/test_marker_and_loop_golden.py::test_killed_followup_runs_kill_handoff_again
    failed in 20260916T153008Z-a36ff57c9d46-2653430-full-run.json (head a36ff57c9d46)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/plan_chain_golden/test_marker_and_loop_golden.py::test_normally_completing_followup_breaks_exec_loop[--code-code]
    failed in 20260916T153008Z-a36ff57c9d46-2653430-full-run.json (head a36ff57c9d46)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/plan_chain_golden/test_marker_and_loop_golden.py::test_normally_completing_followup_breaks_exec_loop[--epic-epic]
    failed in 20260916T153008Z-a36ff57c9d46-2653430-full-run.json (head a36ff57c9d46)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/plan_chain_golden/test_plan_approval_response_golden.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/question_shell/test_followup_prompt.py::test_unreadable_chain_falls_back_to_declared_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_backfill.py::test_batch_is_bounded_and_reports_remaining
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_derivation.py::test_a_second_pass_over_the_same_documents_is_idempotent
    failed in 20260910T193142Z-755ef4a7b60a-3798219-full-run.json (head 755ef4a7b60a)
    excluded by 1 scoped run(s), first 20260910T185316Z-755ef4a7b60a-3178828.json (head 755ef4a7b60a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd/test_artifact_link_machine_authorize.py::test_backfill_sweep_skips_primary_owned_root
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_machine_authorize.py::test_outbox_drain_skips_primary_owned_root
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_machine_authorize.py::test_reconcile_and_repair_reports_skip_and_does_not_commit
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_machine_authorize.py::test_rename_repair_skips_primary_owned_root
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_migrate_notes.py::test_migrate_notes_apply_is_available_without_feature_override
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_migrate_notes.py::test_migrate_notes_apply_writes_events_and_migrated_notes
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_migrate_notes.py::test_migrate_notes_trims_link_descriptions
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_neighborhood.py::test_launch_neighborhood_empty_when_no_semantic_rows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_neighborhood.py::test_launch_neighborhood_filters_observational_and_related
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_neighborhood.py::test_neighborhood_footer_caps_and_reports_overflow
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_neighborhood.py::test_neighborhood_footer_none_when_no_rows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_neighborhood.py::test_neighborhood_footer_prefers_semantic_over_observational
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_projection.py::test_derived_origin_row_renders_in_the_links_block
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_reconcile.py::test_forwards_deadline_and_deferred_refs
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_release_evidence.py::test_blank_run_id_or_agent_id_never_qualifies
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_release_evidence.py::test_evidence_does_not_release_a_different_run_or_agent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_release_evidence.py::test_malformed_evidence_lines_are_skipped_not_fatal
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_release_evidence.py::test_recorded_evidence_is_visible_for_the_exact_run_and_agent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py::test_commit_artifact_link_indexes_stages_existing_and_deleted_indexes
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py::test_rename_repair_commit_includes_rewrite_and_removed_index
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py::test_repair_applies_renames_resolved_before_deadline_expiry
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py::test_repair_deadline_defers_unexamined_refs
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_rename_repair.py::test_repair_scans_rename_history_once_per_kind
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_every_aggregate_writer_converges_regardless_of_publish_status
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_index_harness_asserts_against_durable_store_truth
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_rebuild_carries_forward_bead_row_when_bead_store_commit_is_stale
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_rebuild_carries_forward_row_when_sidecar_commit_is_stale
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_rebuild_carries_forward_rows_from_invisible_sidecar_clone
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_rebuild_drops_bead_row_deleted_from_fresh_bead_store
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_rebuild_drops_rows_deleted_from_visible_sidecar_companion
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_remove_rows_prunes_aggregate_even_when_sidecar_is_invisible
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_aggregate.py::test_stale_preview_is_rejected_and_retried_rather_than_clobbering
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_backfill_bead_endpoint_links_is_additive_and_idempotent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_bead_bead_row_lives_in_the_event_stream
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_bead_endpoint_is_not_written_to_sidecar_json
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_bead_load_includes_incoming_rows_stored_on_the_target_bead
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_bead_merge_includes_sidecar_and_deduplicates
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_bead_owned_rows_skip_a_second_bead_store_reduction
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_bead_rows.py::test_plan_implements_bead_reaches_the_bead_from_either_direction
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_link_index.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_project_key.py::test_assembled_relations_are_builtins_then_plugins_then_config
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_a_stale_projected_row_disappears_once_its_rule_stops_matching
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_a_stored_row_beats_a_projected_row_with_the_same_identity
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_bead_neighborhood_excludes_projected_rows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_every_aggregate_writer_converges_with_projected_rows_present
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_load_artifact_rows_excludes_projected_rows_for_an_aggregate_only_ref
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_projected_rows_are_materialized_into_the_aggregate
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_projected_rows_never_reach_sidecar_or_bead_storage
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_remove_rows_refuses_to_delete_a_purely_projected_pair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_remove_rows_still_removes_a_stored_row_sharing_no_identity_with_projected
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_stored_link_keys_excludes_projected_rows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_projected.py::test_volume_smoke_12500_projected_rows_rebuild_inside_budget
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_durable_sidecar_rows_builds_pass_context_once
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_durable_sidecar_rows_dedupe_before_filter_does_not_weaken_publishability
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_durable_sidecar_rows_resolves_each_agent_ref_once
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_durable_sidecar_rows_resolves_each_distinct_agent_ref_once
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_reconcile_agent_rows_use_store_workspace_context
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_reconcile_aggregate_collects_sidecar_rows_from_known_workspace_stores
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_reconcile_aggregate_keeps_rows_with_unpublished_agent_endpoints
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_reconcile.py::test_reconcile_aggregate_skips_unreadable_sibling_workspace_sidecar
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_derived_bead_endpoint_upsert_does_not_increment_uses
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_file_file_row_persists_in_the_aggregate
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_prompt_ref_upsert_converges_uses_instead_of_incrementing
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_remove_rows_can_target_one_relation
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_remove_rows_drops_every_edge_between_a_pair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_reserved_relation_is_rejected
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_undirected_related_is_idempotent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_upsert_canonicalizes_historical_aliases
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_rows.py::test_upsert_writes_both_sidecars_and_rebuilds_aggregate
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_sidecar.py::test_malformed_sidecar_index_is_fail_loud
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_sidecar.py::test_missing_sidecar_root_is_not_an_error
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_artifact_link_store_sidecar.py::test_schema_v1_sidecar_file_is_unsupported_after_graduation
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_commit_store_artifact_link_derivation.py::test_derives_for_changed_markdown_files_and_skips_the_links_dir
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_agent_url_finds_family_lane_page_in_local_sidecar
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_agent_url_links_family_member_without_anchor
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_agent_url_links_registered_family_lane
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_agent_url_resolves_project_from_sidecar_anchor
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_agent_url_reuses_and_refreshes_agent_name_registry_snapshot
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_plan_url_accepts_legacy_repo_relative_reference
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_plan_url_resolves_logical_reference_to_blob_url
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_hosted_links.py::test_resolution_is_cached_across_many_plans
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_locally_changed_plan_with_missing_parent_still_errors
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_non_git_plan_tree_keeps_the_strict_parent_error
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_published_plan_is_clean_once_the_parent_lands
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_published_plan_with_unpublished_parent_only_warns
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_repair_errors_on_a_locally_changed_missing_parent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_link_parent_scope.py::test_repair_reports_the_unpublished_parent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_default_still_skips_prompt_section_without_snapshot
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_installs_prompt_section_when_snapshot_is_expected_but_absent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_installs_reciprocal_prompt_section_when_snapshot_exists
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_leaves_unpaired_plan_unlinked_without_prompt_snapshot
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_preserves_existing_prompt_section_when_snapshot_is_absent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_produces_valid_bidirectional_pair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_projects_prompt_parent_and_bead_in_canonical_order
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_rebases_authored_parent_for_destination
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_rejects_malformed_header_before_writing_destination
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_reuses_existing_destination_create_time
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_archive_with_expected_snapshot_produces_valid_bidirectional_pair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_archive.py::test_consecutive_archives_are_byte_identical
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_agent_registry_snapshot_failure_is_diagnostic
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_artifact_metadata_paths_collapse_to_one_plan_key
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_builds_sorted_rendering_records_from_one_history_walk
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_epic_rollup_ignores_parent_cycles
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_epic_rollup_reads_bullets_and_legacy_parent_without_changing_tales
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_family_members_collapse_to_one_lane_with_member_link_hint
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_history_failure_keeps_artifact_results_and_reports_diagnostic
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_legacy_member_tag_uses_its_recorded_destination
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_associations.py::test_snapshots_agent_registry_once_for_many_plan_associations
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_project_plan_header_sections_installs_supplied_prompt_path
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_project_plan_header_sections_skips_absent_prompt_path
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_degrades_to_unlinked_label
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_does_not_link_a_bead_the_store_lost
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_keeps_link_when_store_cannot_be_read
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_omits_and_removes_without_frontmatter
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_prefers_bead_id_and_links_hosted_page[bead: sase-ai.8\n]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_prefers_bead_id_and_links_hosted_page[bead_id: sase-ai.8\nbead: ignored-fallback\n]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_header_writes.py::test_refresh_bead_section_reuses_supplied_known_bead_ids
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_links_refresh.py::test_refresh_backfills_bead_section_from_frontmatter
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_links_refresh.py::test_refresh_dry_run_write_and_second_write_are_idempotent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_links_refresh.py::test_refresh_plan_scope_rejects_missing_reference
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_links_refresh.py::test_refresh_reports_unresolved_legacy_parent_without_dropping_it
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_plan_links_refresh.py::test_refresh_retargets_existing_prompt_section_to_agents_sidecar
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_doctor.py::test_commit_sdd_files_includes_links_index_but_still_excludes_sase
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_refresh.py::test_projection_refresh_commits_index_and_ignore_without_lock_residue
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_refresh.py::test_refresh_artifact_links_creates_binary_companion
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_refresh.py::test_refresh_artifact_links_follows_committed_research_rename
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_refresh.py::test_refresh_artifact_links_writes_v2_tables_after_plan_header
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd/test_referenced_by_refresh.py::test_refresh_referenced_by_dry_write_and_second_write_are_idempotent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_artifact_link_ignore.py::test_lock_ignore_appends_without_disturbing_existing_content
    failed in 20260910T223826Z-12f01fbc1c7a-2472624-full-run.json (head 12f01fbc1c7a)
    excluded by 13 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_all_configured_sidecars_found_connects_without_creation
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_missing_agents_sidecar_is_dropped_with_a_warning
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_missing_non_agents_sidecar_raises_actionable_error
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_non_project_directory_is_a_noop
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_non_remote_backed_policy_is_a_noop
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_auto_init.py::test_unmanaged_repo_is_a_noop
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_link_files.py::test_list_sdd_files_prefers_nested_plans_subdir_with_month_dirs
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_link_files.py::test_list_sdd_files_uses_flat_root_with_readme_only_plans_subdir
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_conflict_aborts_and_preserves_legacy_source
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_existing_positive_clone_adopts_new_legacy_artifacts_without_provider
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_existing_positive_clone_remains_usable_offline
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_explicit_init_denial_is_forwarded_for_managed_repo
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_first_materialization_fails_closed_without_positive_provider_result[None]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_first_materialization_fails_closed_without_positive_provider_result[authentication failed]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_local_and_in_tree_artifacts_are_imported_without_deleting_in_tree
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_materialization_bootstraps_primary_and_numbered_workspace
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_materialization_is_idempotent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_materialization_recovers_from_concurrent_sidecar_push
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_mismatched_local_git_repo_is_imported_via_staging
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_old_negative_record_is_retried_and_replaced
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_unmanaged_repo_refuses_materialization_before_provider_create
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_materialize.py::test_versioned_stale_clone_defers_overlap_and_skips_runtime_metadata
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_plan_ref_display.py::test_a_legacy_path_below_the_cwd_still_resolves
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_plan_ref_display.py::test_a_legacy_path_that_resolves_to_itself_renders_once
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_plan_ref_display.py::test_a_malformed_reference_is_reported_not_treated_as_legacy
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_plan_ref_display.py::test_exact_resolution_reports_the_reference_and_the_path
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_plan_ref_display.py::test_month_drift_is_marked_rather_than_hidden
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_repository_transaction_failures.py::test_injected_continue_failure_aborts_after_semantic_repair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_cleanup_push_warns_and_next_run_pushes_existing_commit
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_import_push_preserves_schema_two_and_rerun_retries
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_accepts_minimal_config_and_projection_store
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_no_publish_copies_and_cleans_without_commits_or_pushes
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures
    failed in 20260825T120518Z-51f6369b34bc-737472-full-run.json (head 51f6369b34bc)
    excluded by 5 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/sdd_store/test_sidecar_init_creation.py::test_agents_init_uses_hidden_root_and_records_every_sidecar_role
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_init_creation.py::test_custom_sidecar_init_uses_pinned_private_provider_options
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_init_creation.py::test_split_init_materializes_plans_and_custom_role_without_research
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_init_creation.py::test_split_init_no_publish_writes_plans_and_beads_without_commits_or_pushes
    failed in 20260910T223826Z-12f01fbc1c7a-2472624-full-run.json (head 12f01fbc1c7a)
    excluded by 13 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_init_reconciliation.py::test_split_init_cuts_over_changed_pinned_sidecar
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_sidecar_init_reconciliation.py::test_split_init_re_records_stale_research_sidecar
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/sdd_store/test_workspace_clone.py::test_strict_clone_failure_with_no_record_names_repo_init_remedy
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/service/test_service_config.py::test_a_fatal_section_error_raises_service_config_error
    failed in 20260917T145701Z-797feeb62dcb-3110794-full-run.json (head 797feeb62dcb)
    excluded by 4 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/service/test_service_config.py::test_a_local_layer_service_section_is_ignored_with_a_warning
    failed in 20260917T145701Z-797feeb62dcb-3110794-full-run.json (head 797feeb62dcb)
    excluded by 4 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/service/test_service_config.py::test_an_overlay_replaces_a_plugin_declared_entry_field_whole
    failed in 20260917T145701Z-797feeb62dcb-3110794-full-run.json (head 797feeb62dcb)
    excluded by 4 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/service/test_service_config.py::test_the_real_default_config_composes_scheduler_enabled_gateway_disabled
    failed in 20260917T145701Z-797feeb62dcb-3110794-full-run.json (head 797feeb62dcb)
    excluded by 4 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/shells/test_followup_vcs_preallocation.py::test_extract_directives_records_starter_vcs_ref
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/shells/test_followup_vcs_preallocation.py::test_gate_followup_recovers_vcs_ref_from_composed_prompt_without_meta
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/shells/test_followup_vcs_preallocation.py::test_gh_gate_followup_is_spawned_with_preallocation_env
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/shells/test_shells_substrate.py::test_create_family_shell_member_layers_kind_role_and_metadata
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_binding_smoke.py::test_projects_view_reports_truncated_patch_rows_through_real_binding
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_binding_smoke.py::test_statistics_facade_smoke_through_real_bindings
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_inherited_monitor_id_matches_ordinary_start_semantics
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_overlapping_serial_family_does_not_double_count
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_parallel_members_add_their_own_slots
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_shared_family_name_across_projects_counts_separately
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_standalone_agent_matches_python_occupancy
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/stats/test_runner_occupancy_parity.py::test_workflow_step_does_not_occupy
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_builtin.py::test_every_builtin_spec_validates_and_has_a_stable_digest
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_flag_project_type.py::test_flag_cannot_be_created_through_bead_create
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_flag_project_type.py::test_flag_project_type_is_in_the_live_catalog
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_project_config.py::test_new_project_type_defines_new_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_project_config.py::test_replace_list_strategy_resets_earlier_layers
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_project_config.py::test_use_override_deep_merges_sibling_keys
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_project_config.py::test_use_override_prefix_names_the_original_provider
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_project_config.py::test_use_override_still_rejects_a_wrong_provider_prefix_after_an_override
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_registry_cwd.py::test_registry_rebuilds_across_chdir
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_snapshot.py::test_describe_snapshot_drift_names_digest_and_package
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_snapshot.py::test_describe_snapshot_drift_names_new_live_type
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_candidates_accepts_valid_spec_with_provenance
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_candidates_first_plugin_wins_duplicate
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_candidates_reject_plugin_shadowing_builtin
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_explicit_create_refusal_changes_digest
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_omitted_create_refusal_does_not_change_digest
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_presentation_hash_is_stable_across_calls
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_presentation_hashes_missing_accent_into_curated_palette
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_presentation_keeps_declared_glyph_and_accent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_presentation_warns_on_duplicate_resolved_color
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_validate_task_type_spec_accepts_flag_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_validate_task_type_spec_rejects_reserved_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/task_types/test_validation.py::test_validate_task_type_spec_returns_stable_digest
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_cleanup_test_data.py::test_cleanup_end_to_end_preserves_production_and_near_miss_rows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_health.py::test_health_payload_empty_store
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_health.py::test_health_payload_queries_real_local_store
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_snapshot.py::test_snapshot_empty_store_is_friendly
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_snapshot.py::test_snapshot_json_has_store_metadata
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_snapshot.py::test_snapshot_rich_groups_local_values
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_snapshot.py::test_snapshot_subsystem_filter_is_case_insensitive
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_status.py::test_status_renders_local_details
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_cli_status.py::test_status_reports_store_counts_and_freshness
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/telemetry/test_ingestion.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_testing.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_testing.py::test_ace_page_group_reports_reset_hook_leaks
    failed in 20260909T202355Z-0879bfe5fddb-786186-full-run.json (head 0879bfe5fddb)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_tui_app.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ace_wait.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_artifact_layout_cli_migrates_verifies_and_rolls_back
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_artifact_layout_migrate_persists_manifest_and_records_entry_failure
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_artifact_path_helpers_resolve_legacy_to_existing_day_shard
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_create_artifacts_directory_canonicalizes_project_alias
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_create_artifacts_directory_uses_day_shards_for_ace_run
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_layout.py::test_launch_artifacts_dir_uses_day_shards_for_ace_run
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_declare_lifecycle_coverage
    failed in 20260826T185604Z-8d074c8dd3c6-3483716-full-run.json (head 8d074c8dd3c6)
    excluded by 9 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
    failed in 20260826T185604Z-8d074c8dd3c6-3483716-full-run.json (head 8d074c8dd3c6)
    excluded by 10 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 23 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_agent_artifact_startup_fixtures.py::test_dismissed_archive_fixture_covers_shards_legacy_and_corrupt_files
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_attachment_discovery.py::test_agent_tag_matches_projects_global_lane_tags_onto_local_members
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_attachment_discovery.py::test_collect_agent_paths_from_extra_repo_base_range_and_untracked
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_attachment_discovery.py::test_extra_repo_commit_paths_match_lane_tagged_family_commits
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_attachment_discovery.py::test_extra_repo_commit_paths_require_matching_agent_and_machine_tags
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_attachment_discovery.py::test_extra_repo_scan_can_exclude_sdd_internal_paths
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_agent_bead_display_finds_bead_in_another_known_project
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_agent_bead_display_finds_split_sidecar_root
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_agent_bead_display_uses_agent_workspace_before_cwd
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_agent_bead_display_uses_explicit_project_before_cwd
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_agent_bead_display_uses_managed_checkout_primary_workspace
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_bead_display.py::test_local_only_lookup_never_materializes_or_syncs_store
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_excludes_current_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_resolves_latest_completed_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_agent_name_template_suffix_shape_resolves_latest_completed_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_explicit_completed_agent_uses_done_response_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_failed_agent_with_done_response_path_carries_failure_payload
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_failed_agent_without_marker_paths_uses_timestamp_chat_scan
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_failed_agent_without_transcript_emits_launch_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_main_emits_parseable_json
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_malformed_metadata_is_ignored
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_missing_chat_history_fails_clearly
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_mixed_successful_and_failed_agents_keep_order_and_failure_marker
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_multiple_agents_resolve_in_invocation_order
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_multiple_aliases_to_same_transcript_are_coalesced
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_omitted_name_excludes_current_artifacts_dir
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_omitted_name_uses_most_recent_named_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_successful_agent_source_has_no_failure_key
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name.py::test_unreadable_transcript_is_rejected_before_loading
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_clan.py::test_agent_then_overlapping_clan_keeps_unique_later_member
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_clan.py::test_clan_and_agent_sources_preserve_parent_order
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_family.py::test_agent_then_overlapping_family_keeps_unique_later_member
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_family.py::test_family_and_explicit_member_duplicate_transcript_are_coalesced
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_family.py::test_family_source_includes_completed_members_in_chain_order
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_family_gate.py::test_explicit_gate_member_fork_yields_gate_alone
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_chat_from_name_tribe.py::test_mixed_tribe_and_named_fork_parents_preserve_order
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_dismiss_artifact_cleanup.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_dismiss_in_memory.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_dismiss_in_memory.py::test_bulk_dismiss_transaction_uses_one_notification_update
    failed in 20260911T015547Z-1546398faaea-857097-full-run.json (head 1546398faaea)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_dismiss_names.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_dismiss_persistence.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_dismiss_persistence.py::test_dismiss_workflow_parent_persistence_uses_pre_removal_snapshot
    failed in 20260911T015547Z-1546398faaea-857097-full-run.json (head 1546398faaea)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_dismiss_persistence.py::test_do_dismiss_all_persistence_callback_runs_deferred_work
    failed in 20260911T015547Z-1546398faaea-857097-full-run.json (head 1546398faaea)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_group_revival_e2e.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_group_revival_execution.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_group_revival_routing.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_kill_bulk.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_kill_phase1_async_io.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_kill_single_actions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_kill_single_execution.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_kill_single_persistence.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_launch_validation.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_agent_loader_dedup_pid_reuse.py::test_pid_reuse_merges_running_agents_with_missing_suffix
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_dedup_pid_safety_net.py::test_pid_dedup_safety_net
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_epic_created_status.py::test_plan_root_without_concrete_child_does_not_synthesize_planner
    failed in 20260827T221318Z-f07abbec800e-3849983-full-run.json (head f07abbec800e)
    excluded by 5 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_incomplete_history.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_incomplete_history_dedup.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_merges_running_shadow_metadata
    failed in 20260915T153752Z-53c6c51c3b09-1762460-full-run.json (head 53c6c51c3b09)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_running_home.py::test_remote_resolved_running_home_record_has_no_local_effects
    failed in 20260913T112546Z-f3a39fa835c9-3603452-full-run.json (head f3a39fa835c9)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_self_heal_cleanup.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_followup_roots.py::test_apply_status_overrides_ap5_workflow_children_after_code_handoff
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_promoted_plan_family.py::test_promoted_family_unreviewed_tale_projects_onto_root
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_question_families.py::test_apply_status_overrides_question_only_family_without_followup_is_question
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_questions.py::test_apply_status_overrides_plan_chain_root_step_projection_unchanged
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_questions.py::test_apply_status_overrides_planner_child_with_answered_family_followup_is_done
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_tale.py::test_apply_status_overrides_active_code_keeps_planner_child_tale_approved
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_loader_status_override_tale.py::test_apply_status_overrides_completed_code_keeps_planner_child_tale_approved
    failed in 20260828T005100Z-794fbd3db9f8-2123091-full-run.json (head 794fbd3db9f8)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_model_timestamps.py::test_snapshot_agent_timestamps_display_includes_scalar_plan
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_monitor_stop_action.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_name_wipe.py::test_wipe_done_agent_clears_lookup_registry_and_notifications
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_extract_naming.py::TestExtractDirectivesImplicitForkWait::test_failed_fork_target_records_terminal_aware_dependency
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_extract_naming.py::TestExtractDirectivesImplicitForkWait::test_failed_fork_target_shadowed_by_live_namesake_still_waits
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_extract_naming.py::TestExtractDirectivesImplicitForkWait::test_monitor_starter_fork_records_agent_identity
    failed in 20260906T181300Z-ece5db3cc874-2867894-full-run.json (head ece5db3cc874)
    excluded by 2 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_exact_name_preferred_over_workflow
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_agent_by_workflow_name
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_dismissed_prefixed_artifact_without_done
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_finds_done_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_local_bare_and_qualified_selectors_share_exact_first_lookup
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_only_done_returns_none_when_no_done
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_only_done_skips_running
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_prefers_running_over_done
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_returns_none_when_not_found
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestFindNamedAgent::test_skips_dead_agent_without_done
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[epic_approved]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[noop]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::TestWaitSuccessOutcomeClassification::test_bare_named_agent_resolves_as_wait_success[plan_committed]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_lookup.py::test_bare_named_agent_with_plan_rejected_outcome_is_not_wait_success
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_child_keeps_exact_reference
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_template_suffix_uses_latest_concrete_name
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_names_resume.py::TestResumeAgentNames::test_resolve_resume_template_uses_latest_concrete_name
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_context.py::test_waited_agent_variables_load_as_fallback_context
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_plan_wait_exposes_plan_file_under_row_key
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_plan_wait_without_plan_path_exposes_nothing
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_plan_context.py::test_submitted_planner_populates_both_base_and_row_keys
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_workflow_context.py::test_submitted_plan_file_renders_in_later_workflow_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_output_variable_workflow_context.py::test_waited_producer_variables_render_in_later_workflow_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_audit.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_meta.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_meta.py::test_revive_existing_meta_without_name_preserves_stored_lookup
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_names.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_revive_status.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_search_cli.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agent_search_cli.py::test_agent_search_filters_artifact_link_facets
    failed in 20260825T224618Z-7015c7938d98-1286225-full-run.json (head 7015c7938d98)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_agy_integration_polish.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_alias_history_modal.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_alias_overrides_indicator.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_ancestors_children_panel.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_artifact_file_e2e.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_inventory.py::test_configured_chops_table_shows_summary_first[True]
    failed in 20260915T231151Z-f421051fdda8-2906371-full-run.json (head f421051fdda8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_output_contract.py::test_managed_tmp_reap_reports_pressure_min_age
    failed in 20260914T152147Z-16ee9c233645-2108299-full-run.json (head 16ee9c233645)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_proposal_launch.py::test_runner_all_skipped_typed_admission_succeeds_without_agent
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_proposal_launch.py::test_typed_chop_proposal_uses_durable_admission_and_chop_env
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_proposal_launch_clan_dispatch_e2e.py::test_typed_clan_batch_promotes_first_surviving_member_end_to_end
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_proposal_launch_clan_dispatch_e2e.py::test_typed_clan_batch_restores_sequential_member_waits_end_to_end
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_runner_script.py::test_run_configured_chop_once_records_failure_with_exit_code
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_capture_subprocess_diagnostic_bounds_and_sanitizes_output
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_capture_subprocess_diagnostic_classifies_absent_and_missing_logs
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_capture_subprocess_diagnostic_reads_only_bounded_log_tail
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_run_configured_chop_once_preserves_subprocess_diagnostic
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_scheduled_error_digest_keeps_diagnostic_after_run_log_pruned
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_chop_subprocess_diagnostics.py::test_timeout_preserves_partial_subprocess_output
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_config_backend.py::test_canonical_routine_job_config_projects_public_names
    failed in 20260915T200238Z-5ca8a60d2d73-3651783-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_config_backend.py::test_public_projection_obeys_contract_flag
    failed in 20260915T200238Z-5ca8a60d2d73-3651783-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_config.py::test_default_builtin_chops_use_explicit_full_script_names
    failed in 20260826T004520Z-c7e0a29e50e6-3534859-full-run.json (head c7e0a29e50e6)
    excluded by 4 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_config.py::test_load_axe_config_rejects_agent_chops_with_source_provenance
    failed in 20260915T200912Z-5ca8a60d2d73-3787956-full-run.json (head 5ca8a60d2d73)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_config.py::test_load_axe_config_rejects_bare_string_chops
    failed in 20260916T122025Z-edde28a8dd4b-2863613-full-run.json (head edde28a8dd4b)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_history.py::test_failed_chop_records_failure_history
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_history.py::test_timed_out_chop_records_timeout_history
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_tick.py::test_chops_run_concurrently
    failed in 20260911T133436Z-a657cba42726-2196261-full-run.json (head a657cba42726)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_tick.py::test_one_chop_failure_does_not_block_others
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_tick.py::test_run_tick_error_handling
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_tick.py::test_run_tick_resumes_after_maintenance_cleared
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_lumberjack_tick.py::test_timeout_expired_records_error_and_continues
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_process_start.py::test_ensure_recovers_unpublished_lock_holder_after_grace
    failed in 20260825T215216Z-79e51b564ec9-95355-full-run.json (head 79e51b564ec9)
    excluded by 1 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_preflight_and_extraction_agree_on_a_failed_fork_parent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_axe_run_agent_phases_wait_chats.py::test_resolve_wait_chat_paths_resolves_indexed_template
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_bead_show_pager.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_bead_show_pager.py::test_bead_show_bare_token_follows_through_the_real_resolver
    failed in 20260915T141032Z-b2a10778e6f8-3874641-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_bead_show_pager.py::test_bead_show_document_renders_the_bead_id_as_a_bare_token
    failed in 20260915T141032Z-b2a10778e6f8-3874641-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_at_path_values.py::test_every_bead_free_text_option_is_classified
    failed in 20260828T142355Z-1858f75606b8-2119501-full-run.json (head 1858f75606b8)
    excluded by 2 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_auto_commit.py::test_fast_path_close_commit_omits_cascade_ids
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_auto_commit.py::test_fast_path_reclose_with_note_uses_note_commit
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_auto_commit.py::test_fast_path_update_commit_joins_every_changed_id
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_dep_rm.py::test_dep_rm_errors_are_nonzero_and_leave_the_batch_untouched
    failed in 20260915T163713Z-4e98613a1fbb-3265843-full-run.json (head 4e98613a1fbb)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[create_missing_parent]
    failed in 20260915T163713Z-4e98613a1fbb-3265843-full-run.json (head 4e98613a1fbb)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_id_shorthand.py::test_work_task_dry_run_uses_canonical_id_for_shorthand
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_mutation_push.py::test_bead_store_mutation_routes_explicit_cwd_to_commit_and_push
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_mutation_push.py::test_handle_bead_close_legacy_namespace_still_pushes
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_mutation_push.py::test_handle_bead_update_multi_id_commits_once_and_pushes_once
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_plus_one.py::test_plus_one_uses_canonical_commit_and_deferred_push
    failed in 20260915T152128Z-df87d68dcbc6-1348147-full-run.json (head df87d68dcbc6)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_refs.py::test_ref_add_reports_a_missing_issue_without_crashing
    failed in 20260915T181212Z-53035c96715c-1479629-full-run.json (head 53035c96715c)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_budget.py::test_show_full_reduces_the_bead_store_exactly_once
    failed in 20260915T141032Z-b2a10778e6f8-3874641-full-run.json (head b2a10778e6f8)
    excluded by 4 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_bead/test_cli_show_cross_project.py::test_ambiguous_prefix_names_candidates
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_cross_project.py::test_foreign_epic_expansion_uses_foreign_store_for_children
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_cross_project.py::test_foreign_full_id_renders_foreign_bead_and_project_label
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_cross_project.py::test_foreign_json_keeps_existing_envelope_shape
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_cross_project.py::test_known_project_without_materialized_store_is_actionable
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_cross_project.py::test_mixed_batch_uses_each_project_render_context
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_router.py::test_router_opens_each_foreign_store_once_and_closes_it
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_show_router.py::test_router_reports_unmaterialized_store
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 2 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_cleanup_decline_aborts_before_wipe_or_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_fresh_epic_has_no_cleanup_prompt_and_yes_skips_launch_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_json_implies_yes_to_all_noninteractively
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_no_flags_confirm_cleanup_then_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_noninteractive_cleanup_refuses_with_yes_to_all_remedy
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_yes_still_prompts_for_cleanup_but_skips_launch_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_yes_to_all_skips_both_prompts
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_dry_run_retry_filters_closed_phases_without_mutating
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_dry_run_warns_force_reuse_without_mutating
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_legacy_land_owner_and_launches
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_live_land_owner_and_launches
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_force_reuses_workflow_name_only_owner
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_passes_when_no_collisions
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_retry_allows_terminal_same_name_attempt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_collisions.py::test_work_retry_force_reuses_live_phase_owner_and_launches
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_contention_regressions.py::test_task_launch_waits_for_overlapping_epic_launch_and_claims_task
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_async_config_is_upgraded_to_sync_prelaunch_push
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_invokes_push_when_config_flag_enabled
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_no_push_flag_overrides_config
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_no_push_rejects_detached_store_before_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_push_failure_stops_before_launch_and_preserves_checkpoint
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_retry_push_failure_preserves_existing_checkpoint
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_rewrites_launch_query_and_env_after_graph_relocation
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_checkpoint.py::test_work_uses_sync_push_even_when_config_flag_disabled
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_matches_confirmed_launch_before_force_reuse_rewrite
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_never_mutates_or_launches
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_relaunches_from_stored_phase_sizes
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_renders_model_directives
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_uses_custom_big_epic_threshold
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch.py::test_dry_run_does_not_snapshot_epic_plan
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch.py::test_launch_snapshots_authoritative_plan_and_overwrites_on_relaunch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch.py::test_prelaunch_visibility_failure_never_reaches_agent_launcher
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch.py::test_snapshot_failure_warns_and_launches_without_snapshot_metadata
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch.py::test_work_launches_and_passes_rendered_multi_prompt
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_revalidate_raises_when_blocker_appears_after_preview
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_select_bead_work_launch_returns_blocked_targets_instead_of_raising
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_task_work_accepts_beadless_family_member
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_beadless_family_members_do_not_wedge_retry
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_conflicting_family_bead_still_blocks
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_direct_registry_name_mismatch_without_beads_blocks
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_dry_run_renders_blockers_without_mutating
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_expected_name_container_conflict_aborts_before_mutation[land-clan-container]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_expected_name_container_conflict_aborts_before_mutation[phase-clan-container]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_family_cleanup_failure_aborts_before_mutation[member-wipe-errors]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_family_cleanup_failure_aborts_before_mutation[residual-family-reservation]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_family_member_with_ancestor_epic_bead_is_accepted
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[name-still-reserved]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[wipe-raises]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_force_reuse_cleanup_failure_aborts_before_mutation[wipe-reports-errors]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_cleanup.py::test_work_reports_every_family_blocker_in_one_run
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_wrappers.py::test_work_dry_run_regular_epic_renders_vcs_launch_wrappers
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_launch_wrappers.py::test_work_dry_run_renders_patch_launch_wrappers
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_rollback_kills_partially_launched_agents
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_allows_already_ready_epic_and_launches_remaining_phases
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_checkpoint_failure_rolls_back_before_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_retry_does_not_unmark_already_ready_epic_on_launch_failure
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_rollback_restores_prior_in_progress_status
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_lifecycle.py::test_work_rolls_back_on_launch_failure
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_waiting_phase_that_starts_running_before_cleanup_is_preserved
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_all_closed_epic_launches_only_missing_lander
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_all_closed_epic_preserves_matching_live_lander_without_mutation
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_all_running_epic_is_idempotent_without_mutation
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_interrupted_phase_family_is_wiped_before_retry
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_preserves_running_phase_and_launches_only_missing_segments
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_relaunch_after_failure_joins_existing_epic_clan
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_retry_allows_legacy_epic_clan_container_skip
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_relaunch.py::test_work_stale_owner_round_trip_wipes_and_rewrites
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_epic_validation.py::test_work_accepts_flag_bead
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_from_plan_publication.py::test_git_sidecar_fresh_clone_sees_complete_graph_before_launch
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_from_plan_publication.py::test_plan_file_publication_passes_worker_lock_wait
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_from_plan_publication.py::test_plan_file_publication_returns_when_concurrent_worker_published_head
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_multi_target.py::test_multi_target_short_circuits_on_first_failure_with_json_lines
    failed in 20260906T233805Z-9c167a595b9a-1210975-full-run.json (head 9c167a595b9a)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_store_contention.py::test_epic_preclaim_exhaustion_rolls_back_the_ready_flag
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_store_contention.py::test_task_preclaim_exhaustion_reports_holder_and_claims_nothing
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_store_contention.py::test_task_preclaim_retries_past_a_contended_store
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_in_progress_task_with_live_assignee_is_idempotent_success
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_stale_in_progress_task_cleans_up_before_mutation
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_is_read_only
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_normalizes_legacy_sizeless_task_to_small
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.LARGE-@large-True]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.MEDIUM-@medium-False]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.SMALL-@small-False]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.XLARGE-@xlarge-True]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_dry_run_routes_all_sizes_through_phase_policy[PhaseSize.XSMALL-@xsmall-False]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_json_reports_task_launch_state
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_launch_query_includes_plan_for_large_tasks[PhaseSize.LARGE]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_launch_query_includes_plan_for_large_tasks[PhaseSize.XLARGE]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[Status.OPEN]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[Status.READY]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_persists_durable_stage_timing
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_task_work_refuses_mismatched_bead_owner_without_cleanup
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_yes_does_not_skip_destructive_cleanup_confirmation
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_zero_spawn_failure_restores_prior_task_state[checkpoint]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cli_work_task.py::test_zero_spawn_failure_restores_prior_task_state[launch]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cross_project.py::test_origin_for_bead_id_matches_custom_store_prefix
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cross_project.py::test_origin_for_bead_id_matches_registry_label
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cross_project.py::test_origin_for_bead_id_reports_registry_ambiguity
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cross_project.py::test_origin_for_bead_id_returns_unmaterialized_registry_match
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_cross_project.py::test_registry_prefix_disagreement_falls_through_to_store_stage
    failed in 20260915T133529Z-b2a10778e6f8-2999851-full-run.json (head b2a10778e6f8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_epic_from_plan.py::test_valid_plan_runs_real_bead_work_wave_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_epic_launch_proc.py::test_monitor_and_fallback_proc_share_guarded_execution_argv
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_snooze_surfaces.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_locks_local_integration_only
    failed in 20260908T180613Z-18b0a91a264d-2821200-full-run.json (head 18b0a91a264d)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_sync_worker_hygiene.py::test_managed_sync_worker_clears_failed_integration_marker
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_sync_worker_hygiene.py::test_managed_sync_worker_does_not_mutate_process_environment
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_sync_worker_hygiene.py::test_managed_sync_worker_redacts_credentials_in_push_errors
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_task_beads.py::test_create_task_prints_relocated_published_id
    failed in 20260915T163713Z-4e98613a1fbb-3265843-full-run.json (head 4e98613a1fbb)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_task_type_end_to_end.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead/test_work_epic_plan.py::TestEpicValidation::test_no_open_phases_raises
    failed in 20260822T170318Z-b351ceb33e3b-3254227-full-run.json (head b351ceb33e3b)
    excluded by 2 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead_flag_presentation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_bead_time_surface_coverage.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_changespec_status_indicators.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored
    failed in 20260908T164414Z-8c4f8fd22ae9-1221278-full-run.json (head 8c4f8fd22ae9)
    excluded by 18 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_agents_actions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_agents_fleet.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_agents_navigation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_agents_panels.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_axe.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_changespecs.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_availability_scope.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_catalog.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_catalog.py::test_run_workflow_command_is_contextual_retry_on_agents
    failed in 20260910T104750Z-eb7560fd5e3c-2181850-full-run.json (head eb7560fd5e3c)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_catalog_build.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_catalog_guards.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_context_extraction.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_execution.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_palette_e2e.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_palette_modal.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_command_palette_wiring.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_workflow_publication.py::test_commit_publishes_every_sidecar_inline_in_order
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_workflow_publication.py::test_fully_tagged_commit_and_resume_publish_each_sidecar_once
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_commit_workflow_publication.py::test_publication_step_records_release_evidence_for_this_run
    failed in 20260910T151830Z-2da11eb28790-3275164-full-run.json (head 2da11eb28790)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 1 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_config_edit_plan.py::test_plan_exact_key_path_does_not_split_dotted_mapping_key
    failed in 20260916T055747Z-2ff78b16868e-2872426-full-run.json (head 2ff78b16868e)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_config_inventory.py::test_inventory_effective_values_match_merge_golden
    failed in 20260916T055747Z-2ff78b16868e-2872426-full-run.json (head 2ff78b16868e)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_copy_agent_name.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_facade.py::test_find_gate_shell_by_gate_id_calls_rust_binding
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_facade.py::test_load_agent_artifact_records_calls_rust_binding
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_facade.py::test_verify_agent_artifact_index_reports_clean_index
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_facade.py::test_verify_agent_artifact_index_reports_missing_index
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_facade.py::test_verify_agent_artifact_index_reports_stale_and_missing_rows
    failed in 20260916T070859Z-297e6122b041-4140572-full-run.json (head 297e6122b041)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_agent_meta_wait_priority_scan_preserves_explicit_and_legacy_values
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_bounded_newest_first_limits_completed_without_hiding_incomplete
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_disable_prompt_step_markers
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_disable_raw_prompt_snippet
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_include_project_states_filters_scanner_projects
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_max_prompt_snippet_bytes_truncates
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_missing_root_returns_empty_snapshot
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_only_workflow_dirs_filters_records
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_scan_agent_artifact_dirs_honors_project_and_workflow_filters
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_scan_agent_artifact_dirs_reads_exact_unique_dirs
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_selective_marker_options_skip_payloads_but_keep_done_presence
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_snapshot_serializes_to_json
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_unreadable_artifact_dir_is_counted
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_unsupported_workflow_dirs_are_skipped
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_options.py::test_waiting_runner_slot_fields_match_filesystem_marker
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_records_are_sorted_deterministically
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_scan_returns_one_record_per_artifact_dir
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_basic.py::test_stats_count_decode_errors
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_done_record_parses_done_marker
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_failed_record_carries_error_and_traceback
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_mentor_dir_is_walked
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_non_repeat_done_record_defaults_repeat_stop_fields
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_repeat_stopped_record_carries_repeat_stop_fields
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_done.py::test_retried_records_link_via_lineage_fields
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_errors.py::test_malformed_agent_meta_is_skipped
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_errors.py::test_waiting_marker_decode_error_does_not_crash
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_index.py::test_bounded_source_clan_context_reconciles_through_index
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_index.py::test_index_query_honors_project_filters
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_agent_meta
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_auto_approve_plan_action
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_clan_attributes_through_scan_and_index
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_commit_diff_path_through_scan_and_index
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_output_variables_through_scan_and_index
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_carries_wait_completed_at
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_linked_repos_survive_scan_index_and_enrichment
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_running_record_prefers_canonical_agent_meta_tribe
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_running.py::test_scalar_plan_submitted_at_is_preserved
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_home_running_record_has_running_marker
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_workflow_root_record_has_state_and_steps
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_agent_scan_records_workflow.py::test_workflow_state_hidden_is_parsed
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_agent_cleanup_execution.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_facade/test_axe_chop.py::test_subprocess_diagnostic_facade_round_trips_through_rust
    failed in 20260907T043318Z-272ebad820f8-2829658-full-run.json (head 272ebad820f8)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_core_finalizer_facade.py::test_finalizer_facade_round_trips_deferred_instance_result
    failed in 20260824T152937Z-570b6be4b0c1-3976986-full-run.json (head 570b6be4b0c1)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_direct_typed_launch.py::test_direct_proc_queue_fields_round_trip_from_rust
    failed in 20260916T043230Z-b6b11f21556b-1081402-full-run.json (head b6b11f21556b)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_directive_edit.py::test_set_prompt_wait_formats_and_round_trips_priority
    failed in 20260909T020549Z-67f2ca6040cf-2235300-full-run.json (head 67f2ca6040cf)
    excluded by 28 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 4
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_directive_edit.py::test_set_prompt_wait_formats_runner_threshold
    failed in 20260909T020549Z-67f2ca6040cf-2235300-full-run.json (head 67f2ca6040cf)
    excluded by 28 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 4
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_directives_wait.py::test_wait_unknown_keyword_raises
    failed in 20260909T020549Z-67f2ca6040cf-2235300-full-run.json (head 67f2ca6040cf)
    excluded by 28 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 4
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_dismissed_agent_lifecycle.py::test_full_lifecycle_dismiss_then_revive_named_agent
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dismissed_agent_lifecycle.py::test_same_day_two_named_foo_get_unique_dismissed_names_then_revive
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dispatch_federation.py::test_facade_read_deadline_preserves_healthy_partial_host
    failed in 20260910T130725Z-0523874af159-625404-full-run.json (head 0523874af159)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_dispatch_federation.py::test_supervisor_spawns_worker_and_replaces_config
    failed in 20260907T060012Z-34fb561dd986-4150504-full-run.json (head 34fb561dd986)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_docs_getting_started_providers.py::test_getting_started_muse_grok_wording_separates_provider_selection
    failed in 20260822T211604Z-5c9fb7d07b43-2798417-full-run.json (head 5c9fb7d07b43)
    excluded by 2 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_file_references_substitution.py::test_process_file_references_normal_mode_non_home_unchanged
    failed in 20260909T120631Z-4068437a2c23-3846815-full-run.json (head 4068437a2c23)
    excluded by 1 scoped run(s), first 20260909T123510Z-4068437a2c23-169972.json (head 4068437a2c23)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_finalizer_declaration_channel_recovery.py::test_incident_shaped_recovery_prompt_attributes_paths_to_this_run
    failed in 20260824T152937Z-570b6be4b0c1-3976986-full-run.json (head 570b6be4b0c1)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_execution_ledger.py::test_provider_authored_skipped_fails_closed
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_execution_ledger.py::test_retryable_plugin_execute_stops_at_budget_boundary
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_extension_runtime.py::test_external_provider_request_includes_accepted_payload_and_obligations
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_extension_runtime.py::test_external_provider_runs_describe_validate_execute_verify
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_extension_runtime.py::test_plugin_timeout_and_malformed_output_fail_closed
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_live_e2e_cycles.py::test_live_command_and_fixture_plugin_run_in_order
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_finalizers_plan_integrity.py::test_worker_request_uses_sealed_selection_and_turn_identity
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_followup_prompt_helpers.py::test_with_feedback_parent_default_is_multi_prompt_segment_local
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_followup_prompt_helpers.py::test_with_feedback_xprompt_defaults_parent_from_family_attach
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_followup_prompt_helpers.py::test_with_feedback_xprompt_expands_from_parent_artifacts
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_deferred_launch_ignores_bare_fork_prose_inside_disabled_region
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_bare_resume_loads_resolved_chat_path
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork(planner, coder)]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_multi_parent_fork_renders_provenance_envelope[#fork:planner,coder]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_embedded_single_parent_fork_keeps_legacy_envelope
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_inherited_vcs_tag_is_not_injected_into_fork_history
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_fork_workflow.py::test_inline_deferred_fork_survives_workspace_removal_and_late_preprocessing
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_gate_cli_show.py::test_show_unknown_gate_shell_reference_exits_with_ref_error
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_gate_e2e_smoke.py::test_e2e_tale_plan_gate_structure_and_branches
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_git_setup_adopt_runner_workspace.py::test_pre_allocated_env_still_wins_over_parent_claim
    failed in 20260908T174305Z-a95d7c1ddfcd-2388239-full-run.json (head a95d7c1ddfcd)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_idle_cpu_diet_guardrails.py::test_axe_status_human_render_surfaces_spawn_rate_and_noop_ratio
    failed in 20260915T231151Z-f421051fdda8-2906371-full-run.json (head f421051fdda8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_idle_cpu_diet_guardrails.py::test_axe_status_json_wire_does_not_embed_chop_load
    failed in 20260915T231151Z-f421051fdda8-2906371-full-run.json (head f421051fdda8)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_idle_cpu_diet_guardrails.py::test_idle_fs_guarded_tick_records_zero_spawns_and_trigger_skips
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keybinding_footer_agent.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keybinding_footer_core.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keybinding_footer_status.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keybinding_footer_workflow.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_app_bindings.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_defaults.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_display_help.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_display_help.py::test_agents_help_lists_save_dismiss_marked_agents
    failed in 20260910T104750Z-eb7560fd5e3c-2181850-full-run.json (head eb7560fd5e3c)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_display_help.py::test_agents_help_uses_edit_hooks_for_fork_not_r_for_resume
    failed in 20260910T104750Z-eb7560fd5e3c-2181850-full-run.json (head eb7560fd5e3c)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_display_help.py::test_help_modal_labels_lowercase_a_as_agent_artifacts
    failed in 20260910T104750Z-eb7560fd5e3c-2181850-full-run.json (head eb7560fd5e3c)
    excluded by 9 scoped run(s), first 20260821T194632Z-28009002d5da-3576112.json (head 28009002d5da)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_e2e.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_patch_grouping_binding.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_registry_loading.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_registry_loading_legacy.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_registry_loading_panes.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_keymaps_validation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_kill_named_agent_dismiss.py::test_dismiss_named_agent_retires_done_row_without_kill
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_kill_named_agent_monitor.py::test_kill_named_family_stops_lane_monitor_without_killpg
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_kill_named_agent_monitor.py::test_kill_named_monitor_member_uses_canonical_stop
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_kill_named_agent_monitor.py::test_mobile_exact_name_kill_inherits_monitor_stop
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_launch_admission_dispatch.py::test_proc_queue_capacity_blocks_then_dispatches_when_idle
    failed in 20260916T043230Z-b6b11f21556b-1081402-full-run.json (head b6b11f21556b)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_launch_approval_tui.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_launch_condition_runtime.py::test_skip_does_not_dispatch_or_claim_resources
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_launch_default_indicator_pool_rotation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_launch_pane.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_override_indicator.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke.py::test_invoke_agent_records_provider_preprocess_shadow_measurement
    failed in 20260914T022321Z-65f876aafced-297933-full-run.json (head 65f876aafced)
    excluded by 2 scoped run(s), first 20260914T021302Z-65f876aafced-80985.json (head 65f876aafced)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_llm_provider_invoke.py::test_monitor_continuation_budget_compacts_raw_output_before_provider
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_overrides.py::test_invoke_agent_execution_provider_override_preserves_requested_metadata
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_overrides.py::test_invoke_agent_model_size_backward_compat
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_overrides.py::test_invoke_agent_model_size_override_env_compat
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_overrides.py::test_invoke_agent_model_tier_override_env
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_routing.py::test_invoke_agent_consumes_pool_once_per_invocation
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_routing.py::test_invoke_agent_no_directive_routes_through_configured_default_model
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_routing.py::test_invoke_agent_no_directive_routes_through_shipped_default_pool
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_routing.py::test_invoke_agent_resolves_model_alias_for_provider_and_model
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_llm_provider_invoke_routing.py::test_invoke_agent_warns_when_model_override_falls_back_to_default_provider
    failed in 20260912T202018Z-b681d5072ff0-2555603-full-run.json (head b681d5072ff0)
    excluded by 1 scoped run(s), first 20260905T230802Z-302e6d643af4-2600707.json (head 302e6d643af4)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result0-4-No agent found]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result1-5-already completed]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result2-5-Could not find PID]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_mobile_agent_kill_retry.py::test_kill_mobile_agent_maps_lifecycle_errors[result3-6-Permission denied]
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_model_picker_aliases.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_model_picker_jump.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_model_picker_modal.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_model_picker_options.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_model_picker_usage_hints.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_actions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_alias_description_rendering.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_alias_row_rendering.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_alias_state_rendering.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_bucket_navigation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_buckets.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_descriptions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_display.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit_custom.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit_outcomes.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit_preview.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit_reset.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_edit_reset.py::test_action_reset_configured_opens_preview_with_unset
    failed in 20260820T202329Z-f55b0b80f94d-3797525-full-run.json (head f55b0b80f94d)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_effort.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_history.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_jump.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_keymaps.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_layout.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_leader_mode.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_navigation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_override_flows.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_drain.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_duration.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_lifecycle.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_priority.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_soft_disable.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_modal_toggle.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_rendering.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_provider_routing.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_runner_limit.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_selector_builder.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_threshold.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_usage_alias_hints.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_models_panel_usage_modal.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_action_bindings.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_dismiss_actions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_jump.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_mark_and_tabs.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_mute_snooze.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_plus_ones.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_question_pane.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_read_tab.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_responses.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_scroll.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_section_toggle.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_sections.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_sent_at.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_snooze_status.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_tab_order.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_tab_routing.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_modal_tag_strip.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_sections.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_tab_style.py::test_the_bundled_defaults_match_the_builtin_fallbacks
    failed in 20260910T062525Z-5b330b242759-3062699-full-run.json (head 5b330b242759)
    excluded by 6 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_toast_polling.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_toast_polling_agent_refresh.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_toast_polling_concurrency.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_toast_polling_snooze.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_notification_toasts.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_parallel_agent_family_metadata.py::test_clan_wait_and_fork_resolve_only_after_every_member_completes
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_approval_modal_title.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_auto_approval.py::test_handle_plan_approval_auto_approve
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_auto_approval.py::test_handle_plan_approval_auto_marks_stale_telegram_action_handled
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_auto_approval.py::test_handle_plan_approval_auto_tale_skips_notification
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_auto_approval.py::test_handle_plan_approval_rechecks_auto_approve_while_waiting[approve]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_auto_approval.py::test_handle_plan_approval_rechecks_auto_approve_while_waiting[tale]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_filter_query.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_filter_query_index.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_filter_query_matching.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gate_wait.py::test_tale_gate_selection_translates_wait_into_runner_protocol
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_local_action_aliases_map_to_option_selections[approve-True-True]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_local_action_aliases_map_to_option_selections[commit-True-False]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_local_action_aliases_map_to_option_selections[tale-True-True]
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_plan_action_api_executes_selected_approval_options
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_plan_action_api_filters_coder_options_for_commit_preset
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_gates_action_api.py::test_plan_action_api_filters_protocol_overrides_for_tale_preset
    failed in 20260822T140059Z-104e02e4748e-3814552-full-run.json (head 104e02e4748e)
    excluded by 3 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_inventory_scanning.py::test_lightweight_live_plan_loader_promotes_unreviewed_done_plan
    failed in 20260827T191033Z-b69b07bc97a2-520333-full-run.json (head b69b07bc97a2)
    excluded by 13 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_inventory_scanning.py::test_plan_inventory_exact_timestamp_fallback_finds_sharded_ace_artifact
    failed in 20260827T191033Z-b69b07bc97a2-520333-full-run.json (head b69b07bc97a2)
    excluded by 13 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_inventory_scanning.py::test_plan_inventory_exact_timestamp_fallback_matches_recent_done_planner
    failed in 20260827T191033Z-b69b07bc97a2-520333-full-run.json (head b69b07bc97a2)
    excluded by 13 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_propose_derivation.py::test_derives_an_implements_row_for_the_archived_plan
    failed in 20260907T202041Z-ec6bc4a422f5-2697338-full-run.json (head ec6bc4a422f5)
    excluded by 3 scoped run(s), first 20260907T185001Z-a9f95ca5e645-609651.json (head a9f95ca5e645)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plan_rejection_response.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_plan_validate.py::test_facade_rehydrates_valid_tale_and_ordered_schema
    failed in 20260825T230712Z-012a66a65985-1574570-full-run.json (head 012a66a65985)
    excluded by 1 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_plugin_config_isolation.py::test_default_test_fixture_disables_plugin_config
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 1 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_proc_observer_isolation.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_artifact_staging.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_blank_lines.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_case_ops.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_change.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_char_search.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_delete.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_dot.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_indent.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_join.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_motions.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_number.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_paragraphs.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_percent.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_quote_bracket_objects.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_small_commands.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_surround.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_text_objects.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_toggle_case.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_normal_mode_yank_paste.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_vim_cursor_class.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_visual_mode.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_prompt_visual_mode_surround.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_propose_report_diff_path.py::TestProposeReportStep::test_emits_diff_path_and_proposal_id
    failed in 20260912T101137Z-00d5c40a8195-2729853-full-run.json (head 00d5c40a8195)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_propose_report_diff_path.py::TestProposeReportStep::test_no_diff_path_when_absent
    failed in 20260912T101137Z-00d5c40a8195-2729853-full-run.json (head 00d5c40a8195)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_propose_report_diff_path.py::TestProposeReportStep::test_no_meta_proposal_id_when_entry_id_missing
    failed in 20260912T101137Z-00d5c40a8195-2729853-full-run.json (head 00d5c40a8195)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_provider_disables_indicator.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_query_profile_agents.py::test_agents_profile_filterable_fields_are_all_accepted_by_the_parser
    failed in 20260825T224618Z-7015c7938d98-1286225-full-run.json (head 7015c7938d98)
    excluded by 1 scoped run(s), first 20260825T172951Z-b85cdffd3de6-3592604.json (head b85cdffd3de6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_qwen_opencode_integration_polish.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_reasoning_effort_metadata_enrichment.py::test_rust_scan_projects_reasoning_effort
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_revive_bundle_reprojection.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_run_agent_runner_scratch_cleanup.py::test_cleanup_launch_scratch_preserves_symlink_candidate
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_run_agent_runner_scratch_cleanup.py::test_cleanup_launch_scratch_removes_launch_assigned_directories
    failed in 20260915T142434Z-7a1a1ca3e465-68308-full-run.json (head 7a1a1ca3e465)
    excluded by 6 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_run_agent_runner_setup.py::TestBareForkSelfExclusion::test_bare_fork_resolves_older_agent_not_the_launching_run
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_run_agent_runner_setup.py::TestBareForkSelfExclusion::test_restores_inherited_artifacts_dir_after_expansion
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_carries_done_metadata
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_per_project_cap
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_all_agents_skips_noop_outcome
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_empty_when_processes_dead
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_skips_appears_as_agent_false
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_agents_snapshot.py::test_list_running_agents_skips_non_parallel_parent_timestamp_followups
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_running_field_ledger.py::TestWorkspaceClaimLedger::test_claim_then_release_round_trip_produces_two_records
    failed in 20260820T200515Z-0ec8609ce69b-3379027-full-run.json (head 0ec8609ce69b)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_selection_health_tool.py::test_fail_on_new_flake_still_flags_a_node_that_fails_again_after_its_fix
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_selection_health_tool.py::test_fail_on_new_flake_treats_an_uncollectable_node_as_stale_not_a_flake
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_selection_health_tool.py::test_json_output_is_parseable
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_snippet_text_filter.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_status_state_machine_transitions.py::test_draft_to_ready_allowed_when_sibling_children_reverted
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_empty_string
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_linked_tags_remove_attached_definitions
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_mixed_content_then_tags
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_mixed_legacy_and_prefixed_tags_at_end
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_multiple_blank_line_separated_tag_groups
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_no_tags
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_non_footer_markdown_definition_is_preserved
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_non_tag_uppercase_lines_preserved
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_only_tags
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_prefixed_tags_at_end
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_single_tag
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_tag_like_line_in_middle_not_stripped
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_tags_at_end
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_tags_separated_by_blank_line
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_strip_pr_tags.py::test_tags_with_trailing_blank_lines
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_over_budget_selection_escalates_rather_than_queueing_for_a_lease
    failed in 20260826T235300Z-2e5cd29e680a-3278236-full-run.json (head 2e5cd29e680a)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_over_budget_selection_runs_at_a_leased_width_and_releases_it
    failed in 20260826T235300Z-2e5cd29e680a-3278236-full-run.json (head 2e5cd29e680a)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_scoped_run_takes_no_token_while_the_pool_is_exhausted
    failed in 20260826T235300Z-2e5cd29e680a-3278236-full-run.json (head 2e5cd29e680a)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_suite_gate_integration.py::test_ungoverned_bypass_is_bounded_by_the_host_budget
    failed in 20260826T235300Z-2e5cd29e680a-3278236-full-run.json (head 2e5cd29e680a)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_fact_values_truncate_to_eighty_cells
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_facts_follow_required_spec_order_not_stored_order
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_frozen_chip_and_live_chip_share_the_same_formatter
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_markdown_fact_escapes_backticks_in_the_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_missing_or_empty_required_value_drops_that_pair
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_newlines_in_values_collapse_to_spaces
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_note_without_facts_is_just_the_human_name
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_projections_match_the_plan_examples
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_each_builtin_type[bug-\u2a2f-Bug-#FF5F5F]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_each_builtin_type[ci-\u2699-CI failure-#D7D700]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_each_builtin_type[feature-\u2726-Feature-#5FD75F]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_each_builtin_type[flake-\u2248-Flaky test-#00D7D7]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_each_builtin_type[memory-\u25a4-Memory-#8787FF]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_payload_parse_is_the_identity
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_resolve_uses_the_supplied_registry_instead_of_the_live_catalog
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_three_pair_cap_keeps_spec_order
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_presentation.py::test_unresolved_slug_degrades_to_question_mark_and_raw_field_names
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_gate_surfaces.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_builtin_task_types_resolve_their_pinned_presentation[bug-\u2a2f-#FF5F5F]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_builtin_task_types_resolve_their_pinned_presentation[ci-\u2699-#D7D700]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_builtin_task_types_resolve_their_pinned_presentation[feature-\u2726-#5FD75F]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_builtin_task_types_resolve_their_pinned_presentation[flake-\u2248-#00D7D7]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_builtin_task_types_resolve_their_pinned_presentation[memory-\u25a4-#8787FF]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_every_known_task_type_accent_is_pairwise_distinct_from_every_bead_type
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_task_type_chip_for_untyped_and_unknown_slugs_is_dim
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_task_type_chip_pads_to_a_fixed_width
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_task_type_chip_renders_glyph_and_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_task_type_cli_cell_pads_to_requested_width
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_task_type_cli_cell_renders_glyph_only
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_unknown_slug_degrades_to_a_dim_presentation_naming_the_slug
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_presentation.py::test_untyped_slug_is_a_dim_presentation_never_a_catalog_member
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_registry.py::test_registry_discovers_plugin_task_type_with_resolved_presentation
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_registry.py::test_registry_includes_builtins_with_no_plugins_or_project_config
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_registry.py::test_registry_project_config_overrides_plugin_type
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_task_type_registry.py::test_registry_rejects_plugin_shadowing_a_builtin
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_cost_plugin.py::test_cost_recorder_attributes_ace_settle_helpers
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_a_slow_gear_run_is_still_slower_than_the_full_lane
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_an_escalated_run_is_not_counted_against_the_baseline
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_health_payload_includes_duration_percentiles_and_slow_runs
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_health_payload_reports_flake_suppressed_matches
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_report_says_how_many_records_predate_the_schema
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_health_report.py::test_summary_reports_coverage_escalation_and_savings
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_manifest.py::test_options_reject_nonsense[environ2]
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_manifest.py::test_options_reject_nonsense[environ7]
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_manifest.py::test_paths_output_is_one_path_per_line
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_manifest.py::test_summary_line_reports_escalation
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_report.py::test_an_escalated_pre_schema_4_record_is_read_as_unconsulted
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_report.py::test_reports_the_estimate_against_the_budget
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_test_selection_report.py::test_says_nothing_about_a_gear_that_was_never_offered_anything
    failed in 20260914T132502Z-89879609d10a-3897264-full-run.json (head 89879609d10a)
    excluded by 1 scoped run(s), first 20260825T224023Z-678988da7343-1192385.json (head 678988da7343)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_timezone_display_artifacts.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_timezone_display_tui.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_tui_plan_epic_approval.py
    failed in 20260819T184720Z-a67ba351f026-669326-full-run.json (head a67ba351f026)
    excluded by 2 scoped run(s), first 20260819T173331Z-a67ba351f026-3341202.json (head a67ba351f026)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_completion_exposes_static_if_and_hides_proc_while_flag_is_off
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_flag_off_allows_static_boolean_if_and_strips_it
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_flag_on_rejects_invalid_code_directive_forms[%if(true)\nReview-parenthesized %if only supports should_run]
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_flag_on_rejects_invalid_code_directive_forms[%if+\nReview-static omission]
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_flag_on_rejects_invalid_code_directive_forms[%if:cond\nReview-static omission]
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_static_boolean_if_false_omits_prompt
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_typed_launch_units_code_contract.py::test_static_boolean_if_filters_before_typed_unit_planning
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_user_question_gates.py::test_shell_backed_question_settles_its_gate_shell_and_streams_output
    failed in 20260827T142418Z-be63e9c7dcd3-3991399-full-run.json (head be63e9c7dcd3)
    excluded by 2 scoped run(s), first 20260825T180951Z-f818f16a10c6-100814.json (head f818f16a10c6)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_vcs_log_filter_query.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_embedded.py::TestEmbeddedWorkflowExpansion::test_bang_embeddable_workflow_reference_errors_in_inline_prompt
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_embedded.py::TestEmbeddedWorkflowExpansion::test_embedded_workflow_hashes_inline_gets_newlines
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_embedded.py::TestEmbeddedWorkflowExpansion::test_standalone_workflow_reference_errors_in_inline_prompt
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_parallel.py::test_pre_expand_parallel_collects_post_steps
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_parallel.py::test_pre_expand_parallel_no_embedded_workflows
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_executor_script.py::TestScriptStepChdir::test_chdir_runner_bound_workspace_updates_env_and_callback
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_hitl_gates.py::test_agent_hitl_gate_uses_singleton_option_branches
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_hitl_gates.py::test_command_hitl_gate_keeps_rerun_and_edit_actions
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_canonical_workflow_and_steps_override_legacy_sources
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_current_checkout_wins_without_registry_read
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_does_not_resolve_disabled_registered_project
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_loads_athena_workflows_for_normalized_gh_ref
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_loads_known_project_workspace_from_other_cwd
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_uses_canonical_registered_project_identity[gh_org__proj]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_uses_canonical_registered_project_identity[proj]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_get_all_workflows_uses_canonical_registered_project_identity[short]
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_project.py::test_yml_files_discovered_as_workflow_files
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_xprompts.py::test_hidden_launcher_fixture_validates
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_xprompts.py::test_parse_xprompt_entries_skips_invalid_values
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_xprompts.py::test_workflow_and_local_xprompt_descriptions_parse
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workflow_loader_xprompts.py::test_workflow_local_xprompts_take_priority_over_globals
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_workspace_metadata_cache_teardown.py::test_metadata_patch_teardown_does_not_poison_a_later_test
    failed in 20260823T205246Z-67bcea32329a-694410-full-run.json (head 67bcea32329a)
    excluded by 1 scoped run(s), first 20260823T210934Z-67bcea32329a-959029.json (head 67bcea32329a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded
  tests/test_xprompt_catalog_render_build.py::test_render_html_contains_memory_badges
    failed in 20260824T153147Z-dffd6de576ed-4018518-full-run.json (head dffd6de576ed)
    excluded by 3 scoped run(s), first 20260820T055448Z-98764ad9221e-1476125.json (head 98764ad9221e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_finalizer_add_rows_match
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_finalizer_parenthesized_clause_replacement
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_finalizer_remove_omits_required
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_finalizer_repeated_directive_matches
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_finalizer_utf16_replacement_next_to_non_ascii
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_none_available_when_clear_is_legal
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_none_suppressed_when_required_exists
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_completion_parity.py::test_finalizer_helper_failure_degrades_without_invented_rows
    failed in 20260822T013605Z-2ce7483f2581-42948-full-run.json (head 2ce7483f2581)
    excluded by 1 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_directive_contract.py
    failed in 20260909T115635Z-4068437a2c23-3556728-full-run.json (head 4068437a2c23)
    excluded by 2 scoped run(s), first 20260820T153115Z-43b79bf12b5b-2835222.json (head 43b79bf12b5b)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_frontmatter_schema.py::test_input_type_schema_covers_known_types_with_aliases
    failed in 20260823T081631Z-50534e4f8132-3257868-full-run.json (head 50534e4f8132)
    excluded by 1 scoped run(s), first 20260822T195320Z-50534e4f8132-1764930.json (head 50534e4f8132)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/test_xprompt_swarm_expansion.py::test_static_if_false_omits_swarm_segment_before_nested_expansion
    failed in 20260916T030433Z-90e95fbd26bc-3256564-full-run.json (head 90e95fbd26bc)
    excluded by 12 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/workspace_provider/test_git_object_sharing.py::test_clean_reuse_preserves_unique_local_history_when_repoint_fails
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 5 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/workspace_provider/test_git_object_sharing.py::test_clean_reuse_rolls_back_when_replacement_primary_lacks_objects
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 5 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/workspace_provider/test_git_object_sharing.py::test_dirty_healthy_reuse_refuses_dependency_repoint
    failed in 20260916T004904Z-d2d30944dce4-8372-full-run.json (head d2d30944dce4)
    excluded by 5 scoped run(s), first 20260914T192833Z-ccd32537f54e-3417275.json (head ccd32537f54e)
    distinct change sets: 2
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
    failed in 20260827T225649Z-f07abbec800e-256047-full-run.json (head f07abbec800e)
    excluded by 8 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 3
    matched across unrelated changes; suspect a flake before a miss
    rules across those runs: context-baseline-stale, context-selection, contract-set-always, contract-set-only, no-baseline-depth-boost, serial-budget-exceeded
  tests/xprompt/test_highlight.py::test_flattens_directive_argument_over_placeholder
    failed in 20260916T021731Z-ea358dace46d-2074180-full-run.json (head ea358dace46d)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_highlight.py::test_flattens_overlapping_invocation_and_jinja_by_precedence
    failed in 20260916T021731Z-ea358dace46d-2074180-full-run.json (head ea358dace46d)
    excluded by 1 scoped run(s), first 20260828T195028Z-bcd6813d270a-3017944.json (head bcd6813d270a)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost
  tests/xprompt/test_repo_mention_catalog.py::test_glossary_claimed_name_excluded
    failed in 20260825T054945Z-882ba36f5ae8-969295-full-run.json (head 882ba36f5ae8)
    excluded by 1 scoped run(s), first 20260820T174320Z-4c304ad1fb78-685866.json (head 4c304ad1fb78)
    distinct change sets: 1
    rules across those runs: context-baseline-stale, contract-set-always, contract-set-only, no-baseline-depth-boost

  Known flakes are already excluded from this count (see
  flake-suppressed below); a non-zero count here means the selection
  heuristic itself is unsound as tuned. Raise SASE_TEST_SELECTION_DEPTH
  to 3 or add the missed tests to tests/contract_manifest.txt, then
  re-measure.

flake-suppressed: 1248 (12472 scoped run/failure matches)
  Excluded from false negatives above: each failed across unrelated
  change sets and had an independent full-run pass between failures.
  See reproducible_flake_nodeids in tests/_test_selection_health.py.
  tests/ace/tui/actions/test_agent_retry_family_projection.py::test_live_failed_plan_family_projects_retry_immediately
  tests/ace/tui/actions/test_agent_search_history_split.py::test_async_bounded_agents_search_load_rejects_stale_query
  tests/ace/tui/actions/test_prompt_glossary_panel_open.py::test_ctrl_g_g_from_insert_restores_insert_mode
  tests/ace/tui/actions/test_prompt_glossary_panel_open.py::test_gg_opens_memory_subtab_and_escape_restores_normal_focus
  tests/ace/tui/actions/test_prompt_memory_panel_open.py::test_ctrl_g_m_from_insert_restores_insert_mode
  tests/ace/tui/actions/test_prompt_memory_panel_open.py::test_gm_opens_panel_and_escape_restores_normal_focus
  tests/ace/tui/actions/test_prompt_save_snippet_pane.py::test_gt_new_snippet_loop_writes_publishes_expands_and_restores_cursor
  tests/ace/tui/actions/test_prompt_save_xprompt.py::test_ctrl_g_x_then_panel_ctrl_x_switches_to_snippet_mode
  tests/ace/tui/modals/test_snippet_name_modal.py::test_elsewhere_collision_loads_other_template_but_keeps_destination
  tests/ace/tui/test_agent_metadata_search.py::test_metadata_search_actions_are_agents_only
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_agent_counts_use_visible_top_level_agents
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_lane_headline_ignores_grouping_and_fold_presentation
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_mixed_family_and_clan_uses_lane_headline
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_parallel_root_without_loaded_members_falls_back_to_root
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_projects_parallel_family_member_statuses
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_total_counts_lone_hidden_starting_agent
  tests/ace/tui/test_agent_panel_index_integration.py::test_info_panel_total_counts_stay_coherent_at_every_starting_age
  tests/ace/tui/test_agent_panel_index_integration.py::test_real_status_transition_reveals_previously_hidden_starting_row
  tests/ace/tui/test_agent_runner_slots.py::test_refresh_runner_slot_context_orders_mixed_thresholds_by_admission_path
  tests/ace/tui/test_agent_runner_slots.py::test_refresh_runner_slot_context_ranks_all_waiters_while_pool_is_full
  tests/ace/tui/test_agent_runner_slots.py::test_weighted_capacity_reports_fractional_usage_and_blockers
  tests/ace/tui/test_agent_wait_resume.py::test_apply_wait_updates_parked_priority_in_place
  tests/ace/tui/test_agent_wait_resume.py::test_apply_wait_updates_parked_runner_threshold_in_place
  tests/ace/tui/test_agent_wait_resume.py::test_apply_wait_with_time_relaunches_with_replacement_directive
  tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_agents_refresh_hydrates_catalog_in_focus_mode
  tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_fleet_catalog_refresh_requests_legal_pages_and_logical_keys
  tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_fleet_refresh_apply_defers_behind_active_navigation
  tests/ace/tui/test_agents_onboarding.py::test_agents_onboarding_reappears_after_last_visible_agent_disappears
  tests/ace/tui/test_agents_pane_mount.py::test_agents_pane_mounts_activates_and_loads
  tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
  tests/ace/tui/test_agents_tab_current_project_seed.py
  tests/ace/tui/test_agents_zoom_panel_action.py::test_all_panel_fold_sweep_is_agents_only_underscore_reaches_next_query
  tests/ace/tui/test_agents_zoom_panel_action.py::test_fold_and_bead_snooze_never_contend_for_lowercase_z
  tests/ace/tui/test_agents_zoom_panel_action.py::test_metadata_sections_are_agents_only_and_forward_jump_is_all_tab
  tests/ace/tui/test_agents_zoom_panel_action.py::test_zoom_and_fold_actions_are_tab_gated
  tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
  tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version
  tests/ace/tui/test_artifacts_limit_keys.py::test_artifacts_prompt_bar_ctrl_k_still_opens_history
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes
  tests/ace/tui/test_artifacts_split_modes.py::test_clicking_split_badge_cycles_forward
  tests/ace/tui/test_axe_navigation.py::test_d_resolves_to_description_on_axe_and_diff_on_prs
  tests/ace/tui/test_axe_status_read_cache.py::test_run_json_mtime_change_invalidates_cache
  tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows
  tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section
  tests/ace/tui/test_config_pane_widget.py::test_config_filter_accepts_brackets_and_tab_switches_main_tab
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_opens_edit_modal
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_edit_sibling_repos_opens_normal_editor
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_updates_title_match_count
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_jump_selects_matching_path
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
  tests/ace/tui/test_config_pane_widget.py::test_config_pane_restores_session_bookmark_by_path
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_cancelled_failed_clean_and_non_git_skip_prompt
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_commit_task_reports_established_outcomes[result0-expected0]
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_commit_task_reports_established_outcomes[result1-expected1]
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_commit_task_reports_established_outcomes[result2-expected2]
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_confirm_submits_actual_written_source
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_declining_or_dismissing_commit_submits_no_task
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_dirty_source_uses_canonical_commit_prompt
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_runner_limit_write_requests_standard_agents_refresh
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_successful_write_toast
  tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_successful_write_toast_text
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_escape_cancels_without_moving
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_line_switches_to_jump_variant
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_moves_cursor_and_repaints_detail
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hints_cleared_when_filter_rebuilds_rows
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_is_noop_while_filter_input_has_focus
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_paints_hints_over_visible_rows_in_order
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections
  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_second_apostrophe_returns_to_prior_row
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_detail_ctrl_d_u_on_short_detail_is_noop
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_detail_ctrl_d_u_scrolls_without_stealing_focus
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_ctrl_d_and_ctrl_u_scroll_detail_only
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_g_and_G_jump_tree_cursor
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_h_l_collapse_expand_and_descend
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_j_k_cycle_single_visible_row
  tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_j_k_wrap_visible_tree_and_arrows_clamp
  tests/ace/tui/test_event_driven_pause_fixture.py::test_fixture_patch_does_not_leak_from_previous_test
  tests/ace/tui/test_feature_flags_pane.py::test_confirmed_toggle_restarts_axe_and_suppresses_duplicates
  tests/ace/tui/test_feature_flags_pane.py::test_flags_pane_forwards_config_prefix
  tests/ace/tui/test_feature_flags_pane_journeys.py::test_config_catalog_omits_flags_when_rollout_is_off
  tests/ace/tui/test_feature_flags_pane_journeys.py::test_disabling_rollout_flag_omits_flags_from_post_restart_catalog
  tests/ace/tui/test_fleet_agents.py::test_followed_batch_family_promotions_promote_explicit_singleton
  tests/ace/tui/test_fleet_agents.py::test_merge_catalog_pages_keeps_authoritative_counts_and_second_page_rows
  tests/ace/tui/test_fleet_agents.py::test_offline_fleet_fixture_projects_rows_counts_and_diagnostics
  tests/ace/tui/test_fleet_agents.py::test_project_fleet_agents_maps_pending_attention_onto_local_statuses
  tests/ace/tui/test_fleet_agents.py::test_project_fleet_agents_marks_followed_and_preserves_machine_sections
  tests/ace/tui/test_fleet_agents.py::test_project_fleet_agents_reads_followed_batch_entry_summaries
  tests/ace/tui/test_fleet_agents.py::test_project_fleet_agents_reads_worker_catalog_page_rows
  tests/ace/tui/test_fleet_agents_catalog_pages.py::test_catalog_next_cursors_by_host_keeps_continuations_separate
  tests/ace/tui/test_fleet_agents_catalog_pages.py::test_merge_catalog_pages_keeps_authoritative_counts_and_second_page_rows
  tests/ace/tui/test_fleet_agents_catalog_pages.py::test_project_fleet_agents_reads_worker_catalog_page_rows
  tests/ace/tui/test_fleet_agents_following.py::test_followed_batch_family_promotions_promote_explicit_singleton
  tests/ace/tui/test_fleet_agents_projection.py::test_offline_fleet_fixture_projects_rows_counts_and_diagnostics
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_carries_remote_explicit_zero_queue_weight
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_downgrades_fresh_chip_for_a_cached_aged_host
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_keeps_fresh_chip_for_a_live_fetch
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_keeps_running_for_alive_liveness
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_maps_pending_attention_onto_local_statuses
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_marks_followed_and_preserves_machine_sections
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_never_renders_running_for_a_dead_liveness_row
  tests/ace/tui/test_fleet_agents_projection.py::test_project_fleet_agents_sources_host_running_and_total_counts
  tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes
  tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation
  tests/ace/tui/test_notification_plan_gate.py::test_neutral_plan_submission_forwards_modal_capacity
  tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width
  tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_scroll_keys_move_detail_not_selection
  tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes
  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_dev_update_shows_all_commit_groups
  tests/ace/tui/test_proc_producer_inventory.py::test_inventory_records_infrastructure_and_classifications
  tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
  tests/ace/tui/test_startup_stopwatch_live_update.py::test_slow_mount_state_read_does_not_block_app_key_dispatch
  tests/ace/tui/test_startup_stopwatch_live_update.py::test_start_post_mount_background_loads_schedules_all_once
  tests/ace/tui/test_wait_modal.py::test_modal_returns_explicit_runner_threshold
  tests/ace/tui/test_wait_modal.py::test_runners_validation_accepts_zero_and_rejects_non_integers
  tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_returns_while_xprompt_file_read_is_blocked
  tests/ace/tui/tools/test_reader_core.py::test_discover_related_tool_artifact_dirs_uses_index_without_fallback_scan
  tests/ace/tui/widgets/test_agent_display_clan.py::test_family_header_recolors_only_real_container_name
  tests/ace/tui/widgets/test_agent_display_family_roster.py::test_loaded_plan_family_roster_uses_concrete_member_state_and_content
  tests/ace/tui/widgets/test_agent_queue_section.py::test_queue_field_renders_front_label_and_section_requires_real_position
  tests/ace/tui/widgets/test_agent_queue_section.py::test_queue_ladder_renders_duration_value
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_accept_kind_reopens_payload_then_accepts_document
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_bare_at_enter_submits_but_ctrl_l_and_navigation_accept
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_bare_at_opens_artifact_kinds_only
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_ctrl_t_reveals_gated_files_before_accepting_lone_kind
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_directory_accept_drills_down_and_file_accept_closes
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_mid_payload_accept_replaces_the_complete_detected_range
  tests/ace/tui/widgets/test_artifact_ref_completion_widget.py::test_revealed_files_survive_typing_and_reset_when_menu_closes
  tests/ace/tui/widgets/test_artifact_ref_sync_trigger.py::test_disabled_flag_inserts_the_second_colon_literally_and_submits_nothing
  tests/ace/tui/widgets/test_artifact_ref_sync_trigger.py::test_second_colon_is_consumed_and_never_enters_the_buffer
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_auto_xprompt_menu_toggle_disables_auto_open_only
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_auto_xprompt_menu_toggle_disables_slash_skill_auto_open
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_bare_hash_does_not_auto_open
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_bof_plus_routes_to_project_completion
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_cold_catalog_defers_without_sync_build_then_opens_when_warm
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_embedded_hash_token_does_not_auto_open
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_hash_name_auto_opens_xprompt_menu_without_extending
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_hash_plus_does_not_route_to_project_completion
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_no_matching_xprompt_does_not_show_placeholder
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_prompt_context_project_key_opens_same_project_xprompt_menu
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_single_match_auto_opens_without_accepting
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_slash_skill_cold_catalog_defers_without_sync_build
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_slash_skill_token_auto_opens_skill_panel_when_warm
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_standalone_marker_auto_opens_standalone_xprompts
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_typing_narrows_deleting_widens_and_space_dismisses
  tests/ace/tui/widgets/test_auto_xprompt_completion.py::test_vcs_tag_project_namespace_opens_project_xprompt_menu
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_builds_model_candidates_from_catalog
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_filters_leading_at_to_model_aliases
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_filters_model_candidates_by_short_alias
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_filters_provider_scope_in_paren_forms
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_filters_provider_scoped_models
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_directive_arg_completion_marks_provider_candidates_as_directories
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_model_alias_candidate_carries_resolution_and_provenance
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_model_candidate_preserves_structured_advisory_metadata
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_model_completion_keystroke_path_never_uses_override_lock
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_provider_scoped_model_completion_has_no_shared_extension
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_queue_capacity_completion_describes_limit
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_arg_completion_excludes_groups_and_deduplicates_insertions
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_arg_completion_excludes_selected_keywords_case_insensitively
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_arg_completion_orders_kinds_and_matches_bare_tribe
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_paren_arg_completion_suggests_runners_keyword
  tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_priority_completion_describes_order_and_default
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_directive_completion_matches_aliases_to_canonical_insertions
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_id_parenthesized_completion_advertises_identity_keywords
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_model_paren_completion_offers_alias_keys_and_model_values
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_bare_percent_auto_menu_uses_directive_gate
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_bare_percent_auto_opens_directive_panel
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_bare_percent_then_brace_clears_menu_and_inserts_alt_pair
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_ctrl_t_at_percent_opens_directive_panel
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_directive_invalid_context_does_not_auto_open
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_directive_typing_narrows_deleting_widens_and_space_dismisses
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_multi_candidate_directive_completion_accepts_ctrl_l
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_percent_partial_auto_opens_directive_panel
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_unknown_directive_does_not_show_placeholder
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_colon_after_effort_auto_opens_directive_value_panel
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_colon_after_model_auto_opens_model_value_panel
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_ctrl_t_unique_model_provider_row_drills_down
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_directive_arg_auto_menu_uses_directive_gate
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_directive_arg_completion_accepts_selection
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_directive_arg_refresh_narrows_widens_and_dismisses
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_directive_name_recipe_expands_as_snippet
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_model_arg_completion_replaces_partial_with_canonical_value
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_model_provider_row_acceptance_drills_down_to_scoped_menu
  tests/ace/tui/widgets/test_directive_value_completion_interactions.py::test_xprompts_enabled_colon_offers_bool_values
  tests/ace/tui/widgets/test_finalizer_completion.py::test_finalizer_menu_uses_warm_inventory_without_loading_config
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_auto_show_on_existing_frontmatter
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_ctrl_g_equals_focuses_panel_from_insert
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_dash_after_content_stays_passive
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_g_equals_again_closes_empty_panel_from_inside
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_g_equals_focuses_panel
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_g_equals_toggles_focus_with_populated_panel
  tests/ace/tui/widgets/test_frontmatter_panel.py::test_leading_dash_newline_stays_passive
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_ctrl_t_opens_history_words_after_local_miss
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_ctrl_t_mid_word_matches_goal_example
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_hyphenated_acceptance_preserves_right_hand_suffix
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_hyphenated_prefix_auto_accepts_from_prompt_history
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_navigation_ctrl_l_accept_preserves_suffix
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_navigation_enter_accept_preserves_suffix
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_history_single_match_auto_accepts_and_preserves_suffix
  tests/ace/tui/widgets/test_history_word_completion_accept.py::test_short_local_match_does_not_block_history_fallback
  tests/ace/tui/widgets/test_history_word_completion_cold_cache.py::test_cold_cache_placeholder_applies_loaded_words
  tests/ace/tui/widgets/test_history_word_completion_delete.py::test_ctrl_d_deletes_history_word_keeps_menu_open_and_toasts
  tests/ace/tui/widgets/test_history_word_completion_delete.py::test_ctrl_d_deleting_last_history_word_closes_menu
  tests/ace/tui/widgets/test_history_word_completion_delete.py::test_ctrl_d_history_word_falls_back_to_local_row_removal
  tests/ace/tui/widgets/test_history_word_completion_delete.py::test_smart_mode_ctrl_d_deletes_instantly_without_rebuilding_index
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_mode_mid_word_completion_preserves_suffix
  tests/ace/tui/widgets/test_history_word_completion_ranking.py::test_smart_ranking_prefers_related_word_over_more_recent_unrelated_word
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_history_refresh_does_not_yield_to_short_local_match
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_history_refresh_narrows_and_switches_back_to_local
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_history_refresh_preserves_hyphenated_shared_prefix
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_history_refresh_preserves_shared_prefix_narrowing_with_suffix
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_local_refresh_falls_through_when_only_short_match_remains
  tests/ace/tui/widgets/test_history_word_completion_refresh.py::test_structured_cursor_dismisses_active_history_words
  tests/ace/tui/widgets/test_model_alias_completion.py::test_cold_model_alias_catalog_shows_loading_without_blocking_keys
  tests/ace/tui/widgets/test_model_alias_completion.py::test_loading_model_alias_row_is_not_selectable
  tests/ace/tui/widgets/test_model_alias_completion.py::test_model_alias_catalog_cache_miss_after_loaded_reschedules
  tests/ace/tui/widgets/test_model_alias_completion.py::test_model_alias_catalog_failure_can_retry_from_unavailable_row
  tests/ace/tui/widgets/test_model_alias_completion.py::test_model_alias_catalog_request_does_not_revive_inactive_stack_pane
  tests/ace/tui/widgets/test_model_alias_completion.py::test_model_alias_catalog_worker_refreshes_matching_request
  tests/ace/tui/widgets/test_model_alias_completion.py::test_model_alias_catalog_worker_rejects_stale_prompt_state
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_accept_preserves_context_and_undo_redo
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_accept_replaces_whole_token_from_mid_token_cursor
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_auto_opens_and_enter_expands_without_submit
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_context_detects_prompt_boundaries[  *small-cursor3-small-*small]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_context_detects_prompt_boundaries[*-cursor0--*]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_context_detects_prompt_boundaries[Use *la-cursor1-la-*la]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_context_detects_prompt_boundaries[first\nnext *SM-cursor2-SM-*SM]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_context_rejects_protected_regions_and_unicode_columns
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_ctrl_l_accepts_selection_without_submit_or_newline
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_ctrl_t_opens_when_auto_directive_menu_is_disabled
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Explain *laX later-cursor5-Explain %m:@large later-%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Title\r\nUse *la\ttail-cursor6-Title\r\nUse %m:@large\ttail-%m:@large]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Use *la   now-cursor2-Use %m:@large   now-%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Use *la now-cursor1-Use %m:@large now-%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Use *la-cursor0-Use %m:@large -%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Use *la\nnow-cursor4-Use %m:@large \nnow-%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[Use *la\tnow-cursor3-Use %m:@large\tnow-%m:@large]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_edit_plan_is_cursor_complete[\U0001f642 *la\r\nnext-cursor7-\U0001f642 %m:@large \r\nnext-%m:@large ]
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_navigation_preserves_selection_while_filtering
  tests/ace/tui/widgets/test_model_alias_completion.py::test_star_alias_subtitle_omits_missing_description
  tests/ace/tui/widgets/test_model_alias_completion.py::test_unknown_star_alias_stays_literal_and_can_submit
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_accept_preserves_context_and_undo_redo
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_accept_replaces_whole_token_from_mid_token_cursor
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_auto_opens_and_enter_expands_without_submit
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_context_and_filtering_use_model_rows_only
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_ctrl_l_accepts_selection_without_submit_or_newline
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_ctrl_t_opens_when_auto_directive_menu_disabled
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_edit_plan_spacer_cases
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_navigation_preserves_selection_while_filtering
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_double_star_third_star_and_space_dismiss_completion
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_loading_model_rows_are_not_selectable
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_model_catalog_failure_can_retry_explicit_unavailable_row
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_model_catalog_worker_refreshes_only_matching_shortcut_kind
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_model_catalog_worker_rejects_stale_explicit_prompt_state
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_second_star_takes_over_when_alias_catalog_is_loading
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_second_star_takes_over_when_alias_rows_are_empty
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_star_shortcut_switches_between_alias_and_model_in_manual_session
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_unknown_double_star_stays_literal_and_can_submit
  tests/ace/tui/widgets/test_model_explicit_completion.py::test_warm_double_star_typing_never_builds_catalog_on_key_path
  tests/ace/tui/widgets/test_placeholder_completion.py::test_accept_replaces_inner_text_with_and_without_closing_bracket
  tests/ace/tui/widgets/test_placeholder_completion.py::test_accepting_a_saved_candidate_closes_the_bracket_either_way
  tests/ace/tui/widgets/test_placeholder_completion.py::test_auto_trigger_gains_saved_group_only_once_a_prefix_is_typed
  tests/ace/tui/widgets/test_placeholder_completion.py::test_automatic_trigger_never_accepts_a_lone_match
  tests/ace/tui/widgets/test_placeholder_completion.py::test_cold_cache_menu_gains_the_saved_group_when_the_cache_warms
  tests/ace/tui/widgets/test_placeholder_completion.py::test_ctrl_d_deletes_saved_placeholder_keeps_menu_open_and_toasts
  tests/ace/tui/widgets/test_placeholder_completion.py::test_ctrl_d_deleting_last_saved_placeholder_closes_menu
  tests/ace/tui/widgets/test_placeholder_completion.py::test_ctrl_d_on_prompt_placeholder_only_explains_without_deleting
  tests/ace/tui/widgets/test_placeholder_completion.py::test_ctrl_d_saved_placeholder_falls_back_to_local_row_removal
  tests/ace/tui/widgets/test_placeholder_completion.py::test_ctrl_t_explicitly_accepts_single_placeholder_with_auto_off
  tests/ace/tui/widgets/test_placeholder_completion.py::test_disabled_feature_reproduces_todays_placeholder_menu
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_bare_bracket_accepts_lone_prompt_before_saved_group
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_accepts_a_lone_saved_match_outright
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_accepts_lone_literal_prompt_match
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_accepts_lone_prompt_match_before_saved_group
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_leaves_multiple_prompt_matches_open
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_leaves_multiple_saved_matches_open
  tests/ace/tui/widgets/test_placeholder_completion.py::test_manual_trigger_shows_the_full_saved_list_at_a_bare_bracket
  tests/ace/tui/widgets/test_placeholder_completion.py::test_placeholder_free_prompt_stays_silent
  tests/ace/tui/widgets/test_placeholder_completion.py::test_refresh_keeps_the_highlighted_saved_candidate_across_an_edit
  tests/ace/tui/widgets/test_placeholder_completion.py::test_snippet_tabstop_opens_completion_and_survives_accept
  tests/ace/tui/widgets/test_placeholder_completion.py::test_typing_open_bracket_auto_opens_and_live_narrows
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_auto_trigger_hides_ranked_saved_group_until_a_prefix
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_cold_index_menu_re_ranks_once_the_cache_publishes
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_ctrl_d_removes_a_ranked_saved_row_without_rebuilding_the_store
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_ctrl_d_still_refuses_prompt_rows_on_the_ranked_path
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_disabled_index_reproduces_prompt_local_menu
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_recent_menu_reproduces_store_order_without_ranking_metadata
  tests/ace/tui/widgets/test_placeholder_completion_ranking.py::test_smart_menu_ranks_related_saved_tag_ahead_of_frequent_recent
  tests/ace/tui/widgets/test_prompt_at_prefix_completion.py::TestAtPrefixIntegration::test_at_prefix_directory_drilldown
  tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py::test_hash_at_expand_multiline_undo_is_single_step
  tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py::test_hash_at_expand_then_normal_mode_undo_restores_trigger
  tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py::test_hash_at_expand_undo_then_redo_restages_input
  tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py::test_hash_at_expand_undo_unstages_input_and_hides_panel
  tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py::test_hash_at_posts_snippet_requested_with_origin
  tests/ace/tui/widgets/test_prompt_escape_cancel.py::test_ctrl_c_still_cancels_with_stripped_prompt_text
  tests/ace/tui/widgets/test_prompt_escape_cancel.py::test_escape_clears_pending_operator_without_cancelling
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_accept_ctrl_l_inserts_selected_candidate
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_completion_state_resets_on_submit_and_cancel
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_directory_drilldown_on_accept
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_enter_accepts_completion_instead_of_submitting
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_escape_dismisses_completion_panel_and_enters_normal_mode
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_navigation_keys_update_highlight
  tests/ace/tui/widgets/test_prompt_file_completion.py::TestPromptFileCompletion::test_non_path_tab_still_expands_snippet
  tests/ace/tui/widgets/test_prompt_file_history_completion.py::TestFileHistoryCompletion::test_accept_inserts_path_at_cursor
  tests/ace/tui/widgets/test_prompt_file_history_completion.py::TestFileHistoryCompletion::test_ctrl_d_is_passthrough_for_file_kind
  tests/ace/tui/widgets/test_prompt_file_history_completion.py::TestFileHistoryCompletion::test_ctrl_d_on_last_remaining_entry_closes_panel
  tests/ace/tui/widgets/test_prompt_file_history_completion.py::TestFileHistoryCompletion::test_ctrl_d_removes_highlighted_entry_and_keeps_panel_open
  tests/ace/tui/widgets/test_prompt_file_history_completion.py::TestFileHistoryCompletion::test_typing_after_history_trigger_dismisses_panel
  tests/ace/tui/widgets/test_prompt_format.py::test_cursor_and_mode_changes_during_worker_are_preserved
  tests/ace/tui/widgets/test_prompt_format.py::test_edit_while_formatter_runs_is_responsive_and_discards_result
  tests/ace/tui/widgets/test_prompt_format.py::test_focus_change_does_not_retarget_multi_pane_format
  tests/ace/tui/widgets/test_prompt_format.py::test_formatter_error_and_ordinary_typing_leave_formatting_explicit
  tests/ace/tui/widgets/test_prompt_format.py::test_formatting_does_not_enter_insert_dot_repeat_capture
  tests/ace/tui/widgets/test_prompt_format.py::test_insert_ctrl_g_f_formats_and_maps_live_selection
  tests/ace/tui/widgets/test_prompt_format.py::test_newer_format_request_wins
  tests/ace/tui/widgets/test_prompt_format.py::test_normal_gf_formats_once_preserves_mode_and_is_one_undo_step
  tests/ace/tui/widgets/test_prompt_format.py::test_rebuilt_pane_discards_old_widget_result
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_bound_height_g_prefix_hints_show_remainder
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_hints_group_ctrl_x_with_mini_xprompt[insert]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_in_insert_mode_shows_insert_prefix_hints
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_in_normal_mode_shows_same_prefix_hints_as_insert
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_save_continuations_preserve_draft_and_clear_prefix[insert]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_save_continuations_preserve_draft_and_clear_prefix[normal]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_x_continuations_request_mini_xprompt_target_and_clear_prefix[insert-ctrl+x]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_x_continuations_request_mini_xprompt_target_and_clear_prefix[insert-x]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_x_continuations_request_mini_xprompt_target_and_clear_prefix[normal-ctrl+x]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_ctrl_g_x_continuations_request_mini_xprompt_target_and_clear_prefix[normal-x]
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_escape_cancels_insert_prefix_and_stays_insert_mode
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_escape_hides_pending_g_prefix_hints
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_g_in_normal_mode_shows_g_prefix_hints
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_normal_ctrl_g_continuation_dispatches_in_normal_mode
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_normal_ctrl_g_escape_cancels_prefix_and_stays_normal_mode
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_normal_unknown_ctrl_g_key_hides_hints_without_side_effects
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_real_terminal_ctrl_g_ctrl_c_cancels_all_from_insert
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_real_terminal_ctrl_g_ctrl_c_cancels_all_from_normal
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_unknown_g_prefix_key_hides_hints_without_side_effects
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py::test_unknown_insert_prefix_key_hides_hints_without_inserting
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py::test_counted_gg_jumps_to_target_line_after_hint_integration
  tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py::test_gg_still_jumps_to_buffer_start_after_hint_integration
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_ctrl_g_g_from_insert_posts_glossary_request
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_ctrl_g_g_from_normal_posts_glossary_request
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_gg_from_normal_posts_glossary_request
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_glossary_request_carries_identity_under_cursor
  tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py::test_glossary_request_is_none_when_catalog_is_cold
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_ctrl_k_requests_history_with_single_line_filter
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_dot_history_shortcuts_submit_as_plain_prompt_text[#gh:sase .]
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_dot_history_shortcuts_submit_as_plain_prompt_text[#gh:sase .x]
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_dot_history_shortcuts_submit_as_plain_prompt_text[.]
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_dot_history_shortcuts_submit_as_plain_prompt_text[.x]
  tests/ace/tui/widgets/test_prompt_history_trigger.py::test_full_stop_inserts_period_without_requesting_history
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_narrow_terminal_subtitle_keeps_readout_and_truncates_hints
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_soft_completion_visible_still_shows_readout
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_solo_pane_feedback_mode_shows_readout
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_solo_pane_readout_tracks_typing
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_solo_pane_subtitle_shows_readout
  tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py::test_vim_mode_switch_recolors_subtitle_digits
  tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py::test_initial_cursor_clamps_to_document
  tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py::test_initial_cursor_restores_middle_pane_on_fresh_bar
  tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py::test_missing_initial_cursor_still_parks_at_end
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_current_prompt_text_reflects_live_edits
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_initial_separators_render_stacked_panes
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_load_prompt_into_pane_keeps_frontmatter_when_entry_has_none
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_single_prompt_renders_one_solo_pane
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_single_prompt_with_frontmatter_lifts_to_panel
  tests/ace/tui/widgets/test_prompt_input_bar_stack.py::test_stack_title_and_separator_surface_agent_count
  tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py::test_ctrl_g_ctrl_g_on_single_pane_requests_active_text
  tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py::test_ctrl_g_g_on_single_pane_requests_active_text
  tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py::test_ctrl_g_g_on_stacked_bar_requests_whole_stack
  tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py::test_focused_normal_mode_ctrl_g_starts_prefix_and_shadows_global_binding
  tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py::test_focused_pane_ctrl_g_starts_prefix_and_shadows_global_binding
  tests/ace/tui/widgets/test_prompt_jinja.py::test_jinja_auto_pairing
  tests/ace/tui/widgets/test_prompt_jinja.py::test_jinja_ctrl_t_completion
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_ctrl_l_accepts_warm_xprompt_suggestion_before_debounce
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_completion_does_not_hide_ctrl_t_panel_path
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_directive_suggestion_replaces_only_with_ctrl_l
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_arg_name_and_bool_value_suggestions
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_before_period_preserves_period
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_required_text_accept_adds_double_colon_space
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_suggestion_accepts_with_ctrl_l_not_enter
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_suggestion_uses_canonical_project_namespace
  tests/ace/tui/widgets/test_prompt_live_completion.py::test_soft_xprompt_without_inputs_skips_space_before_punctuation
  tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py::test_gL_cancel_leaves_body_unchanged
  tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py::test_gL_converts_placeholders_to_inputs_and_invocation_slots
  tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py::test_gL_infers_jinja_inputs
  tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py::test_gL_prefills_body_and_commits_invocation
  tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py::test_gL_preserves_existing_helpers
  tests/ace/tui/widgets/test_prompt_memory_panel_entry.py::test_ctrl_g_m_from_insert_posts_memory_request
  tests/ace/tui/widgets/test_prompt_memory_panel_entry.py::test_gm_from_normal_posts_memory_request
  tests/ace/tui/widgets/test_prompt_memory_panel_entry.py::test_memory_request_carries_note_under_cursor
  tests/ace/tui/widgets/test_prompt_memory_panel_entry.py::test_memory_request_detects_live_memory_reference
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_active_section_reconciles_across_same_document_rerender
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_cheap_paint_preserves_section_until_enriched_layout_returns
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_get_content_height_reserve_uses_last_title_not_trailing_roster_row
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_resolve_section_at_row_still_resolves_fold_only_anchor
  tests/ace/tui/widgets/test_prompt_path_inventory.py::test_at_keystroke_does_not_stat_or_scan
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_cancel_failed_search_and_missing_pane_keep_search_register
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_counted_repeat_advances_across_multiple_prompt_panes
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_forward_repeats_cross_panes_and_skip_panes_without_matches
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_forward_search_previews_confirms_and_records_search_register
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_forward_search_register_is_shared_across_prompt_panes
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_large_buffer_search_jumps_even_when_overlay_is_skipped
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_normal_mode_escape_clears_highlights_but_keeps_repeat_search
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_prompt_stack_wrap_feedback_only_reports_global_boundaries
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_repeat_absent_from_every_pane_keeps_focus_cursor_and_register
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_repeat_search_n_and_shift_n_respect_recorded_direction
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_repeat_search_reports_not_found_after_buffer_changes
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_repeat_search_without_previous_search_is_hint_only
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_repeat_search_wraps_with_vim_style_feedback
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_reverse_repeats_cross_to_earlier_pane_and_shift_n_inverts
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_reverse_search_previews_previous_match_without_opening_help
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_reverse_search_register_direction_is_shared_across_panes
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_search_cancel_restores_origin_and_clears_highlights[ctrl+c]
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_search_cancel_restores_origin_and_clears_highlights[escape]
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_search_highlights_clear_on_insert_mode_entry
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_search_register_survives_prompt_stack_rebuild
  tests/ace/tui/widgets/test_prompt_search_interactive.py::test_search_updates_counter_as_query_grows_and_shrinks
  tests/ace/tui/widgets/test_prompt_snippets_panel_entry.py::test_ctrl_g_t_from_insert_posts_snippets_request
  tests/ace/tui/widgets/test_prompt_snippets_panel_entry.py::test_gt_from_normal_posts_snippets_request
  tests/ace/tui/widgets/test_prompt_snippets_panel_entry.py::test_snippets_request_seeds_call_under_cursor
  tests/ace/tui/widgets/test_prompt_snippets_panel_entry.py::test_snippets_request_seeds_known_bare_trigger
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_ctrl_g_minus_adds_bottom_pane_from_insert
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_adds_bottom_pane_from_normal
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_adds_empty_pane_without_explicit_vcs_tag
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_inherits_from_selected_pane
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_inherits_tag_after_directives_without_body
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_is_normal_mode_only
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_g_minus_uses_current_pane_after_focus_change
  tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py::test_plain_dash_no_longer_adds_pane_in_normal
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_bare_j_join_supports_count
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_bare_j_joins_active_pane_lines_and_does_not_focus
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_bare_k_without_lookup_target_does_not_focus_pane_or_bubble
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_ctrl_gk_focuses_previous_pane_from_insert_and_keeps_insert
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_ctrl_gk_focuses_previous_pane_from_normal_and_keeps_normal
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_ctrl_l_does_not_focus_pane_when_consumed_by_completion
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_g_prefix_nav_is_normal_mode_only
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_gj_focuses_next_pane_and_cycles_at_bottom_edge
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_gk_cycles_from_top_to_bottom
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_gk_focuses_previous_pane_from_normal
  tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py::test_gk_then_gj_round_trips_focus
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_comma_is_inert_now_that_stack_keymaps_moved_to_g_prefix
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_ctrl_gk_moves_active_pane_higher_from_insert_and_keeps_insert
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_g_prefix_reorder_is_normal_mode_only
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_gj_moves_active_pane_lower
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_gj_on_bottom_pane_wraps_to_top
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_gk_moves_active_pane_higher
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_gk_on_top_pane_wraps_to_bottom
  tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py::test_reorder_preserves_live_edits
  tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py::test_multi_pane_comma_reverses_char_search
  tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py::test_single_pane_comma_still_reverses_char_search
  tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py::test_typing_separator_stays_passive
  tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py::test_typing_separator_stays_passive_in_feedback_mode
  tests/ace/tui/widgets/test_prompt_stack_snippet_pane_lifecycle.py::test_gt_and_ctrl_g_t_request_snippet_target
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_ctrl_c_cancels_only_selected_pane_and_keeps_bar
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_ctrl_c_on_final_pane_cancels_whole_bar
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_ctrl_g_enter_submits_selected_pane_from_insert
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_ctrl_s_stashes_active_pane
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_enter_on_empty_selected_pane_opens_submit_choice
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_enter_on_final_pane_submits_whole_bar
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_enter_on_multi_pane_pushes_submit_choice_modal
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_enter_on_targeted_single_pane_pushes_submit_choice_modal
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_g_enter_drains_stack_one_pane_at_a_time
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_g_enter_on_single_pane_bar_submits_normally
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_g_enter_reattaches_frontmatter_to_single_pane_submit
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_g_enter_submits_selected_pane_and_keeps_bar
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_submit_choice_all_submits_whole_stack[a]
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_submit_choice_all_submits_whole_stack[ctrl+s]
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_submit_choice_current_submits_selected_pane
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_targeted_multi_pane_choice_rows_include_launch_and_save
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_targeted_single_choice_save_as_posts_save_as_request
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_targeted_single_choice_send_submits_draft
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_targeted_single_choice_write_posts_write_request
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_targeted_submit_choice_dirty_copy_names_write_path
  tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py::test_untargeted_multi_pane_choice_rows_are_unchanged
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_current_pane_submit_ignores_todo_in_unsent_pane
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_selected_pane_todo_confirmation_preserves_then_commits[chooser]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_selected_pane_todo_confirmation_preserves_then_commits[direct]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_single_prompt_todo_confirmation_launches_unchanged_once
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_single_prompt_todo_confirmation_rejects_without_mutation[None]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_single_prompt_todo_confirmation_rejects_without_mutation[escape]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_single_prompt_todo_confirmation_rejects_without_mutation[n]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_single_prompt_todo_confirmation_rejects_without_mutation[q]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_confirmation_fails_closed_after_origin_unmount
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_confirmation_fails_closed_after_stack_rebuild
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_free_and_literal_shaped_prompts_submit_immediately[TODOS TODO2 preTODO remain ordinary]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_free_and_literal_shaped_prompts_submit_immediately[`TODO: inline literal`]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_free_and_literal_shaped_prompts_submit_immediately[```\nTODO(owner): fenced literal\n```]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_free_and_literal_shaped_prompts_submit_immediately[lowercase todo remains ordinary]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_todo_free_and_literal_shaped_prompts_submit_immediately[plain prompt with no draft marker]
  tests/ace/tui/widgets/test_prompt_stack_submit_todo.py::test_whole_stack_todo_confirmation_counts_submitted_markers
  tests/ace/tui/widgets/test_prompt_star_search.py::test_counted_star_honors_count
  tests/ace/tui/widgets/test_prompt_star_search.py::test_d_star_moves_without_deleting
  tests/ace/tui/widgets/test_prompt_star_search.py::test_f_star_and_dt_star_treat_asterisk_as_literal_target
  tests/ace/tui/widgets/test_prompt_star_search.py::test_g_star_matches_substring
  tests/ace/tui/widgets/test_prompt_star_search.py::test_hash_searches_backward_for_whole_word
  tests/ace/tui/widgets/test_prompt_star_search.py::test_insert_mode_star_inserts_literal_character
  tests/ace/tui/widgets/test_prompt_star_search.py::test_n_after_star_keeps_whole_word_and_case_sensitive_semantics
  tests/ace/tui/widgets/test_prompt_star_search.py::test_single_occurrence_wraps_with_vim_style_feedback
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_crosses_prompt_panes_and_focuses_destination
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_from_whitespace_scans_forward_on_line
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_jumps_to_next_occurrence_and_records_register
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_matches_whole_word_only
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_mid_word_and_on_first_char_reach_same_destination
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_on_lowercase_word_skips_uppercase_match
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_on_uppercase_word_skips_lowercase_match
  tests/ace/tui/widgets/test_prompt_star_search.py::test_star_with_no_keyword_after_cursor_notifies_without_touching_state
  tests/ace/tui/widgets/test_prompt_star_search.py::test_visual_star_on_empty_selection_notifies_without_register
  tests/ace/tui/widgets/test_prompt_star_search.py::test_visual_star_searches_charwise_selection_literally
  tests/ace/tui/widgets/test_prompt_star_search.py::test_visual_star_searches_v_line_selection_literally
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_capture_omits_cursor_when_active_pane_is_empty
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_ctrl_gS_captures_all_non_empty_panes_from_insert
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_ctrl_g_upper_x_captures_frontmatter_only_draft
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_ctrl_gs_stashes_all_non_empty_panes_from_insert
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_ctrl_s_captures_multiline_cursor_on_active_pane
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_ctrl_s_stashes_single_pane_from_insert
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gS_captures_all_non_empty_panes_without_clearing_bar
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gS_empty_prompt_posts_empty_update_request
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gS_preserves_shared_frontmatter
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_g_upper_x_captures_all_non_empty_panes_without_clearing_bar
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_g_upper_x_multi_pane_captures_active_pane_as_snippet_body
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_g_upper_x_multi_pane_is_not_marked_single_pane
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_g_upper_x_multi_pane_with_one_empty_pane_is_not_single_pane
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_g_upper_x_single_pane_marks_event_single_pane
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gs_all_empty_is_noop
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gs_marks_non_final_active_pane
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gs_preserves_shared_frontmatter
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_gs_stashes_all_non_empty_panes_in_order
  tests/ace/tui/widgets/test_prompt_stash_capture.py::test_single_pane_comma_still_reverses_char_search
  tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py::test_ctrl_gp_posts_restore_request_from_insert
  tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py::test_empty_ctrl_s_posts_restore_request
  tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py::test_non_empty_ctrl_s_stashes_without_restore_request
  tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py::test_whitespace_ctrl_s_posts_restore_request
  tests/ace/tui/widgets/test_prompt_todo_title.py::test_todo_title_aggregates_reorders_and_removes_panes
  tests/ace/tui/widgets/test_prompt_todo_title.py::test_todo_title_capsule_keeps_running_gold_after_theme_switch
  tests/ace/tui/widgets/test_prompt_todo_title.py::test_todo_title_keeps_binding_mode_agent_and_jinja_adornments
  tests/ace/tui/widgets/test_prompt_todo_title.py::test_todo_title_tracks_initial_offscreen_text_and_live_edits
  tests/ace/tui/widgets/test_prompt_todo_title.py::test_todo_title_updates_for_append_and_fresh_stash_restore_paths
  tests/ace/tui/widgets/test_prompt_virtual_wrap.py::test_alt_b_moves_to_previous_word_in_insert_mode
  tests/ace/tui/widgets/test_prompt_virtual_wrap.py::test_alt_f_moves_to_next_word_boundary_in_insert_mode
  tests/ace/tui/widgets/test_prompt_virtual_wrap.py::test_esc_prefixed_word_keys_move_by_word_in_insert_mode[\x1bb-16-11]
  tests/ace/tui/widgets/test_prompt_virtual_wrap.py::test_esc_prefixed_word_keys_move_by_word_in_insert_mode[\x1bf-0-5]
  tests/ace/tui/widgets/test_prompt_virtual_wrap.py::test_typing_past_narrow_width_does_not_insert_newlines
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_accepts_hyphenated_prompt_word_and_preserves_suffix
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_immediately_accepts_one_prompt_word_match
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_mid_word_accept_preserves_right_hand_suffix_as_word
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_mid_word_matches_goal_example
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_narrowing_preserves_suffix_without_space_until_commit
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_opens_multiple_prompt_words_and_renders_plain_rows
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_ctrl_t_scans_all_prompt_lines
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_lowered_minimum_restores_short_prompt_word_completion
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_candidates_refresh_and_preserve_selection
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_cursor_movement_dismisses_without_prefix
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_menu_ctrl_l_accept_preserves_suffix
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_menu_enter_accept_preserves_suffix
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_navigation_and_enter_acceptance
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_prompt_word_refresh_never_reintroduces_short_candidates
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_stale_short_candidate_cannot_be_accepted
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_structured_token_keeps_precedence_over_prompt_words
  tests/ace/tui/widgets/test_prompt_word_completion.py::test_whitespace_keeps_recent_file_history_precedence
  tests/ace/tui/widgets/test_recursive_finder_modal.py::TestCtrlRPromptWiring::test_ctrl_r_escape_leaves_prompt_unchanged
  tests/ace/tui/widgets/test_recursive_finder_modal.py::TestCtrlRPromptWiring::test_ctrl_r_opens_finder_and_inserts_at_cursor
  tests/ace/tui/widgets/test_recursive_finder_modal.py::TestCtrlRPromptWiring::test_ctrl_r_preseeds_partial_filename
  tests/ace/tui/widgets/test_recursive_finder_modal.py::TestCtrlRPromptWiring::test_ctrl_r_while_ctrl_t_open_uses_selected_dir_as_root
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[#git:foo +-#gh:sase ]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[#git:foo Fix bug +-#gh:sase Fix bug]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[%model:opus Body +-%model:opus #gh:sase Body]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[+-#gh:sase ]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[+sa-#gh:sase ]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[---\nname: x\n---\nBody +----\nname: x\n---\n#gh:sase Body]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[Describe this repo. +-#gh:sase Describe this repo.]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_applies_canonical_expansion[Line one\n +-#gh:sase Line one\n]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_placeholder_is_noop
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_accept_places_cursor_after_inserted_tag
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_bare_plus_at_bof_auto_opens_menu
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_bare_plus_query_filters_and_accepts
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_bof_plus_accept_expands_to_tag
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_ctrl_n_p_cycle_highlight
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_ctrl_t_on_bof_plus_token_opens_menu
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_ctrl_t_on_existing_plus_token_opens_menu
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_empty_catalog_shows_placeholder_row
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_escape_dismisses_menu
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_glued_plus_after_text_does_not_open
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_hash_plus_does_not_open[Fix ]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_hash_plus_does_not_open[]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_hash_plus_does_not_open[c]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_menu_renders_patch_project_display_name
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_menu_renders_project_and_patch_badges
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_non_matching_query_dismisses
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_plus_without_literal_space_does_not_open[\t]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_plus_without_literal_space_does_not_open[line\n]
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_space_after_token_dismisses
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_space_delimited_plus_auto_opens_menu
  tests/ace/tui/widgets/test_vcs_project_completion.py::test_typing_filters_candidates
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_accept_namespace_chains_to_repo_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_accept_patch_applies_terminal_colon_transform
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_accept_project_applies_token_local_colon_transform
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_accept_project_applies_token_local_paren_transform
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_auto_open_empty_source_stays_silent
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_colon_auto_opens_ref_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_ctrl_t_empty_source_shows_placeholder
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_negative_ref_start_dismisses_ref_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_non_vcs_colon_keeps_xprompt_argument_behavior
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_owner_slash_routes_to_repo_menu_not_ref_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_paren_auto_pair_opens_ref_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_typed_slash_hands_off_from_ref_menu_to_repo_menu
  tests/ace/tui/widgets/test_vcs_ref_completion.py::test_typing_filters_ref_menu
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_accept_repo_candidate_applies_canonical_colon_transform
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_accept_repo_candidate_applies_canonical_paren_transform
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_backspace_past_slash_dismisses_cached_repo_menu
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_cache_miss_shows_loading_then_worker_result
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_ctrl_t_opens_existing_repo_ref
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_slash_auto_opens_cached_repo_menu
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_typing_narrows_cached_repo_menu
  tests/ace/tui/widgets/test_vcs_repo_completion.py::test_worker_result_dropped_when_menu_closed_before_fetch_finishes
  tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_ctrl_space_action_is_gated_only_while_prompt_is_mounted
  tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_colon_after_wait_auto_opens_wait_targets_panel
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_prose_comma_after_wait_directive_does_not_reopen_panel
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_real_comma_after_wait_agent_reopens_panel
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_wait_arg_completion_excludes_selected_agent_and_groups
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_wait_arg_completion_excludes_selected_keyword_in_paren_form
  tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_wait_paren_empty_clause_offers_documented_bead_keyword
  tests/ace/tui/widgets/test_xprompt_arg_hints.py::test_accepting_required_xprompt_shows_arg_hint_panel
  tests/ace/tui/widgets/test_xprompt_arg_hints.py::test_submit_cancel_and_escape_clear_arg_hint_state
  tests/ace/tui/widgets/test_xprompt_arg_value_completion.py::test_bool_named_arg_offers_true_false_values
  tests/ace/tui/widgets/test_xprompt_arg_value_completion.py::test_fork_agent_arg_auto_menu_respects_disabled_xprompt_gate
  tests/ace/tui/widgets/test_xprompt_arg_value_completion.py::test_fork_agent_arg_auto_menu_uses_xprompt_gate
  tests/ace/tui/widgets/test_xprompt_arg_value_completion.py::test_named_arg_completion_does_not_interfere_with_snippet_tab
  tests/ace/tui/widgets/test_xprompt_arg_value_completion.py::test_parenthesized_arg_name_completion_skips_existing_names
  tests/ace/tui/widgets/test_xprompt_completion.py::test_panel_acceptance_uses_xprompt_completion_skeleton
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_absent_spacer_invalidates_later_comma_rewrite
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_changed_reference_invalidates_later_comma_rewrite
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_completion_before_punctuation_records_no_spacer
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_completion_panel_accept_then_comma
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_cursor_movement_invalidates_later_comma_rewrite
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_cursor_movement_invalidates_the_tab_spacer_deletion
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_intervening_keystroke_clears_pending_spacer
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_no_input_ctrl_t_single_candidate_then_comma
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_no_input_soft_completion_then_comma
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_no_input_xprompt_colon_is_not_rewritten
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_optional_agent_spacer_colon_opens_agent_menu
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_optional_agent_spacer_colon_respects_disabled_auto_menu
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_optional_only_ctrl_t_single_candidate_then_colon
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_optional_only_ctrl_t_single_candidate_then_comma
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_required_text_completion_does_not_record_pending_spacer
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_shift_tab_after_spacer_retreats_without_the_space
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_spacer_tab_deletion_is_one_shot
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_tab_after_spacer_jumps_to_next_tabstop_without_the_space
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_tab_at_the_last_tabstop_keeps_the_spacer
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_tab_does_not_expand_a_snippet_named_after_the_xprompt
  tests/ace/tui/widgets/test_xprompt_completion_spacer.py::test_tab_without_a_snippet_session_keeps_the_spacer
  tests/agents_sync/test_commit_publication_bounded_drain.py::test_after_a_blocked_render_a_later_drain_retries_and_succeeds
  tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued
  tests/artifact_refs/test_context.py::test_context_assembles_dynamic_document_role_and_namespaces
  tests/axe/test_agent_meta_atomic.py::test_generic_and_specialized_agent_meta_writers_use_atomic_publication
  tests/completion/test_build.py::test_mutex_groups_found
  tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot
  tests/core/test_agent_artifact_run_retention.py::test_apply_removes_selected_runs_empty_shards_and_deindexes
  tests/core/test_agent_artifact_run_retention.py::test_plan_degrades_to_continuation_unavailable_on_retention_value_error
  tests/core/test_agent_artifact_run_retention.py::test_plan_protects_recent_referenced_open_bead_and_incomplete_runs
  tests/core/test_agent_artifact_run_retention.py::test_plan_reports_empty_out_of_range_shards
  tests/core/test_continuation_retention.py::test_apply_skips_dir_when_continuation_ancestry_appears
  tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe
  tests/core/test_continuation_retention.py::test_plan_protects_pending_delivery_ancestry
  tests/core/test_continuation_retention.py::test_plan_protects_unreadable_continuation_metadata
  tests/core/test_continuation_retention.py::test_plan_reclaims_old_ancestry_after_safe_terminal_disposition
  tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway
  tests/fakey/test_monitor_capacity_e2e.py::test_epic_launch_shaped_zero_weight_monitor_frees_full_capacity_for_its_workers
  tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
  tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_monitor_crash_reclaims_claim_without_disturbing_unrelated_owner
  tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_monitor_timeout_reclaims_claim_without_disturbing_unrelated_owner
  tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace
  tests/fakey/test_pipe_e2e.py::test_fresh_named_model_pipe_skips_fork_and_records_model
  tests/fakey/test_pipe_e2e.py::test_monitor_sleep_one_next_still_attaches_and_transfers_claim
  tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
  tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_off_leaves_agents_alone
  tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
  tests/fakey/test_retry_pipeline_e2e.py::test_execution_override_runs_fakey_with_requested_model_metadata
  tests/fakey/test_retry_pipeline_e2e.py::test_fallback_switches_the_real_subprocess_model
  tests/fakey/test_retry_pipeline_e2e.py::test_kill_during_retry_wait_stops_before_another_subprocess
  tests/fakey/test_retry_pipeline_e2e.py::test_retries_exhausted_raises_after_snapshotting_terminal_attempt
  tests/fakey/test_retry_pipeline_e2e.py::test_retryable_failure_then_success_records_lifecycle_and_nudge
  tests/fakey/test_retry_pipeline_e2e.py::test_spawn_new_agent_writes_handoff_and_terminal_parent_artifacts
  tests/fakey/test_runner_slots_e2e.py::test_child_is_exempt_while_repeat_roots_stay_capped
  tests/fakey/test_runner_slots_e2e.py::test_fakey_agents_respect_cap_and_release_in_fifo_order
  tests/fakey/test_runner_slots_e2e.py::test_fakey_monitor_holds_capacity_across_handoff_and_followup
  tests/fakey/test_runner_slots_e2e.py::test_fakey_priority_admission_differs_from_park_order
  tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit
  tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error
  tests/llm_provider/test_codex_usage_probe.py::test_registered_hook_runs_through_isolated_probe
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes
  tests/llm_provider/test_temporary_override_phase2.py::test_invoke_agent_applies_active_override
  tests/llm_provider/test_temporary_override_phase2.py::test_invoke_agent_applies_nondefault_alias_override_effort
  tests/llm_provider/test_temporary_override_phase2.py::test_invoke_agent_expired_override_ignored
  tests/llm_provider/test_temporary_override_phase2.py::test_invoke_agent_explicit_provider_name_beats_override
  tests/llm_provider/test_temporary_override_phase2.py::test_invoke_agent_prompt_directive_beats_override
  tests/llm_provider/test_usage_config.py::test_usage_indicator_bundled_fable_default_does_not_synthesize_missing_window
  tests/llm_provider/test_usage_config.py::test_usage_indicator_defaults_and_overrides
  tests/llm_provider/test_usage_config.py::test_usage_indicator_real_bundled_default_and_user_override_projection[empty-provider-map-keeps-bundled-exact-window]
  tests/llm_provider/test_usage_config.py::test_usage_indicator_real_bundled_default_and_user_override_projection[exact-key-never-wins]
  tests/llm_provider/test_usage_config.py::test_usage_indicator_real_bundled_default_and_user_override_projection[exact-key-threshold-restores-generic-boundary]
  tests/llm_provider/test_usage_config.py::test_usage_indicator_real_bundled_default_and_user_override_projection[unrelated-provider-override-keeps-claude-defaults]
  tests/llm_provider/test_usage_probe.py::test_descendant_processes_are_reaped
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait
  tests/main/test_artifact_cli_link.py::test_relation_list_covers_every_builtin_slug
  tests/main/test_artifact_cli_link_health.py::test_derived_row_rendered_in_links_table_is_not_stale
  tests/main/test_artifact_cli_link_health.py::test_fix_does_not_rewrite_when_marker_text_is_unmanaged_prose
  tests/main/test_artifact_cli_link_health.py::test_inspect_fix_does_not_reintroduce_renamed_rows_from_sibling_clone
  tests/main/test_artifact_cli_link_health.py::test_inspect_fix_repairs_historical_research_rename
  tests/main/test_artifact_cli_link_health.py::test_inspect_reports_row_level_aggregate_drift
  tests/main/test_artifact_cli_link_health.py::test_inspect_treats_existing_bead_refs_as_live
  tests/main/test_artifact_cli_link_health.py::test_missing_derived_row_projection_is_reported_stale
  tests/main/test_artifact_cli_link_health.py::test_unpublished_agent_refs_are_informational
  tests/main/test_artifact_cli_list_doctor.py::test_doctor_fix_then_verify_reports_changed_ids_and_health
  tests/main/test_artifact_cli_list_doctor.py::test_doctor_health_ignores_missing_source_paths
  tests/main/test_artifact_cli_prune_runs.py::test_prune_runs_apply_refuses_when_protections_are_unavailable
  tests/main/test_artifact_cli_prune_runs.py::test_prune_runs_defaults_to_dry_run
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases
  tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_avoids_heavy_imports
  tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_child_cpu_budget[directive]
  tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_wall_clock_budget[monitor]
  tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output
  tests/main/test_init_memory_task_types_snapshot.py::test_memory_plan_generates_artifact_relation_registry_in_artifacts_note_and_snapshot
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_questions-expected_phrases11]
  tests/main/test_lsp_handler.py::test_sase_lsp_execs_env_override_in_subprocess
  tests/main/test_lsp_handler.py::test_sase_lsp_subprocess_preserves_version_and_server_args
  tests/main/test_monitor_handler_start_implicit.py::test_start_implicit_family_container_derives_cwd_from_the_live_member
  tests/main/test_monitor_handler_start_implicit.py::test_start_implicit_family_member_uses_caller_workspace_without_agent_flag
  tests/main/test_monitor_handler_start_implicit.py::test_start_implicit_numeric_phase_uses_caller_workspace_without_agent_flag
  tests/main/test_monitor_handler_start_launch.py::test_start_json_envelope_is_stable
  tests/main/test_monitor_handler_start_launch.py::test_start_json_envelope_reports_handed_off_before_the_kill
  tests/main/test_monitor_handler_start_launch.py::test_start_json_includes_explicit_followup_model
  tests/main/test_monitor_handler_start_launch.py::test_start_lane_flag_is_a_deprecated_alias_for_agent
  tests/main/test_monitor_handler_start_launch.py::test_start_launches_a_real_monitor_and_reports_the_resolved_timeout
  tests/main/test_monitor_handler_start_launch.py::test_start_prints_the_summary_before_the_agent_runner_handoff_kill
  tests/main/test_monitor_handler_start_launch.py::test_start_truncates_an_overlength_status_label
  tests/main/test_parser_command_help.py::test_agents_help_renders_sorted_subcommands
  tests/main/test_parser_command_help.py::test_axe_ensure_help_documents_healing_and_watchdog
  tests/main/test_parser_machine.py::test_machine_help_renders_sorted_subcommands_and_defaults_to_list
  tests/main/test_proc_handler_run.py::test_run_attributes_the_proc_to_the_resolved_session
  tests/main/test_proc_handler_run.py::test_run_derives_a_label_from_the_command
  tests/main/test_proc_handler_run.py::test_run_json_emits_the_created_proc
  tests/main/test_proc_handler_run.py::test_run_named_proc_shell_derives_and_does_not_conflate_keys
  tests/main/test_proc_handler_run.py::test_run_prints_the_id_and_the_follow_hint
  tests/main/test_proc_handler_run.py::test_run_quiet_prints_only_the_proc_id
  tests/main/test_proc_handler_run.py::test_run_session_none_leaves_the_proc_unattributed
  tests/main/test_proc_handler_run.py::test_run_truncates_a_very_long_derived_label
  tests/main/test_proc_handler_run.py::test_run_wait_json_keeps_stdout_parseable
  tests/main/test_proc_handler_run.py::test_run_wait_json_quiet_still_emits_only_the_envelope
  tests/main/test_proc_handler_run.py::test_run_wait_reports_a_signalled_command_like_a_shell
  tests/main/test_proc_handler_run.py::test_run_wait_streams_output_and_propagates_the_exit_code[raise SystemExit(0)-0]
  tests/main/test_proc_handler_run.py::test_run_wait_streams_output_and_propagates_the_exit_code[raise SystemExit(3)-3]
  tests/main/test_proc_handler_show.py::test_show_follow_json_waits_for_the_finished_proc
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift
  tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs
  tests/main/test_workspace_handler_cleanup_repair.py::TestCompact::test_compact_apply_installs_alternate_and_reclaims_objects
  tests/main/test_workspace_handler_cleanup_repair.py::TestCompact::test_compact_can_target_one_registered_checkout
  tests/main/test_workspace_handler_cleanup_repair.py::TestCompact::test_compact_dry_run_reports_without_touching_alternate
  tests/main/test_workspace_handler_cleanup_repair.py::TestRepair::test_repair_dissociates_when_sharing_disabled
  tests/main/test_workspace_handler_cleanup_repair.py::TestRepair::test_repair_refuses_broken_non_sase_alternate
  tests/main/test_workspace_handler_cleanup_repair.py::TestRepair::test_repair_repoints_broken_sase_alternate
  tests/memory/test_memory_selector_render.py::test_note_section_retains_children_listing_beneath_its_header
  tests/monitor/test_continuation_delivery.py::test_concurrent_dispatch_spawns_once
  tests/monitor/test_continuation_delivery.py::test_followup_reserves_identity_before_spawn
  tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[after_reserve-reserved]
  tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[after_spawn-dispatching]
  tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[before_reserve-None]
  tests/monitor/test_continuation_delivery.py::test_injected_crashes_keep_delivery_key_stable[before_spawn-dispatching]
  tests/monitor/test_continuation_delivery.py::test_resume_adoption_decision_preserves_acknowledged_records
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_attaches_to_the_lane_and_transfers_the_claim
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_omits_auto_prefix_without_auto_state
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_omits_the_fork_prefix_when_the_starter_never_settles
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_reauthors_auto_prefix
  tests/monitor/test_monitor_followup.py::test_launch_followup_agent_uses_explicit_next_model
  tests/monitor/test_monitor_followup_rollout.py::test_disabled_start_stays_legacy_after_rollout_enabled
  tests/monitor/test_monitor_followup_rollout.py::test_enabled_start_keeps_versioned_records_after_rollout_disabled
  tests/monitor/test_monitor_followup_rollout.py::test_launch_followup_agent_renders_from_frozen_result_and_intent
  tests/monitor/test_monitor_followup_rollout.py::test_launch_followup_agent_uses_legacy_launcher_when_records_disabled
  tests/monitor/test_monitor_followup_workspace.py::test_launch_followup_agent_falls_back_to_fresh_claim_after_transfer_failure
  tests/monitor/test_monitor_followup_workspace.py::test_launch_followup_agent_falls_back_to_primary_when_meta_pairing_is_unresolvable
  tests/monitor/test_monitor_followup_workspace.py::test_launch_followup_agent_falls_back_to_workspace_zero_when_workspace_taken
  tests/monitor/test_monitor_followup_workspace.py::test_launch_followup_agent_repairs_a_meta_workspace_num_mismatch
  tests/monitor/test_monitor_followup_workspace.py::test_launch_followup_agent_repairs_a_nested_managed_dir_to_its_owning_workspace
  tests/monitor/test_monitor_owner_cleanup.py::test_owner_cleanup_stops_monitor_child_and_suppresses_followup
  tests/monitor/test_monitor_proc_facade.py::test_background_grandchild_and_resistant_group_are_stopped
  tests/monitor/test_monitor_proc_facade.py::test_claim_is_released_when_there_is_no_followup
  tests/monitor/test_monitor_proc_facade.py::test_invalid_utf8_output_is_retained_with_replacement
  tests/monitor/test_monitor_proc_facade.py::test_quiet_command_retains_an_output_log
  tests/monitor/test_monitor_proc_facade.py::test_start_uses_one_proc_id_and_artifacts_cross_links
  tests/monitor/test_monitor_proc_facade.py::test_stop_uses_the_proc_service_and_suppresses_followup
  tests/monitor/test_monitor_proc_settlement.py::test_settle_monitor_artifacts_leaves_stopped_at_unpersisted
  tests/monitor/test_monitor_resume.py::test_checkpoint_resume_creates_numbered_manual_branch_and_supersedes_base
  tests/monitor/test_monitor_resume.py::test_checkpoint_resume_preserves_concurrent_acknowledgment
  tests/monitor/test_monitor_resume.py::test_concurrent_identical_checkpoint_resume_spawns_once
  tests/monitor/test_monitor_resume.py::test_crash_after_fence_keeps_acknowledged_branch_intact
  tests/monitor/test_monitor_resume.py::test_repeat_resume_after_acknowledgment_does_not_spawn
  tests/monitor/test_monitor_resume.py::test_resume_does_not_retry_dispatching_record_without_uninvoked_proof
  tests/monitor/test_monitor_resume.py::test_resume_refuses_stale_receiver_without_live_process
  tests/monitor/test_monitor_resume.py::test_resume_rejects_fire_and_forget_monitor
  tests/monitor/test_monitor_resume.py::test_resume_rejects_stopped_monitor
  tests/monitor/test_monitor_resume.py::test_resume_then_adopt_invokes_provider_once
  tests/monitor/test_monitor_resume.py::test_resume_uses_persisted_record_protocol_when_rollout_disabled
  tests/monitor/test_monitor_resume.py::test_resume_uses_the_frozen_result_delivery_key
  tests/monitor/test_monitor_resume_delivery.py::test_repeat_resume_after_acknowledgment_does_not_spawn
  tests/monitor/test_monitor_resume_delivery.py::test_resume_dispatch_real_preprocess_adopt_budget_and_provider_invoke_combine
  tests/monitor/test_monitor_resume_delivery.py::test_resume_then_adopt_invokes_provider_once
  tests/monitor/test_monitor_resume_manual.py::test_checkpoint_resume_creates_numbered_manual_branch_and_supersedes_base
  tests/monitor/test_monitor_resume_manual.py::test_checkpoint_resume_preserves_concurrent_acknowledgment
  tests/monitor/test_monitor_resume_manual.py::test_concurrent_identical_checkpoint_resume_spawns_once
  tests/monitor/test_monitor_resume_manual.py::test_crash_after_fence_keeps_acknowledged_branch_intact
  tests/monitor/test_monitor_resume_manual.py::test_resume_refuses_stale_receiver_without_live_process
  tests/monitor/test_monitor_resume_manual.py::test_resume_repairs_missing_starter_parent_once_starter_settled
  tests/monitor/test_monitor_resume_manual.py::test_resume_still_requires_checkpoint_while_starter_parent_is_missing
  tests/monitor/test_monitor_start.py::test_monitor_claim_survives_stale_cleanup_allocation_and_followup_transfer
  tests/monitor/test_monitor_start.py::test_start_monitor_epic_launch_from_non_numbered_cwd_uses_workspace_zero
  tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion
  tests/monitor/test_monitor_start.py::test_start_monitor_refuses_a_numbered_cwd_claimed_by_another_live_agent
  tests/monitor/test_monitor_start.py::test_start_monitor_request_clamps_overlength_before_agent_meta
  tests/monitor/test_monitor_start.py::test_start_monitor_without_metadata_workspace_num_claims_the_cwd_checkout
  tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
  tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
  tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
  tests/monitor/test_monitor_start_ack.py::test_supervisor_ack_marker_carries_real_pid_pgid_and_identity
  tests/monitor/test_monitor_start_conflicts.py::test_start_monitor_serializes_concurrent_starts_in_one_lane
  tests/monitor/test_monitor_start_lane_pinning.py::test_explicit_family_target_still_selects_newest_lane_member
  tests/monitor/test_monitor_start_lane_pinning.py::test_implicit_start_from_a_promoted_family_container_pins_the_live_member
  tests/monitor/test_monitor_start_lane_pinning.py::test_implicit_start_pins_family_member_not_newer_settled_monitor
  tests/monitor/test_monitor_start_lane_pinning.py::test_implicit_start_pins_numeric_phase_caller_not_sibling_or_land
  tests/monitor/test_monitor_start_lane_pinning.py::test_implicit_start_pins_the_callers_artifacts_dir_over_a_newer_member
  tests/monitor/test_monitor_start_supervisor.py::test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running
  tests/monitor/test_monitor_start_supervisor.py::test_sighup_to_supervisor_does_not_stop_the_monitor
  tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_captures_supervisor_diagnostics
  tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_persists_a_supervisor_identity
  tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_reparents_the_supervisor_before_return
  tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env
  tests/monitor/test_monitor_start_teardown.py::test_start_monitor_claim_failure_does_not_run_the_command
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_completes_when_grandchild_holds_stdout
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_escalates_term_ignoring_chatty_child
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_idle_timeout_fires_after_output_stalls
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_kills_the_whole_process_group_on_timeout
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_after_child_closes_stdio
  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_after_partial_line
  tests/monitor/test_monitor_supervise_timeout.py::test_supervisor_subprocess_stops_cleanly_on_sigterm
  tests/pager/test_app_actions.py::test_y_then_label_copies_the_links_resolved_path
  tests/pager/test_rail_parity.py::test_pager_and_link_rail_share_ref_presentation[plan:202608/link_traversing_pager.md-expected_target5-source]
  tests/pager/test_rail_parity.py::test_pager_and_link_rail_share_ref_presentation[plan:202608/link_traversing_pager.md-expected_target5-target]
  tests/pager/test_rendered_link_contract.py::test_file_backed_home_path_hint_uses_filesystem_resolution
  tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
  tests/pager/test_syntax_activation.py
  tests/question_shell/test_followup_prompt.py::test_answered_followup_prompt_has_live_fork_and_no_leaked_markers
  tests/sdd/test_artifact_link_publication_retry.py::test_retry_sweep_publishes_previously_unpushed_hidden_sidecar_commit
  tests/sdd/test_artifact_link_reconcile.py::test_commits_changed_paths_from_a_repair
  tests/sdd/test_artifact_link_reconcile.py::test_no_changed_paths_does_not_commit
  tests/sdd/test_artifact_link_reconcile.py::test_reconciles_and_repairs_with_the_doctor_candidate_refs
  tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
  tests/sdd_store/test_sidecar_bead_adoption.py::test_fresh_init_records_and_seeds_root_beads_sidecar
  tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_imports_pushes_cleans_and_reruns_without_new_commits
  tests/sdd_store/test_sidecar_init_creation.py::test_split_init_creates_both_repos_before_writing_record
  tests/shells/test_followup_vcs_preallocation.py::test_monitor_followup_forwards_recorded_vcs_ref
  tests/shells/test_shells_substrate.py::test_shell_done_marker_writers_stamp_finished_at_through_shared_helper
  tests/stats/test_runner_occupancy_parity.py::test_monitor_handoff_gap_stays_occupied
  tests/telemetry/test_catalog.py::test_catalog_all_have_subsystem
  tests/telemetry/test_catalog.py::test_get_subsystems_order_matches_constant
  tests/telemetry/test_metrics.py::test_metric_def_count
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet
  tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
  tests/test_agent_artifact_directory_operation_audit.py::test_reviewed_dir_operation_sites_declare_coverage
  tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
  tests/test_agent_artifact_dismissed_save_audit.py::test_reviewed_dismissed_agent_save_sites_sync_projection
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_includes_anonymous_appears_as_agent_workflow
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_matches_source_scan_for_anonymous_workflows
  tests/test_agent_artifact_index_anonymous_visibility.py::test_tier1_visible_inbox_still_filters_explicit_workflow_state_hidden
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations
  tests/test_agent_chat_from_name.py::test_explicit_running_agent_falls_back_to_meta_chat_path
  tests/test_agent_chat_from_name_proc.py::test_existing_agent_name_wins_over_colliding_proc_name
  tests/test_agent_group_revival_e2e.py::test_lowercase_s_dispatches_by_active_tab
  tests/test_agent_group_revival_e2e.py::test_mark_save_preview_and_revive_saved_agent_group
  tests/test_agent_group_revival_e2e.py::test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader
  tests/test_agent_hold_service.py::test_rebind_agent_hold_round_trips_and_keeps_created_at
  tests/test_agent_kill_dismiss_fast_path.py
  tests/test_agent_kill_phase2_kill_all.py
  tests/test_agent_list_runner_slots.py::test_runner_slot_queue_orders_parked_waiters_after_open_thresholds
  tests/test_agent_load_tiering_harness.py::test_load_tiering_oracle_reports_under_selecting_candidate_filter
  tests/test_agent_load_tiering_production_oracle.py::test_production_machine_query_oracle_repairs_owner_after_index
  tests/test_agent_loader_dedup_pid_families.py::test_pid_dedup_preserves_followup_workflow_agents
  tests/test_agent_loader_epic_created_status.py::test_epic_bead_id_without_epic_approval_does_not_create_epic_status
  tests/test_agent_loader_epic_created_status.py::test_host_epic_metadata_reload_crosses_real_artifact_loader_boundary
  tests/test_agent_loader_epic_created_status.py::test_host_owned_epic_metadata_advances_concrete_planner_family
  tests/test_agent_loader_epic_created_status.py::test_host_owned_epic_metadata_advances_synthetic_planner_family
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard
  tests/test_agent_name_registry_lock.py::test_wipe_does_not_delete_under_the_allocation_lock
  tests/test_agent_name_registry_rebuild.py::test_reservation_reads_skip_the_stale_proof_memo
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix
  tests/test_agent_names_extract_metadata.py::TestExtractDirectivesMetadata::test_batch_predecessor_context_binds_bare_wait
  tests/test_agent_names_extract_metadata.py::TestExtractDirectivesMetadata::test_batch_predecessor_context_binds_local_xprompt_wait
  tests/test_agent_names_extract_metadata.py::TestExtractDirectivesMetadata::test_persists_wait_runners_metadata
  tests/test_agent_names_extract_metadata.py::TestExtractDirectivesMetadata::test_preserved_batch_predecessor_context_rebinds_refreshed_wait
  tests/test_agent_names_extract_templates.py::TestExtractDirectivesTemplates::test_generated_template_name_uses_planned_name_without_explicit_claim
  tests/test_agent_wait_cli.py
  tests/test_agent_wait_cli.py::test_all_excludes_caller_and_its_family
  tests/test_agent_wait_cli.py::test_exit_code_timeout
  tests/test_agent_wait_live.py
  tests/test_agent_wait_live.py::test_live_rows_preserve_shared_capacity_order
  tests/test_agent_wait_live.py::test_terminal_blocker_warning_when_dependency_failed
  tests/test_agent_wait_live.py::test_why_column_for_waiting_queued_monitor_and_prompt
  tests/test_agent_wait_watch.py
  tests/test_agents_tab_query_filter.py::test_agent_search_query_refilters_and_schedules_async_agents_refresh
  tests/test_alias_history_modal.py::test_modal_navigation_skips_group_headers_and_spacers
  tests/test_alias_history_modal.py::test_modal_single_alias_renders_runs_without_group_header
  tests/test_approve_options_modal_state.py::test_c_key_is_disabled_for_tale_actions
  tests/test_approve_options_modal_state.py::test_c_key_sets_capacity_on_epic
  tests/test_approve_options_modal_state.py::test_capacity_editor_cancel_keeps_previous_value
  tests/test_approve_options_modal_state.py::test_capacity_zero_displays_drain_and_is_submitted_for_epic
  tests/test_approve_options_modal_state.py::test_p_key_preserves_capacity_in_edit_prompt
  tests/test_approve_options_modal_state.py::test_switching_to_tale_does_not_submit_stale_capacity
  tests/test_artifact_create_bead_attachment.py::test_a_bare_flag_attaches_to_the_agents_own_bead
  tests/test_artifact_create_bead_attachment.py::test_an_explicit_bead_id_receives_the_minted_reference
  tests/test_axe_chop_agents.py::test_spawn_agent_subprocess_records_chop_launch_and_detaches
  tests/test_axe_chop_output_contract_digest_and_reap.py::test_managed_tmp_reap_emits_action_summary
  tests/test_axe_chop_output_contract_digest_and_reap.py::test_managed_tmp_reap_emits_noop_summary
  tests/test_axe_chop_wait_runners.py::test_prepare_and_preview_inject_queue
  tests/test_axe_chop_wait_runners.py::test_queue_priority_only_keeps_lumberjack_threshold
  tests/test_axe_chop_wait_runners.py::test_queue_runner_threshold_overrides_lumberjack_default
  tests/test_axe_chop_wait_runners.py::test_wait_dependency_and_runner_threshold_merge
  tests/test_axe_default_chop_triggers.py::test_artifact_glob_chops_skip_idle_and_fire_on_new_agent_artifact[bead_claim_checks]
  tests/test_axe_default_chop_triggers.py::test_artifact_glob_chops_skip_idle_and_fire_on_new_agent_artifact[wait_checks]
  tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  tests/test_axe_run_agent_phases_tribes.py::test_planned_template_name_does_not_inherit_nested_existing_tribe
  tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  tests/test_bead/test_claimed_status.py::test_show_explains_claim_owner
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_full]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_implicit_closed_json]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_json_limit]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_json]
  tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[show_phase_json]
  tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable
  tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_orphaned_clan_bundle_is_released_and_launch_proceeds
  tests/test_bead/test_cli_work_cleanup_confirm.py::test_orphaned_family_bundle_is_released_and_launch_proceeds
  tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout
  tests/test_bead/test_cli_work_epic_dry_run.py::test_work_dry_run_renders_zero_capacity_on_selected_segments
  tests/test_bead/test_cli_work_epic_launch.py::test_work_launch_threads_capacity_into_rendered_multi_prompt
  tests/test_bead/test_cli_work_epic_summary.py::TestEpicSummarySmokeExercises::test_epic_work_clan_panel_renders_persisted_summary
  tests/test_bead/test_cli_work_epic_summary.py::TestEpicSummarySmokeExercises::test_epic_work_launch_uses_snapshot_without_refreshing_stale_clone
  tests/test_bead/test_cli_work_epic_validation.py::test_capacity_error_after_prior_multi_target_success_keeps_json_lines
  tests/test_bead/test_cli_work_epic_validation.py::test_work_rejects_capacity_on_standalone_task_json
  tests/test_bead/test_cli_work_multi_target.py::test_bead_work_parser_assigns_capacity_and_cl_name_short_aliases
  tests/test_bead/test_cli_work_multi_target.py::test_multi_target_dispatch_reuses_options_and_one_lock
  tests/test_bead/test_epic_launch.py::test_build_epic_launch_argv_preserves_explicit_zero_capacity
  tests/test_bead/test_epic_launch_finish.py::test_work_command_failure_notification_preserves_capacity_resume_hint
  tests/test_bead/test_epic_launch_monitor.py::test_start_epic_launch_monitor_forwards_capacity_and_records_resume_argv
  tests/test_bead/test_work_rendering.py::TestCapacityDirective::test_capacity_composes_with_weight_only_land_queue
  tests/test_capacity_gate_to_admission.py::test_epic_gate_capacity_reaches_weighted_admission
  tests/test_clan_summary_persistence.py::test_plan_race_refresh_replaces_identity_fallback_with_complete_plan
  tests/test_clan_summary_script_execution.py::test_generic_plan_summary_entry_point_uses_epic_environment_fallback
  tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_exits_on_sigterm_without_sigkill
  tests/test_command_availability_scope.py::test_grouping_cycle_palette_commands_follow_grouping_capability
  tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning
  tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom
  tests/test_core_agent_scan_options.py::test_capacity_only_skips_done_dirs_and_keeps_active_ones
  tests/test_core_agent_scan_options.py::test_options_round_trip_through_snapshot
  tests/test_direct_typed_launch.py::test_invalid_typed_syntax_fails_before_agent_launch
  tests/test_direct_typed_launch.py::test_isolated_direct_bash_proc_settles_without_agent
  tests/test_directive_edit.py::test_set_prompt_queue_preserves_existing_wait
  tests/test_directive_edit.py::test_set_prompt_queue_preserves_existing_weight
  tests/test_directive_edit.py::test_set_prompt_wait_and_queue_splits_fields
  tests/test_directives_split_models.py::test_split_prompt_for_models_xprompt_model_axis_composes_with_alts
  tests/test_directives_wait.py::test_queue_directive_sets_runner_slot_fields
  tests/test_directives_wait.py::test_wait_bead_keywords_mix_and_deduplicate_in_source_order
  tests/test_dismissed_agent_lifecycle.py
  tests/test_embedded_env_injection.py::TestExpandEmbeddedInjectsEnv::test_embedded_workflow_colon_arg_decodes_plus_space_substitution
  tests/test_embedded_env_injection.py::TestExpandEmbeddedInjectsEnv::test_embedded_workflow_injects_environment
  tests/test_embedded_env_injection.py::TestExpandEmbeddedInjectsEnv::test_environment_template_rendering
  tests/test_embedded_env_injection.py::TestExpandEmbeddedInjectsEnv::test_multiple_env_vars_injected
  tests/test_finalizers_live_e2e.py::test_live_clean_completion_has_no_recovery_or_commit
  tests/test_fleet_contract_counts_sase_core_rs.py::test_count_contract_deduplicates_current_instances_and_buckets
  tests/test_fleet_contract_sase_core_rs.py::test_locator_projection_and_validation_round_trip_without_local_data
  tests/test_gate_cli_show.py::test_show_reports_an_accepted_failed_gate
  tests/test_gate_decision_acceptance.py::test_cancel_is_permitted_after_current_failure
  tests/test_gate_decision_acceptance.py::test_conflicting_selection_supersedes_after_current_failure
  tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads
  tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections
  tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_j_keeps_local_newline_priority
  tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_k_keeps_local_history_priority
  tests/test_keymaps_e2e.py::test_prompt_input_space_is_text_after_home_prompt_opens
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_dismissal_is_idempotent[home]
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_dismissal_is_idempotent[nonhome]
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_falls_back_to_unknown_cl_name_for_home_without_meta
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_index_write_failure_does_not_flip_success
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_notification_failure_does_not_flip_success
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_permission_denied_keeps_question_active
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_writes_dismissal_for_home_uses_meta_cl_name
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_writes_dismissal_for_nonhome_uses_claim_cl_name
  tests/test_kill_named_agent_dismiss.py::test_kill_named_agent_writes_dismissal_when_process_already_stopped
  tests/test_kill_named_agent_dismiss.py::test_kill_named_root_dismisses_child_question_only
  tests/test_kill_named_agent_dismiss_waiting.py::test_kill_named_agent_cleans_up_and_dismisses_when_pid_missing
  tests/test_kill_named_agent_dismiss_waiting.py::test_kill_named_agent_dead_meta_pid_cleans_up_stale_waiting_agent
  tests/test_kill_named_agent_dismiss_waiting.py::test_kill_named_agent_meta_pid_recycling_guard_does_not_signal
  tests/test_kill_named_agent_dismiss_waiting.py::test_kill_named_agent_uses_live_meta_pid_for_waiting_home_agent
  tests/test_kill_named_agent_dismiss_waiting.py::test_kill_named_agent_uses_live_meta_pid_for_waiting_nonhome_agent
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected
  tests/test_launch_condition_workspace_admission_flow.py::test_stale_source_checkout_skips_after_prepared_lease_sees_upstream
  tests/test_launch_proc_runtime.py::test_admission_launches_proc_and_mixed_wait_order
  tests/test_launch_proc_runtime.py::test_bash_proc_runs_without_agent_artifacts
  tests/test_launch_proc_runtime.py::test_delayed_proc_after_wait_preserves_the_same_executable_environment
  tests/test_launch_proc_runtime.py::test_duplicate_fingerprint_does_not_spawn_a_second_child
  tests/test_launch_proc_runtime.py::test_proc_metadata_preserves_label_provenance_through_prepare
  tests/test_launch_proc_runtime.py::test_python_proc_uses_sase_interpreter
  tests/test_launch_proc_runtime.py::test_standalone_proc_resolves_user_installed_command_and_preserves_host_env
  tests/test_launch_proc_runtime.py::test_timeout_settles_without_agent_slots
  tests/test_llm_provider_invoke.py::test_invoke_agent_execution_provider_override_preserves_requested_metadata
  tests/test_llm_provider_invoke.py::test_invoke_agent_no_directive_routes_through_configured_default_model
  tests/test_llm_provider_invoke.py::test_invoke_agent_resolves_model_alias_for_provider_and_model
  tests/test_llm_provider_invoke.py::test_invoke_agent_unknown_execution_provider_is_actionable
  tests/test_llm_provider_invoke.py::test_invoke_agent_warns_when_model_override_falls_back_to_default_provider
  tests/test_llm_provider_invoke_overrides.py::test_execution_override_resolves_display_model_with_requested_provider
  tests/test_managed_tmp_reaper.py::test_a_concurrent_command_s_fresh_scratch_survives
  tests/test_managed_tmp_reaper.py::test_a_missing_root_is_not_an_error
  tests/test_managed_tmp_reaper.py::test_broad_cleanup_roots_are_rejected[unsafe_root0]
  tests/test_managed_tmp_reaper.py::test_broad_cleanup_roots_are_rejected[unsafe_root1]
  tests/test_managed_tmp_reaper.py::test_broad_cleanup_roots_are_rejected[unsafe_root2]
  tests/test_managed_tmp_reaper.py::test_broad_cleanup_roots_are_rejected[unsafe_root3]
  tests/test_managed_tmp_reaper.py::test_broad_cleanup_roots_are_rejected[unsafe_root4]
  tests/test_managed_tmp_reaper.py::test_every_literal_managed_tmpdir_bucket_has_a_horizon
  tests/test_managed_tmp_reaper.py::test_horizons_are_chosen_per_subdirectory
  tests/test_managed_tmp_reaper.py::test_managed_subdirectories_themselves_always_survive
  tests/test_managed_tmp_reaper.py::test_muse_prompts_bucket_uses_the_handoff_horizon
  tests/test_managed_tmp_reaper.py::test_removals_are_capped_per_invocation
  tests/test_managed_tmp_reaper.py::test_symlinks_are_neither_followed_nor_removed
  tests/test_managed_tmp_reaper.py::test_the_default_root_follows_the_managed_tmpdir_resolution
  tests/test_managed_tmp_reaper.py::test_unknown_top_level_entries_use_the_default_horizon
  tests/test_managed_tmp_reaper_artifact_index.py::test_a_file_only_pass_never_touches_the_artifact_index
  tests/test_managed_tmp_reaper_artifact_index.py::test_reaped_directories_drop_their_artifact_index_rows
  tests/test_managed_tmp_reaper_artifact_index.py::test_workflow_artifact_directories_are_pruned_whole
  tests/test_managed_tmp_reaper_config.py::test_managed_tmp_config_overrides_low_free_space_pressure_age
  tests/test_managed_tmp_reaper_config.py::test_managed_tmp_config_overrides_pressure_thresholds
  tests/test_managed_tmp_reaper_config.py::test_managed_tmp_config_overrides_the_command_scratch_horizon
  tests/test_managed_tmp_reaper_pressure.py::test_low_free_space_pressure_age_still_protects_fresh_descendant
  tests/test_managed_tmp_reaper_pressure.py::test_ordinary_cargo_build_dir_names_are_eligible_and_protect_fresh_descendants
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_catches_large_top_level_target_residue
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_catches_legacy_build_targets_bucket
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_keeps_recent_targets_when_free_space_is_ample
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_preserves_build_tree_with_fresh_descendant
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_preserves_unknown_bucket_with_fresh_child
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_prunes_large_build_scratch_before_horizon
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_skips_generic_agent_tmp_and_handoff
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_stops_at_free_space_recovery_threshold
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_uses_low_free_space_age_when_size_also_triggers
  tests/test_managed_tmp_reaper_pressure.py::test_pressure_reaping_uses_low_free_space_below_root_ceiling
  tests/test_managed_tmp_reaper_reporting.py::test_describe_flags_a_capped_pass
  tests/test_managed_tmp_reaper_reporting.py::test_describe_names_the_busiest_buckets
  tests/test_managed_tmp_reaper_reporting.py::test_describe_reports_an_idle_pass
  tests/test_managed_tmp_reaper_reporting.py::test_dry_run_reports_selected_entries_without_removing_them
  tests/test_models_panel_edit.py::test_action_edit_picker_uses_flat_alias_snapshot
  tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo
  tests/test_models_panel_navigation.py::test_panel_navigation_skips_headers_and_empty_hint_with_wrap
  tests/test_models_panel_override_flows.py::test_action_override_opens_alias_enabled_picker
  tests/test_models_panel_runner_limit.py::test_title_footer_and_chooser_show_effective_and_configured_limits
  tests/test_multi_prompt_launcher_xprompt_groups.py::test_launch_agents_from_cwd_passes_single_segment_swarm_provenance
  tests/test_ops_settlement.py::test_command_failure_writes_error_envelope_without_log_inference
  tests/test_ops_settlement.py::test_legacy_submission_without_operation_stays_compatible
  tests/test_ops_settlement.py::test_operation_request_is_written_before_launch_and_result_round_trips
  tests/test_ops_settlement.py::test_overlapping_concurrency_keys_conflict
  tests/test_ops_settlement.py::test_result_before_terminal_crash_after_publication
  tests/test_ops_settlement.py::test_successful_command_without_result_settles_as_durable_error
  tests/test_plan_approval_actions_epic.py::test_prepare_epic_launch_keeps_capacity_in_monitor_failure_resume_hint
  tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[host_first-0]
  tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[host_first-1]
  tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[host_first-2]
  tests/test_plan_approval_launch_reliability_integration.py::test_combined_tale_approval_to_coder_link_lifecycle[host_first]
  tests/test_plan_filter_query_canonical.py::test_canonical_query_round_trip_property
  tests/test_plan_gate_capacity.py::test_epic_adapter_forwards_capacity_onto_the_launch_argv
  tests/test_plan_gate_capacity.py::test_epic_gate_command_path_hands_capacity_to_prepare_epic_launch
  tests/test_plan_gate_capacity.py::test_epic_gate_selection_translates_capacity_into_runner_protocol
  tests/test_plan_gate_capacity.py::test_execute_plan_gate_command_accepts_explicit_zero_capacity
  tests/test_plan_gate_capacity.py::test_gate_answer_set_coerces_capacity_integer
  tests/test_plan_gate_capacity.py::test_legacy_approval_emits_capacity_field
  tests/test_plan_gate_capacity.py::test_neutral_approval_puts_capacity_in_shared_input
  tests/test_plan_gate_capacity.py::test_skip_mode_does_not_launch_even_with_capacity
  tests/test_proc_env_isolation.py::test_sase_ml_file_families_ignore_inherited_live_proc_env
  tests/test_proc_observer_isolation.py::test_constructed_ace_app_does_not_poison_a_later_test
  tests/test_procs_runner.py::test_ace_origin_proc_is_owned_by_its_supervisor_pid
  tests/test_procs_runner.py::test_kill_proc_terminates_a_detached_proc
  tests/test_procs_runner.py::test_kill_proc_terminates_the_supervised_process_group
  tests/test_procs_runner.py::test_killed_supervisor_is_reconciled_to_terminal_error
  tests/test_procs_runner.py::test_legacy_detached_submit_creates_unattributed_command_row
  tests/test_procs_runner.py::test_submit_supervisor_captures_output_and_proc_environment
  tests/test_procs_runner.py::test_supervisor_records_nonzero_and_unspawnable_commands
  tests/test_procs_service.py::test_barrier_timeout_does_not_run_the_command
  tests/test_procs_service.py::test_named_proc_shell_reuse_is_project_scoped_and_waits_for_settlement
  tests/test_procs_service.py::test_result_and_artifact_settlement_are_durable
  tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
  tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash
  tests/test_procs_service.py::test_stop_records_intent_then_settles_killed
  tests/test_procs_service.py::test_submit_derives_bare_named_proc_shell
  tests/test_procs_service.py::test_submit_records_a_proc_shell_and_settles_success
  tests/test_procs_service.py::test_submit_request_normalizes_legacy_kind_to_command
  tests/test_procs_service.py::test_submit_request_replay_returns_the_active_row
  tests/test_procs_service.py::test_total_and_idle_timeouts_settle_as_errors
  tests/test_procs_service.py::test_wait_for_proc_recovers_after_an_early_settlement_reconcile
  tests/test_procs_supervisor.py::test_invalid_utf8_and_quiet_commands_settle
  tests/test_procs_supervisor.py::test_process_group_kill_reaps_grandchildren_and_resistant_children
  tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  tests/test_procs_supervisor.py::test_supervisor_is_reparented_away_from_the_starter
  tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention
  tests/test_queue_directive.py::test_queue_adapter_collects_and_formats_through_rust
  tests/test_queue_directive.py::test_typed_launch_parses_queue_and_rebuilds_canonical_prompt
  tests/test_queue_directive.py::test_typed_launch_rejects_retired_wait_queue_keywords
  tests/test_queue_directive.py::test_validate_queue_capacity_rejects_booleans_and_invalid_numbers
  tests/test_run_agent_runner_slot_capacity.py::test_releasing_monitor_admits_the_parked_waiter
  tests/test_run_agent_runner_slot_capacity.py::test_running_monitor_occupying_last_slot_parks_new_launch
  tests/test_run_agent_runner_wait_queue.py::test_force_reuse_bead_marker_retains_wait_claim_without_release_marker
  tests/test_run_agent_runner_wait_queue.py::test_queued_child_proceeds_after_identity_wait_barrier
  tests/test_run_agent_runner_wait_queue.py::test_runner_forwards_blocking_wait_result_to_code_refresh
  tests/test_run_agent_runner_wait_queue.py::test_waiting_bead_claims_before_wait_and_promotes_before_execution
  tests/test_runner_slots_queue.py::test_live_waiter_queue_excludes_terminal_records_and_includes_reacquiring_child
  tests/test_running_agents_snapshot.py::test_list_all_agents_includes_done_and_failed
  tests/test_running_agents_snapshot.py::test_list_running_agents_filters_done_and_dead
  tests/test_running_agents_snapshot.py::test_list_running_agents_reports_waiting_marker
  tests/test_running_agents_snapshot.py::test_list_running_agents_surfaces_slot_relevant_parallel_children
  tests/test_running_agents_snapshot.py::test_running_listing_slot_occupancy_matches_admission_count
  tests/test_runtime_workspace_managed_roots.py::TestManagedRootMaterialization::test_adjacent_does_not_create_registry
  tests/test_runtime_workspace_managed_roots.py::TestManagedRootMaterialization::test_xdg_state_materializes_under_managed_root
  tests/test_runtime_workspace_managed_roots.py::TestRestartSafeResolution::test_marker_records_project_context_for_managed_checkout
  tests/test_runtime_workspace_managed_roots.py::TestRestartSafeResolution::test_same_inputs_resolve_same_checkout_across_processes
  tests/test_scratch_tmpdir_leak_regression.py::test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read
  tests/test_suite_gate_scoped_integration.py::test_scoped_run_takes_no_token_while_the_pool_is_exhausted
  tests/test_temporary_llm_override_agent_meta.py::test_agent_meta_after_clear_uses_configured_default_provider
  tests/test_temporary_llm_override_agent_meta.py::test_agent_meta_frozen_after_later_override_change
  tests/test_temporary_llm_override_agent_meta.py::test_agent_meta_until_cleared_override_records_provider
  tests/test_temporary_llm_override_agent_meta.py::test_launch_alias_overrides_persist_to_meta_and_process_env
  tests/test_vcs_log_filter_query.py::test_canonical_query_round_trip_property
  tests/test_workflow_executor.py::TestShouldHitl::test_inherited_model_override_beats_step_model_directive
  tests/test_workflow_executor.py::TestShouldHitl::test_inherited_vcs_tag_does_not_override_explicit_step_ref
  tests/test_workflow_executor.py::TestShouldHitl::test_inherited_vcs_tag_prefixes_bare_prompt_step
  tests/test_workflow_executor.py::TestShouldHitl::test_inherited_vcs_tag_preserves_directives_and_segments
  tests/test_workflow_executor.py::TestShouldHitl::test_prompt_step_chat_history_includes_step_metadata
  tests/test_workflow_executor_inherit_agent_meta.py::test_resolve_prompt_step_prefers_agent_meta_over_default_model
  tests/test_workflow_executor_inherit_agent_meta.py::test_stale_unredeemed_reservation_is_not_inherited_from_agent_meta
  tests/test_wraps_all.py::test_single_vcs_outside_with_vcs_mentions_inside_disabled_region
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%auto:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%clan(research, su]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%clan(research, tr]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%effort:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, be]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, cl]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, fa]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, tr]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model(me]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model(opus, medium=]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%repeat:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(bead=]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%xprompts_enabled:]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_queue_directive
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_typed_launch_directives_when_enabled
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_queue_argument_rows_match[%q(-expected_insertions1]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_queue_argument_rows_match[%q:-expected_insertions2]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_queue_argument_rows_match[%queue(-expected_insertions0]
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_wait_prose_replacement_ranges_match
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows
  tests/test_xprompt_directive_completion_parity.py::test_lsp_uses_utf16_replacement_ranges
  tests/test_xprompt_directive_completion_parity.py::test_wait_colon_form_never_advertises_structured_keywords
  tests/test_xprompt_directive_completion_parity.py::test_wait_keywords_exclude_queue_fields
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_finalizer_add_rows_match
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_finalizer_parenthesized_clause_replacement
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_finalizer_remove_omits_required
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_finalizer_repeated_directive_matches
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_finalizer_utf16_replacement_next_to_non_ascii
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_none_available_when_clear_is_legal
  tests/test_xprompt_finalizer_completion_parity.py::test_ace_and_lsp_none_suppressed_when_required_exists
  tests/test_xprompt_finalizer_completion_parity.py::test_finalizer_helper_failure_degrades_without_invented_rows
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[**-cursor0-opus]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[**claude/fa-cursor10-claude/claude-fable-5]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Explain **laX later-cursor6-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Title\r\nUse **la\ttail-cursor8-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Use **la   now-cursor3-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Use **la now-cursor2-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Use **la-cursor1-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Use **la\nnow-cursor5-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[Use **la\tnow-cursor4-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[\U0001f642 **la\r\nnext-cursor9-large-model]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_edits_match[first\nnext **op-cursor7-opus]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_filter_text_preselect_and_expansion
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[  **fable-cursor5-expected5]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[**-cursor0-expected0]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[**FA-cursor2-expected2]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[**claude/fa-cursor6-expected6]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[**codex/la-cursor7-expected7]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[**la-cursor1-expected1]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[Use **la-cursor3-expected3]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_double_star_model_names_and_order_match[first\nnext **op-cursor4-expected4]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[*-cursor0-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Explain *laX later-cursor6-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Title\r\nUse *la\ttail-cursor8-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Use *la   now-cursor3-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Use *la now-cursor2-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Use *la-cursor1-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Use *la\nnow-cursor5-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[Use *la\tnow-cursor4-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[\U0001f642 *la\r\nnext-cursor9-@large]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_edits_match[first\nnext *SM-cursor7-@small]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_filter_text_preselect_and_expansion
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[  *scout-cursor5-expected5]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[*-cursor0-expected0]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[*LA-cursor2-expected2]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[*la-cursor1-expected1]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[Use *la-cursor3-expected3]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ace_and_lsp_star_alias_names_and_order_match[first\nnext *SM-cursor4-expected4]
  tests/test_xprompt_model_alias_shortcut_parity.py::test_double_star_model_no_match_is_empty_incomplete_list
  tests/test_xprompt_model_alias_shortcut_parity.py::test_lsp_advertises_star_trigger_character
  tests/test_xprompt_model_alias_shortcut_parity.py::test_missing_and_malformed_catalogs_stay_empty_shortcut
  tests/test_xprompt_model_alias_shortcut_parity.py::test_ordinary_model_completion_still_includes_models_and_providers
  tests/test_xprompt_model_alias_shortcut_parity.py::test_star_alias_no_match_is_empty_incomplete_list
  tests/test_xprompt_model_completion_aliases.py::test_model_completion_catalog_uses_effective_merged_aliases_for_shortcut
  tests/test_xprompt_model_completion_catalog.py::test_model_completion_catalog_filters_hidden_provider_by_metadata_flag
  tests/test_xprompt_model_completion_catalog.py::test_model_completion_catalog_includes_agy_gemini_37_flash_variants
  tests/test_xprompt_model_completion_catalog.py::test_model_completion_catalog_includes_agy_gemini_38_flash_variants
  tests/test_xprompt_model_completion_filtering.py::test_filter_model_alias_shortcut_entries_is_alias_only_and_case_insensitive
  tests/test_xprompt_model_completion_filtering.py::test_model_completion_filter_matches_values_without_unconfigured_default_alias
  tests/test_xprompt_model_completion_filtering.py::test_model_completion_provider_scope_is_case_insensitive
  tests/test_xprompt_model_completion_filtering.py::test_model_completion_provider_scope_uses_first_slash_only
  tests/test_xprompt_model_completion_filtering.py::test_model_completion_provider_scoped_filter_derives_qualified_rows
  tests/workspace_provider/test_git_object_sharing.py::test_dissociate_repoints_then_preserves_foreign_alternates
  tests/workspace_provider/test_git_object_sharing.py::test_failed_repoint_rolls_back_alternate_and_config
  tests/workspace_provider/test_git_object_sharing.py::test_primary_among_foreign_alternates_is_not_claimed
  tests/workspace_provider/test_git_object_sharing.py::test_relative_alternate_is_resolved_from_object_database
  tests/workspace_provider/test_git_object_sharing.py::test_repoint_preserves_foreign_alternates
  tests/workspace_provider/test_git_object_sharing.py::test_reuses_broken_sase_borrower_by_dissociating_when_sharing_disabled
  tests/workspace_provider/test_git_object_sharing.py::test_reuses_broken_sase_borrower_without_deleting_local_work
  tests/workspace_provider/test_git_object_sharing.py::test_shared_clone_installs_sase_alternate_and_survives_repack
  tests/workspace_provider/test_utils_workspace_checkout.py::TestEnsureWorkspaceCheckout::test_adjacent_compat_matches_ensure_git_clone
  tests/workspace_provider/test_utils_workspace_checkout.py::TestEnsureWorkspaceCheckout::test_materialized_checkout_syncs_workspace_sdd_clone
  tests/workspace_provider/test_utils_workspace_checkout.py::TestEnsureWorkspaceCheckout::test_omitted_config_uses_xdg_state_default
  tests/workspace_provider/test_utils_workspace_checkout.py::TestEnsureWorkspaceCheckout::test_xdg_state_materializes_under_managed_root
flake baseline gate: 19 reproducible flake(s) exceed tests/reproducible_flake_baseline.txt (records after 2026-08-15T17:22:27Z, at most 5 failures per run):
  tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_fleet_refresh_apply_defers_behind_active_navigation
  tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows
  tests/ace/tui/test_feature_flags_pane.py::test_confirmed_toggle_restarts_axe_and_suppresses_duplicates
  tests/ace/tui/test_visual_fixture_host_paths.py::test_visual_fixtures_embed_no_host_home_paths
  tests/completion/test_build.py::test_mutex_groups_found
  tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
  tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_questions-expected_phrases11]
  tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
  tests/shells/test_shells_substrate.py::test_shell_done_marker_writers_stamp_finished_at_through_shared_helper
  tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
  tests/test_agent_artifact_dismissed_save_audit.py::test_reviewed_dismissed_agent_save_sites_sync_projection
  tests/test_agent_hold_service.py::test_rebind_agent_hold_round_trips_and_keeps_created_at
  tests/test_artifact_capture_policy.py::test_capture_config_default_and_schema
  tests/test_bead/test_claimed_status.py::test_show_explains_claim_owner
  tests/test_command_availability_scope.py::test_grouping_cycle_palette_commands_follow_grouping_capability
  tests/test_justfile_lint.py::test_rust_dev_install_disables_cargo_incremental_cache
  tests/test_managed_tmp_reaper.py::test_every_literal_managed_tmpdir_bucket_has_a_horizon
  tests/test_suite_gate_lease.py::test_default_automatic_range_keeps_room_for_a_peer_full_run
  tests/test_suite_gate_scoped_integration.py::test_scoped_run_takes_no_token_while_the_pool_is_exhausted
Additions require a filed bead; fix or file the node before landing.
flake baseline gate: 17 recorded node ID(s) no longer collectable (renamed or deleted test); excluded as stale rather than gated as a live flake:
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_active_section_reconciles_across_same_document_rerender
  tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_cheap_paint_preserves_section_until_enriched_layout_returns
  tests/core/test_agent_artifact_run_retention.py::test_apply_still_raises_when_continuation_closure_fails
  tests/core/test_continuation_retention.py::test_apply_skips_dir_when_continuation_ancestry_appears
  tests/main/test_artifact_cli_link_health.py::test_inspect_fix_repairs_historical_research_rename
  tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_wall_clock_budget[monitor]
  tests/monitor/test_monitor_resume.py::test_checkpoint_resume_preserves_concurrent_acknowledgment
  tests/test_agent_load_tiering_harness.py::test_load_tiering_oracle_reports_under_selecting_candidate_filter
  tests/test_agent_wait_cli.py
  tests/test_agent_wait_live.py
  tests/test_agent_wait_watch.py
  tests/test_gate_cli_show.py::test_show_reports_an_accepted_failed_gate
  tests/test_gate_decision_acceptance.py::test_cancel_is_permitted_after_current_failure
  tests/test_gate_decision_acceptance.py::test_conflicting_selection_supersedes_after_current_failure
  tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive_when_enabled
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows_when_enabled
flake baseline gate: 141 failure(s) excluded from flake evidence as attributable dirty-tree source-audit breakage (recorded tree_dirty=True and a changed file inside the failing audit's own scanned source root):
  tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix (20260827T020035Z-72abf3729015-1336267-full-run.json)
  tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix (20260827T031429Z-48e019af82f2-2555764-full-run.json)
  tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix (20260827T032503Z-48e019af82f2-2699835-full-run.json)
  tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix (20260828T132946Z-de491c710dda-1022801-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T162039Z-c9cb183c4605-1836123-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T162501Z-b2b8415b7bd3-1921037-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T164054Z-b419802f30c3-2241819-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T164221Z-b419802f30c3-2278345-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T164530Z-18dcf6b8d5bd-2339669-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T164913Z-b419802f30c3-2424285-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T165218Z-97f57750f6f1-2484290-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T181312Z-a67ba351f026-4148192-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T181817Z-91c432385a6a-57147-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T182205Z-a67ba351f026-125365-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T185052Z-ba03cec630e3-757077-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T194241Z-c8a0e7184a4e-1748225-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260820T113805Z-6d87cf2270b8-3683849-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260820T131241Z-585e34b33d9c-946128-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260820T134512Z-82e68005f079-1448979-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260820T140132Z-82e68005f079-1696022-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260823T132245Z-e2056bddebf0-2110248-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260823T133057Z-dcbf570d53a3-2335880-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T182506Z-cbea4f23b255-3353943-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T182958Z-f72ff9f38564-3476681-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T183737Z-cbea4f23b255-3736780-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T185523Z-d88994bd816d-4175594-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T190646Z-d88994bd816d-171012-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T142323Z-70a9d101583f-4032719-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T151728Z-9fb3a1805e3c-799874-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T190751Z-47be6ebf5272-874870-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T202053Z-4fcd56796af0-2265531-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T203932Z-4fcd56796af0-2647910-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T205627Z-1282c7a8c7ff-2995508-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T212600Z-1282c7a8c7ff-3816381-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T221039Z-79e51b564ec9-573378-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T223856Z-f56cf433328e-1181307-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260827T001442Z-2e5cd29e680a-3709969-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260827T035036Z-d4c3bb4083fe-3056956-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260828T142355Z-1858f75606b8-2119501-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260830T114858Z-f0a8fcefa356-1277413-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260830T173504Z-4509c9d675ea-1414068-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260908T113723Z-2ba228da326e-3094066-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260908T120259Z-b0f6f4f112b8-3511967-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260908T122120Z-63f385c9a626-3930670-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260908T130041Z-0b292e49ffe5-501822-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260908T132430Z-0b292e49ffe5-1032197-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260909T230101Z-bc4566dfbf2d-3906220-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260912T084840Z-56ceab3f9995-1719213-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260912T173143Z-ecea389efd48-2718808-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260912T201003Z-e1a2f7839502-2332211-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260912T204145Z-3114dbd03c33-3208076-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260914T161525Z-9ff2662c0cb7-3274129-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260914T185259Z-dd672fd6cbd3-2641591-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260914T202344Z-bfd22d8df3f1-320362-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260914T202510Z-bfd22d8df3f1-362848-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260915T181603Z-53035c96715c-1639539-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260916T041506Z-9f01691ce063-651721-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260916T155726Z-a36ff57c9d46-3264117-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260916T161217Z-a36ff57c9d46-3601818-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260916T175123Z-7636fe03b8c3-1957671-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260918T042111Z-cc6d51d2db99-3253699-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260918T043228Z-cc6d51d2db99-3572322-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T162039Z-c9cb183c4605-1836123-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T162501Z-b2b8415b7bd3-1921037-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T164054Z-b419802f30c3-2241819-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T164221Z-b419802f30c3-2278345-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T164530Z-18dcf6b8d5bd-2339669-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T164913Z-b419802f30c3-2424285-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T165218Z-97f57750f6f1-2484290-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T181312Z-a67ba351f026-4148192-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T181817Z-91c432385a6a-57147-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T182205Z-a67ba351f026-125365-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T185052Z-ba03cec630e3-757077-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T194241Z-c8a0e7184a4e-1748225-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260820T113805Z-6d87cf2270b8-3683849-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260820T131241Z-585e34b33d9c-946128-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260820T134512Z-82e68005f079-1448979-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260820T140132Z-82e68005f079-1696022-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260823T132245Z-e2056bddebf0-2110248-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260823T133057Z-dcbf570d53a3-2335880-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T182506Z-cbea4f23b255-3353943-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T182958Z-f72ff9f38564-3476681-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T183737Z-cbea4f23b255-3736780-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T185523Z-d88994bd816d-4175594-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T190646Z-d88994bd816d-171012-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T142323Z-70a9d101583f-4032719-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T151728Z-9fb3a1805e3c-799874-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T190751Z-47be6ebf5272-874870-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T202053Z-4fcd56796af0-2265531-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T203932Z-4fcd56796af0-2647910-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T205627Z-1282c7a8c7ff-2995508-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T212600Z-1282c7a8c7ff-3816381-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T221039Z-79e51b564ec9-573378-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T223856Z-f56cf433328e-1181307-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260827T001442Z-2e5cd29e680a-3709969-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260827T035036Z-d4c3bb4083fe-3056956-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260828T142355Z-1858f75606b8-2119501-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260830T114858Z-f0a8fcefa356-1277413-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260830T173504Z-4509c9d675ea-1414068-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260908T113723Z-2ba228da326e-3094066-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260908T120259Z-b0f6f4f112b8-3511967-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260908T122120Z-63f385c9a626-3930670-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260908T130041Z-0b292e49ffe5-501822-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260908T132430Z-0b292e49ffe5-1032197-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260909T230101Z-bc4566dfbf2d-3906220-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260912T084840Z-56ceab3f9995-1719213-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260912T173143Z-ecea389efd48-2718808-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260912T201003Z-e1a2f7839502-2332211-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260912T204145Z-3114dbd03c33-3208076-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260914T161525Z-9ff2662c0cb7-3274129-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260914T185259Z-dd672fd6cbd3-2641591-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260914T202344Z-bfd22d8df3f1-320362-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260914T202510Z-bfd22d8df3f1-362848-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260915T181603Z-53035c96715c-1639539-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260916T041506Z-9f01691ce063-651721-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260916T155726Z-a36ff57c9d46-3264117-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260916T161217Z-a36ff57c9d46-3601818-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260916T175123Z-7636fe03b8c3-1957671-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260918T042111Z-cc6d51d2db99-3253699-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260918T043228Z-cc6d51d2db99-3572322-full-run.json)
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_declare_lifecycle_coverage (20260906T210207Z-8efecdd7390a-2387153-full-run.json)
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations (20260906T210207Z-8efecdd7390a-2387153-full-run.json)
  tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations (20260911T002817Z-eb48ee95a723-3996743-full-run.json)
  tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed (20260827T035036Z-d4c3bb4083fe-3056956-full-run.json)
  tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed (20260906T210207Z-8efecdd7390a-2387153-full-run.json)
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed (20260825T152725Z-9fb3a1805e3c-1053386-full-run.json)
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed (20260916T155726Z-a36ff57c9d46-3264117-full-run.json)
  tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed (20260916T161217Z-a36ff57c9d46-3601818-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260906T021143Z-43164eace6ba-966994-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260914T114623Z-f56dae6dd18e-1784395-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260914T121920Z-23d7f54726f1-2432189-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260914T130018Z-8bd8fb891dd9-3402946-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260917T131337Z-96288aea4cfe-206397-full-run.json)
  tests/test_agent_tribe_terminology.py::test_current_source_avoids_agent_tag_identifiers (20260917T134735Z-96288aea4cfe-1104120-full-run.json)
  tests/test_timezone_display_guard.py::test_no_system_clock_display_sites (20260827T225649Z-f07abbec800e-256047-full-run.json)
  tests/test_timezone_display_guard.py::test_no_system_clock_display_sites (20260908T144721Z-a0ac015e0bda-2823416-full-run.json)
  tests/test_timezone_display_guard.py::test_no_system_clock_display_sites (20260908T150204Z-a0ac015e0bda-3149846-full-run.json)
  tests/test_timezone_display_guard.py::test_no_system_clock_display_sites (20260908T155615Z-8c4f8fd22ae9-4191825-full-run.json)
  tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist (20260820T195055Z-0ec8609ce69b-3054018-full-run.json)
  tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist (20260820T201656Z-0ec8609ce69b-3649937-full-run.json)
  tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist (20260827T225649Z-f07abbec800e-256047-full-run.json)
flake baseline gate: 194 failure(s) retired by a # fixed-at: entry in tests/reproducible_flake_baseline.txt:
  tests/ace/tui/modals/test_snippet_name_modal.py::test_elsewhere_collision_loads_other_template_but_keeps_destination (20260820T152549Z-45711984b473-2765047-full-run.json)
  tests/ace/tui/modals/test_snippet_name_modal.py::test_elsewhere_collision_loads_other_template_but_keeps_destination (20260820T185648Z-b7bdd3185a07-1785563-full-run.json)
  tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion (20260820T185648Z-b7bdd3185a07-1785563-full-run.json)
  tests/ace/tui/modals/test_snippet_name_modal.py::test_new_trigger_returns_empty_starting_body (20260819T215133Z-f1914962c8f7-4152541-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T150803Z-9fb3a1805e3c-568708-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T151728Z-9fb3a1805e3c-799874-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T152011Z-1a96ea92bf4d-866680-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T152725Z-9fb3a1805e3c-1053386-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T154203Z-9fb3a1805e3c-1381316-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260825T154446Z-9fb3a1805e3c-1440583-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260826T122413Z-c8a3c606871e-2190940-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260826T123455Z-c8a3c606871e-2431077-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260826T125003Z-c8a3c606871e-2755940-full-run.json)
  tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes (20260826T130447Z-a5989a873802-2964573-full-run.json)
  tests/ace/tui/test_commits_pane_interactions.py::test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles (20260820T003654Z-1d5616e98674-2851542-full-run.json)
  tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section (20260906T205004Z-a45669b26fd3-2039637-full-run.json)
  tests/ace/tui/test_config_center_resume.py::test_new_process_loads_remembered_admin_center_section (20260907T135748Z-e2ce985dd5b0-3949628-full-run.json)
  tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_stays_open_when_submit_collides (20260819T135538Z-6f72aa5eb0f7-3294864-full-run.json)
  tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_stays_open_when_submit_collides (20260819T184609Z-be6077c7fff3-630606-full-run.json)
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_id_parenthesized_completion_advertises_identity_keywords (20260820T204009Z-f136f4fbdcb8-135801-full-run.json)
  tests/ace/tui/widgets/test_directive_completion_candidates.py::test_id_parenthesized_completion_advertises_identity_keywords (20260820T213422Z-1db274e84e36-914613-full-run.json)
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_ctrl_t_at_percent_opens_directive_panel (20260820T213422Z-1db274e84e36-914613-full-run.json)
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_ctrl_t_at_percent_opens_directive_panel (20260821T225253Z-6639a2801616-2270336-full-run.json)
  tests/ace/tui/widgets/test_directive_completion_interactions.py::test_ctrl_t_at_percent_opens_directive_panel (20260822T000232Z-6ee4e1d3d26c-3377548-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T184433Z-ba03cec630e3-596854-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260819T191404Z-13365a95b082-1272458-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T181936Z-54ede7fa5d07-3238037-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260824T190945Z-54ede7fa5d07-244222-full-run.json)
  tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift (20260825T193336Z-51bb2f136663-1498173-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T184433Z-ba03cec630e3-596854-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260819T191404Z-13365a95b082-1272458-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T181936Z-54ede7fa5d07-3238037-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260824T190945Z-54ede7fa5d07-244222-full-run.json)
  tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot (20260825T193336Z-51bb2f136663-1498173-full-run.json)
  tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit (20260911T001550Z-eb48ee95a723-3730224-full-run.json)
  tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit (20260911T002817Z-eb48ee95a723-3996743-full-run.json)
  tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit (20260911T005931Z-2dcd6a136c71-297790-full-run.json)
  tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit (20260913T105734Z-f3a39fa835c9-3100995-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T143444Z-0b292e49ffe5-2530777-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T144721Z-a0ac015e0bda-2823416-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T152124Z-a0ac015e0bda-3601763-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T163003Z-8c4f8fd22ae9-857335-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T163911Z-8c4f8fd22ae9-1077199-full-run.json)
  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes (20260908T182157Z-8c4f8fd22ae9-3095726-full-run.json)
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait (20260823T143717Z-184fa9aed8b7-3677540-full-run.json)
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait (20260823T150423Z-f8ce6bb2253e-104872-full-run.json)
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait (20260823T153738Z-65367452b956-822100-full-run.json)
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait (20260823T154757Z-65367452b956-1037053-full-run.json)
  tests/main/test_agents_dispatch_handler.py::test_dispatch_wait (20260823T160741Z-65367452b956-1275122-full-run.json)
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (20260825T205627Z-1282c7a8c7ff-2995508-full-run.json)
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (20260825T212600Z-1282c7a8c7ff-3816381-full-run.json)
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (20260825T223150Z-f56cf433328e-990343-full-run.json)
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (20260825T223856Z-f56cf433328e-1181307-full-run.json)
  tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (20260827T001442Z-2e5cd29e680a-3709969-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T152107Z-d5b101ab2ead-2177261-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T193917Z-28009002d5da-3376082-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T195456Z-28009002d5da-3750010-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T213606Z-f929b5e2c803-1281806-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T225253Z-6639a2801616-2270336-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T230152Z-6639a2801616-2508340-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T230213Z-6639a2801616-2512951-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T231005Z-6639a2801616-2615898-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T233710Z-47830f9dedcf-3063962-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260821T234550Z-47830f9dedcf-3238246-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T000232Z-6ee4e1d3d26c-3377548-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T105923Z-3ab0c52dea38-39476-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T111112Z-3ab0c52dea38-292777-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T120239Z-8c1acbfa5056-1246775-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T124053Z-ab5099e20399-1944157-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T125529Z-015557337184-2360267-full-run.json)
  tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift (20260822T130053Z-ab5099e20399-2501409-full-run.json)
  tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line (20260819T214317Z-351a3308402a-3987913-full-run.json)
  tests/telemetry/test_metrics.py::test_metric_def_count (20260821T091644Z-7c52152832fb-966052-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T123657Z-8343169a462a-2081188-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T124843Z-8343169a462a-2331127-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T164054Z-b419802f30c3-2241819-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T164221Z-b419802f30c3-2278345-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T164530Z-18dcf6b8d5bd-2339669-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T164913Z-b419802f30c3-2424285-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T181817Z-91c432385a6a-57147-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T190657Z-45bd0f7c707b-1102931-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T195307Z-9f24f133d76c-1950582-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T205530Z-4eb0c20b31c3-3191037-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T221426Z-ba03cec630e3-484007-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260819T233741Z-35ba42ce77d3-1971048-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260820T005027Z-1d5616e98674-3033536-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260820T012512Z-a3f600800b11-3469307-full-run.json)
  tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (20260820T014146Z-a3f600800b11-3771391-full-run.json)
  tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (20260906T021143Z-43164eace6ba-966994-full-run.json)
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard (20260913T193737Z-faad5c3dc3f0-2444884-full-run.json)
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard (20260913T194151Z-d698f92e0598-2545559-full-run.json)
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard (20260913T194200Z-faad5c3dc3f0-2548957-full-run.json)
  tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard (20260913T203039Z-3781cd264c43-3388336-full-run.json)
  tests/test_agent_name_registry_lock.py::test_wipe_does_not_delete_under_the_allocation_lock (20260907T131404Z-f28e64334ade-3440418-full-run.json)
  tests/test_agent_name_registry_lock.py::test_wipe_does_not_delete_under_the_allocation_lock (20260907T135748Z-e2ce985dd5b0-3949628-full-run.json)
  tests/test_agent_name_registry_lock.py::test_wipe_does_not_delete_under_the_allocation_lock (20260907T141127Z-e2ce985dd5b0-19416-full-run.json)
  tests/test_agent_name_registry_lock.py::test_wipe_does_not_delete_under_the_allocation_lock (20260907T143130Z-e2ce985dd5b0-333936-full-run.json)
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (20260825T212128Z-a7478bdaba81-3694201-full-run.json)
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (20260825T214843Z-f56cf433328e-4190058-full-run.json)
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (20260825T221039Z-79e51b564ec9-573378-full-run.json)
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (20260825T223150Z-f56cf433328e-990343-full-run.json)
  tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (20260825T230712Z-012a66a65985-1574570-full-run.json)
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (20260825T212128Z-a7478bdaba81-3694201-full-run.json)
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (20260825T214843Z-f56cf433328e-4190058-full-run.json)
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (20260825T221039Z-79e51b564ec9-573378-full-run.json)
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (20260825T223150Z-f56cf433328e-990343-full-run.json)
  tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (20260825T230712Z-012a66a65985-1574570-full-run.json)
  tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (20260907T065345Z-50b1405f4268-812137-full-run.json)
  tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (20260907T070520Z-50b1405f4268-950690-full-run.json)
  tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (20260907T171405Z-7ca1654a2175-3274864-full-run.json)
  tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (20260908T155615Z-8c4f8fd22ae9-4191825-full-run.json)
  tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (20260908T213233Z-46f7f549ef2e-2629216-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260820T134512Z-82e68005f079-1448979-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T181936Z-54ede7fa5d07-3238037-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T182506Z-cbea4f23b255-3353943-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T182958Z-f72ff9f38564-3476681-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T183737Z-cbea4f23b255-3736780-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T185523Z-d88994bd816d-4175594-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T190646Z-d88994bd816d-171012-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T190945Z-54ede7fa5d07-244222-full-run.json)
  tests/test_config_schema.py::test_default_config_matches_public_schema (20260824T200113Z-04299c29e7d7-1342500-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T193917Z-28009002d5da-3376082-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T195456Z-28009002d5da-3750010-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T213606Z-f929b5e2c803-1281806-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T225253Z-6639a2801616-2270336-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T231005Z-6639a2801616-2615898-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T233710Z-47830f9dedcf-3063962-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260821T234550Z-47830f9dedcf-3238246-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260822T000232Z-6ee4e1d3d26c-3377548-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260822T105923Z-3ab0c52dea38-39476-full-run.json)
  tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom (20260822T111112Z-3ab0c52dea38-292777-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T115822Z-afe374f93d47-371363-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T121738Z-afe374f93d47-695314-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T122025Z-afe374f93d47-773079-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T122721Z-afe374f93d47-932858-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T123133Z-afe374f93d47-1020720-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T125351Z-1dd58f06cd52-1565658-full-run.json)
  tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected (20260823T132245Z-e2056bddebf0-2110248-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_failure_names_workspace (20260819T134622Z-12df170f9f97-3079838-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_failure_names_workspace (20260819T215133Z-f1914962c8f7-4152541-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_prepares_retained_sidecar (20260819T134622Z-12df170f9f97-3079838-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_prepares_retained_sidecar (20260819T215133Z-f1914962c8f7-4152541-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_uses_default_revision_sentinel (20260819T134622Z-12df170f9f97-3079838-full-run.json)
  tests/test_run_agent_runner_setup_linked_repos.py::test_prepare_linked_repo_workspaces_uses_default_revision_sentinel (20260819T215133Z-f1914962c8f7-4152541-full-run.json)
  tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed (20260820T133234Z-4687d37956ac-1198113-full-run.json)
  tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed (20260820T185648Z-b7bdd3185a07-1785563-full-run.json)
  tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed (20260820T192438Z-0ec8609ce69b-2468999-full-run.json)
  tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed (20260820T193957Z-1382a43d8c5f-2803380-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T065345Z-50b1405f4268-812137-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T070520Z-50b1405f4268-950690-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T214036Z-837b1634ae9e-3936261-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T221947Z-e0c5755033ff-454889-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T223453Z-d8a299c2c3e4-719425-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:] (20260907T224312Z-837b1634ae9e-920572-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(] (20260822T211604Z-5c9fb7d07b43-2798417-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(] (20260823T082649Z-a5193276bc71-3356455-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(] (20260823T122025Z-afe374f93d47-773079-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(] (20260823T122721Z-afe374f93d47-932858-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(] (20260823T123133Z-afe374f93d47-1020720-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260821T195456Z-28009002d5da-3750010-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260822T000232Z-6ee4e1d3d26c-3377548-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260822T230654Z-13266fdcaea9-3994261-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260822T232039Z-13266fdcaea9-4179801-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260823T082649Z-a5193276bc71-3356455-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260823T122025Z-afe374f93d47-773079-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260823T122721Z-afe374f93d47-932858-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260823T123133Z-afe374f93d47-1020720-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260907T214036Z-837b1634ae9e-3936261-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260907T221947Z-e0c5755033ff-454889-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260907T223453Z-d8a299c2c3e4-719425-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match (20260907T224312Z-837b1634ae9e-920572-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive (20260907T214036Z-837b1634ae9e-3936261-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive (20260907T221947Z-e0c5755033ff-454889-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive (20260907T223453Z-d8a299c2c3e4-719425-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive (20260907T224312Z-837b1634ae9e-920572-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows (20260907T214036Z-837b1634ae9e-3936261-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows (20260907T221947Z-e0c5755033ff-454889-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows (20260907T223453Z-d8a299c2c3e4-719425-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows (20260907T224312Z-837b1634ae9e-920572-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_typed_launch_directives_when_enabled (20260823T122025Z-afe374f93d47-773079-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_typed_launch_directives_when_enabled (20260823T122721Z-afe374f93d47-932858-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_typed_launch_directives_when_enabled (20260823T123133Z-afe374f93d47-1020720-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260822T202901Z-50534e4f8132-2290552-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260822T211604Z-5c9fb7d07b43-2798417-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260823T082649Z-a5193276bc71-3356455-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260823T122025Z-afe374f93d47-773079-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260823T122721Z-afe374f93d47-932858-full-run.json)
  tests/test_xprompt_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows (20260823T123133Z-afe374f93d47-1020720-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T065345Z-50b1405f4268-812137-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T070520Z-50b1405f4268-950690-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T214036Z-837b1634ae9e-3936261-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T221947Z-e0c5755033ff-454889-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T223453Z-d8a299c2c3e4-719425-full-run.json)
  tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract (20260907T224312Z-837b1634ae9e-920572-full-run.json)
flake baseline gate: the following # fixed-at: entries in tests/reproducible_flake_baseline.txt retired nothing in the current window and can be removed:
  tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces
  tests/ace/tui/modals/test_snippet_name_modal.py::test_derived_only_collision_returns_composed_template
  tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on
  tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error
  tests/main/test_init_memory_glossary.py::test_memory_plan_renders_glossary_terms_block_in_tier2
  tests/test_config_cache.py::test_drain_config_token_refresh_joins_worker_and_advances_epoch
  tests/test_config_cache.py::test_load_merged_config_caches_plugin_layer
  tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config
  tests/test_force_reuse_launch_seam.py::test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse
  tests/test_force_reuse_launch_seam.py::test_sidecar_without_authorization_still_rejects_forced_reuse
error: recipe `selection-health` failed on line 653 with exit code 1
error: recipe `check-full` failed on line 721 with exit code 1

