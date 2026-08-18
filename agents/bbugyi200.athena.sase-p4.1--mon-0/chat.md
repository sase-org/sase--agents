# Chat History - ace-run (sase-p4.1--mon-0)

- **TIMESTAMP:** 2026-08-17 20:47:07 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-p4.1--mon-0

## Prompt

sase monitor start --command 'just check-full' --reason 'just check escalates on the Justfile --epic-symbol change (broadening set: justfile + core-identity-changed); re-run the full verification lane after re-keying stale sase-p1.2 leftovers to sase-p1'

## Response

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
✗ test cost

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-cost                │
└───────────────────────────────────────────────────────┘

---------- Running pytest cost attribution lane... ----------
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 29995s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 532s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 309s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 274s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30025s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 562s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 339s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 304s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30055s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 592s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 369s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 334s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30085s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 622s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 399s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 364s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30115s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 652s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 429s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 394s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30145s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 682s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 459s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 424s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30175s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 712s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 489s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 454s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30205s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 742s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 519s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 484s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30235s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 772s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 549s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 514s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30265s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 802s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 579s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 545s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30295s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 832s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 609s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 575s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30325s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 862s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 639s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 605s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30355s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2457759, grant 8, age 893s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 669s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 635s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30385s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 699s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 665s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30415s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 729s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 695s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 32s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30446s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 759s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 725s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 62s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30476s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 789s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 755s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 92s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30506s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 819s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 785s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 122s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30536s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 849s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 815s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 152s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30566s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 879s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 845s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 182s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30596s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 909s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 875s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 212s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30626s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 939s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 905s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 243s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30656s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 970s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 935s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 273s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30686s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 1000s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 965s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 303s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30716s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2510452, grant 6, age 1030s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 995s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 333s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30746s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1025s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 363s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 28s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30776s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1055s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 393s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 58s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30806s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1085s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 423s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 88s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30836s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1115s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 453s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 118s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30866s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1145s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 483s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 149s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30896s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1175s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 513s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 179s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30926s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1205s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 543s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 209s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30956s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1235s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 573s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 239s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 30986s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1265s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 603s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 269s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31016s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1295s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 633s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 299s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31046s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1325s, argv 'tools/run_pytest scoped'; 8 tokens: pid 2525416, grant 8, age 663s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 329s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 3 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31076s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1356s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 359s, argv 'tools/run_pytest scoped'; 5 tokens: pid 3077755, grant 5, age 13s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 3 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31106s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1386s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 389s, argv 'tools/run_pytest scoped'; 5 tokens: pid 3077755, grant 5, age 43s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 3 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31136s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1416s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 419s, argv 'tools/run_pytest scoped'; 5 tokens: pid 3077755, grant 5, age 73s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 3 tokens were available below the floor. Current holders: 14 tokens: pid 1172645, grant 14, age 31166s, argv 'tools/run_pytest scoped'; 4 tokens: pid 2517309, grant 4, age 1446s, argv 'tools/run_pytest scoped'; 6 tokens: pid 2923142, grant 6, age 449s, argv 'tools/run_pytest scoped'; 5 tokens: pid 3077755, grant 5, age 103s, argv 'tools/run_pytest scoped'
============================= test session starts ==============================
platform linux -- Python 3.14.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, asyncio-1.4.0, hypothesis-6.165.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 5/5 workers
5 workers [32584 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
..............................s......................................... [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
s....................................................................... [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
..................................s..................................... [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
.........s.............................................................. [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
.......................................s................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
.................s......................................s...s........... [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
...........................................s..s..s...s.................. [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................                                 [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=============================== warnings summary ===============================
tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3174571) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=3174571) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_outbox.py::test_two_processes_enqueue_without_lost_or_duplicate_requests
tests/agents_sync/test_publication_outbox.py::test_two_processes_enqueue_without_lost_or_duplicate_requests
tests/logs/test_run_log.py::TestLogAgentRun::test_two_process_appends_are_complete_json_records
tests/logs/test_run_log.py::TestLogAgentRun::test_two_process_appends_are_complete_json_records
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=3174562) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_fails_before_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_fails_before_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py::test_tab_completes_bead_plus_to_plus_one
tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3174562) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:86: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/agents_sync.py:80: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic agents-sync checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:468: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:296: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:296: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 30743 warming mutation(s) filtered; 247 cooling mutation(s) filtered; 1108 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
29.35s call     tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race
24.97s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
22.81s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
20.40s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
18.19s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_no_change_refreshes_without_restart
16.74s call     tests/test_check_feature_flags_tool.py::test_main_static_on_repo_exits_zero
16.33s call     tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_config_center_handoff_confirms_only_captured_live_provider
16.23s call     tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_auto_update_preview_reuses_load_freshness
14.41s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
13.78s call     tests/test_check_feature_flags_tool.py::test_static_main_ignores_exploding_bd_command
13.13s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
10.81s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.42s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
10.12s call     tests/test_patch_stitch_terminology_audit.py::test_real_repositories_keep_required_retained_categories
9.85s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
9.83s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
9.50s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.44s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
8.93s call     tests/test_tmp_env_leak_guard.py::test_guard_wiring_fails_a_leaking_test_but_not_a_monkeypatched_one
8.28s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
========= 32572 passed, 13 skipped, 71 warnings in 2571.59s (0:42:51) ==========
recording: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260818T004547Z-2690267.json
baseline:  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_baseline.json
timings:   /home/bryan/.sase/test-selection/gh_sase-org__sase/timings covers 2894/2896 files total=3799.940s cost-delta=+449.277s (+11.8%)
Test Cost Report
  record: 85923326314d88ea
  recorded_at: 2026-08-18T00:45:47.912354+00:00
  host: athena
  mode: cost
  worker_count: 5

Summary
  per-test wall: 4249.217s
  per-test CPU: 1835.893s
  per-test idle: 2413.323s
  collection: 221.865s
  worker wall: 14950.255s
  worker CPU: 9933.143s
  peak worker RSS KiB: 1,405,040 KiB
  median worker RSS KiB: 599,246 KiB
  post-collection worker RSS KiB: 599,828 KiB
  worker RSS curve: start=152,072 KiB, post_collection=599,828 KiB, median=599,246 KiB, peak=1,405,040 KiB, samples=342
  files: 2896
  nodes: 32584

Diff
  per-test wall: current 4249.217s; baseline 3719.000s; delta +530.217 (+14.3%)
  per-test CPU: current 1835.893s; baseline n/a; delta n/a
  per-test idle: current 2413.323s; baseline n/a; delta n/a
  collection: current 221.865s; baseline 27.600s; delta +194.265 (+703.9%)
  worker wall: current 14950.255s; baseline n/a; delta n/a
  worker CPU: current 9933.143s; baseline n/a; delta n/a
  peak worker RSS KiB: current 1,405,040 KiB; baseline 1,126,400 KiB; delta +278640.000 (+24.7%)
  median worker RSS KiB: current 599,246 KiB; baseline n/a; delta n/a
  post-collection worker RSS KiB: current 599,828 KiB; baseline n/a; delta n/a

Causes
  AcePage.__aenter__: 536.574s (579x)  delta +146.574 (+37.6%)
  Textual App.run_test enter: 454.941s (3070x)  delta +32.941 (+7.8%)
  subprocess.run: 392.939s (35749x)  delta +132.939 (+51.1%)
  ACE settle_pilot: 322.842s (5836x)  delta n/a
  Pilot.pause(delay): 237.840s (11751x)  delta n/a
  Textual App.run_test exit: 67.993s (3070x)  delta n/a
  sase.main.parser.create_parser: 59.248s (1476x)  delta -0.752 (-1.3%)
  AcePage.__aexit__: 51.182s (577x)  delta n/a
  Pilot.pause(None): 31.404s (544x)  delta n/a
  sase.config.core.load_merged_config: 16.082s (11213x)  delta +16.082
  YAML load: 15.422s (31143x)  delta -49.578 (-76.3%)
  subprocess.Popen: 0.282s (346x)  delta n/a
  ACE pause_until_cpu_idle: 0.001s (2x)  delta n/a
  gettext.find: 0.000s (5x)  delta +0.000

Top 10 Files
  by wall:
      59.363s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      54.696s  tests/ace/tui/test_plugins_browser_pane_loading.py
      43.852s  tests/test_ace_testing.py
      42.821s  tests/test_procs_service.py
      38.399s  tests/ace/tui/test_agents_zoom_panel_files.py
      33.753s  tests/monitor/test_monitor_supervise.py
      33.676s  tests/ace/tui/test_axe_entry_editor_modal.py
      32.673s  tests/monitor/test_monitor_start_ack.py
      32.056s  tests/test_bead/test_snooze_gate_actions.py
      31.125s  tests/test_check_feature_flags_tool.py
  by CPU:
      52.868s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      36.903s  tests/ace/tui/test_plugins_browser_pane_loading.py
      32.583s  tests/test_ace_testing.py
      30.792s  tests/ace/tui/test_axe_entry_editor_modal.py
      30.667s  tests/test_check_feature_flags_tool.py
      24.351s  tests/ace/tui/test_plugins_browser_pane_install.py
      23.808s  tests/ace/tui/test_artifacts_scaffold.py
      22.570s  tests/ace/tui/test_statistics_pane_interactions.py
      20.776s  tests/ace/tui/test_xprompt_browser_load_keymap.py
      20.489s  tests/ace/tui/test_plugin_action_confirm_modal.py
  by idle:
      41.931s  tests/test_procs_service.py
      33.131s  tests/monitor/test_monitor_supervise.py
      32.006s  tests/monitor/test_monitor_start_ack.py
      31.319s  tests/test_bead/test_snooze_gate_actions.py
      28.669s  tests/agents_sync/test_cross_machine_e2e.py
      27.595s  tests/ace/tui/test_agents_zoom_panel_files.py
      26.508s  tests/test_bead/test_flag_gate_response.py
      26.498s  tests/test_bead/test_db_migrations.py
      26.239s  tests/test_fork_workflow.py
      22.827s  tests/test_contract_manifest.py
  by AcePage.__aenter__:
      28.770s    35x  tests/test_ace_testing.py
      20.933s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
      16.940s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      13.489s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      12.970s    12x  tests/ace/tui/test_artifacts_scaffold.py
      12.645s    15x  tests/test_keymaps_e2e.py
      12.473s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      12.314s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
      11.505s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
      10.581s    11x  tests/ace/tui/test_statistics_pane_interactions.py
  by Textual App.run_test enter:
      20.723s    38x  tests/test_ace_testing.py
      14.879s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
      11.412s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
       9.728s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       8.600s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       8.187s    15x  tests/test_keymaps_e2e.py
       7.697s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       7.691s    12x  tests/ace/tui/test_artifacts_scaffold.py
       7.610s    11x  tests/ace/tui/test_statistics_pane_interactions.py
       6.720s     9x  tests/ace/tui/test_config_center_alternate_tab.py
  by subprocess.run:
      22.805s     1x  tests/test_contract_manifest.py
      17.697s     7x  tests/monitor/test_monitor_supervise.py
       7.924s    11x  tests/test_bead/test_snooze_gate_actions.py
       7.811s    12x  tests/test_plan_gates_execution.py
       7.762s    37x  tests/main/test_completion_candidates_contract.py
       7.728s    12x  tests/test_plan_auto_approval.py
       7.653s   477x  tests/test_test_selection_backtest.py
       6.536s    10x  tests/test_plan_gates_action_api.py
       6.310s     9x  tests/test_bead/test_flag_gate.py
       5.987s    90x  tests/workflows/test_commit_add.py
  by ACE settle_pilot:
      27.416s    78x  tests/ace/tui/test_plugins_browser_pane_loading.py
      20.301s   194x  tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py
      19.550s    33x  tests/ace/tui/test_plugins_browser_pane_uninstall.py
      15.770s   143x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      10.703s    52x  tests/ace/tui/test_plugins_browser_pane_install.py
       8.881s   402x  tests/ace/tui/test_statistics_pane_interactions.py
       7.603s    54x  tests/ace/tui/test_axe_entry_editor_modal.py
       7.186s    37x  tests/ace/tui/test_config_pane_widget_commit.py
       6.730s    32x  tests/ace/tui/test_config_pane_widget.py
       6.516s    35x  tests/ace/tui/test_config_pane_widget_jump.py
  by Pilot.pause(delay):
      14.745s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      11.117s   156x  tests/ace/tui/test_plugins_browser_pane_loading.py
       8.858s   104x  tests/ace/tui/test_plugins_browser_pane_install.py
       7.341s   804x  tests/ace/tui/test_statistics_pane_interactions.py
       5.916s   108x  tests/ace/tui/test_axe_entry_editor_modal.py
       5.760s    70x  tests/ace/tui/test_config_pane_widget_jump.py
       5.698s    74x  tests/ace/tui/test_config_pane_widget_commit.py
       5.694s    82x  tests/ace/tui/test_statistics_view_number_select.py
       5.352s   128x  tests/ace/tui/test_plugin_action_confirm_modal.py
       5.313s    64x  tests/ace/tui/test_config_pane_widget.py
  by Textual App.run_test exit:
      11.601s    38x  tests/test_ace_testing.py
       2.274s    10x  tests/ace/tui/test_artifacts_patches_navigator.py
       2.168s     5x  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py
       2.147s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
       1.925s    22x  tests/ace/tui/widgets/test_xprompt_completion_spacer.py
       1.727s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       1.636s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.544s    10x  tests/ace/tui/test_plugins_browser_pane_all_current.py
       1.457s    12x  tests/ace/tui/test_artifacts_scaffold.py
       1.438s     9x  tests/ace/tui/test_plugins_browser_pane_jump.py
  by sase.main.parser.create_parser:
       5.713s    26x  tests/main/test_completion_handler.py
       2.118s     8x  tests/main/test_doctor_command.py
       1.798s    29x  tests/test_bead/test_cli_show_json.py
       1.616s     7x  tests/test_bead/test_cli_show_compact.py
       1.568s     8x  tests/main/test_artifact_handler.py
       1.505s    10x  tests/main/test_parser_namespace_migrations.py
       1.380s    14x  tests/main/test_ops_commands.py
       1.337s     9x  tests/main/test_var_integration.py
       1.333s    17x  tests/test_bead/test_flag_beads.py
       1.264s    35x  tests/main/test_var_parser.py
  by AcePage.__aexit__:
      11.592s    33x  tests/test_ace_testing.py
       2.277s    10x  tests/ace/tui/test_artifacts_patches_navigator.py
       2.170s     5x  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py
       2.152s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
       1.729s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       1.639s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.547s    10x  tests/ace/tui/test_plugins_browser_pane_all_current.py
       1.459s    12x  tests/ace/tui/test_artifacts_scaffold.py
       1.441s     9x  tests/ace/tui/test_plugins_browser_pane_jump.py
       1.381s    10x  tests/ace/tui/test_config_pane_widget_commit.py
  by Pilot.pause(None):
       3.980s    57x  tests/test_models_panel_edit.py
       2.884s    42x  tests/test_models_panel_override_flows.py
       2.376s    39x  tests/test_models_panel_jump.py
       1.913s    42x  tests/test_models_panel_selector_builder.py
       1.697s    36x  tests/test_command_palette_modal.py
       1.639s    32x  tests/test_model_picker_modal.py
       1.577s    21x  tests/test_models_panel_history.py
       1.371s    27x  tests/test_plan_approval_modal_title.py
       1.302s    25x  tests/test_models_panel_provider_modal.py
       1.216s    21x  tests/test_models_panel_actions.py
  by sase.config.core.load_merged_config:
       0.554s    26x  tests/test_config_cache.py
       0.542s   280x  tests/test_bead/test_cli_show_style.py
       0.246s    70x  tests/main/test_var_parser.py
       0.201s    37x  tests/test_bead/test_cli_golden.py
       0.193s    23x  tests/test_plan_search_cli.py
       0.168s    23x  tests/test_plan_validate_diagnostics.py
       0.165s    25x  tests/test_bead/test_cli_search.py
       0.161s    52x  tests/main/test_completion_handler.py
       0.160s    16x  tests/main/test_doctor_command.py
       0.145s    42x  tests/main/test_parser_proc.py
  by YAML load:
       2.984s  4334x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.383s  4550x  tests/main/test_init_skills_sources.py
       0.790s   783x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.560s   741x  tests/test_bead_xprompt_tags.py
       0.455s     8x  tests/test_config_cache.py
       0.342s   282x  tests/test_pooled_alias_single_consumption.py
       0.330s    21x  tests/test_github_actions_ci.py
       0.281s     6x  tests/test_models_panel_keymaps.py
       0.274s  1172x  tests/main/test_init_memory_commit.py
       0.273s   257x  tests/fakey/test_retry_pipeline_e2e.py
  by subprocess.Popen:
       0.027s    34x  tests/test_procs_service.py
       0.022s     1x  tests/test_file_references_invoke.py
       0.017s     8x  tests/fakey/test_provider.py
       0.011s    13x  tests/monitor/test_monitor_supervise.py
       0.011s     3x  tests/test_axe_chop_preflight_policy.py
       0.008s    13x  tests/main/test_proc_handler_run.py
       0.007s    12x  tests/llm_provider/test_muse_artifacts.py
       0.007s    14x  tests/test_fork_workflow.py
       0.006s     8x  tests/test_procs_runner.py
       0.006s    10x  tests/llm_provider/test_muse_provider_core.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/agent_clis/test_cli.py
       0.000s     1x  tests/main/test_lsp_handler.py
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/test_changespec_current.py
       0.000s     1x  tests/test_patch_set_origin_cli.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260818T004547Z-2690267.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_budgets.json
- peak_worker_rss_kib: actual 1405040.000 exceeds budget 1100000.000 + 20% tolerance (1320000.000)
- causes.ace_page_enter: actual 536.574 exceeds budget 400.000 + 20% tolerance (480.000)
- causes.parser_create: actual 59.248 exceeds budget 35.000 + 20% tolerance (42.000)
- causes.pilot_pause_delay: actual 237.840 exceeds budget 190.000 + 20% tolerance (228.000)
- causes.subprocess_run: actual 392.939 exceeds budget 320.000 + 20% tolerance (384.000)
- causes.textual_app_run_test_enter: actual 454.941 exceeds budget 350.000 + 20% tolerance (420.000)
error: recipe `test-cost` failed on line 412 with exit code 1
error: recipe `check-full` failed on line 656 with exit code 1

