# Chat History - ace-run (0e.f0.f0--mon)

- **TIMESTAMP:** 2026-09-18 15:41:30 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 0e.f0.f0--mon

## Prompt

sase monitor start --command 'just check' --reason 'Finish verification for approved Agents secondary-only layout implementation; inline just check reached the governed full test lane and waited on pytest worker tokens'

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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.34.48 is missing 3 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] decide_gate_lifecycle: first appears in sase-core df4e00f (feat(gate-decision): add decide_gate_lifecycle classifier); release v0.34.38 contains it.
[core-floor-probe] select_remaining_commit_obligations: first appears in sase-core 8d5341a (feat(finalizer): select remaining declared repos after repair); no release tag contains it yet.
[core-floor-probe] sudo_validate_handshake: first appears in sase-core b70e64d (feat(sudo): add detached runner execution); release v0.34.52 contains it.
{"cache_hit": true, "capabilities": [{"commit": "df4e00f", "name": "decide_gate_lifecycle", "release": "v0.34.38", "subject": "feat(gate-decision): add decide_gate_lifecycle classifier"}, {"commit": "8d5341a", "name": "select_remaining_commit_obligations", "release": null, "subject": "feat(finalizer): select remaining declared repos after repair"}, {"commit": "b70e64d", "name": "sudo_validate_handshake", "release": "v0.34.52", "subject": "feat(sudo): add detached runner execution"}], "declared_floor": "0.34.48", "exit_code": 4, "message": "sase-core-rs==0.34.48 is missing 3 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 3991 test files in scope
coverage contexts: no baseline cached (run `just refresh-contexts-baseline`); static closure only
middle gear: no bounded lease (tokens-unavailable); escalating rather than queueing for one
escalating to the governed full test lane (rules: context-baseline-missing, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded)
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6359s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 680s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6390s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 711s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6420s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 741s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6450s, heartbeat 0s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 771s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6480s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 801s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6510s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 831s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6540s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 861s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6570s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 891s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6600s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 921s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6630s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 951s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6660s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 981s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6690s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1011s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6720s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1041s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6750s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1071s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6780s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1101s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6811s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1132s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6841s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1162s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6871s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1192s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6901s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1222s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6931s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1252s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6961s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1282s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 6991s, heartbeat 0s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1312s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7021s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1342s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7051s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1372s, heartbeat 0s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7082s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1403s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7112s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1433s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7142s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1463s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7172s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1493s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7202s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1523s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7233s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1554s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7263s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1584s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7293s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1614s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7323s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1644s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7353s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1674s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7384s, heartbeat 4s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1705s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7414s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1735s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7444s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1765s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7474s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1795s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7504s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1825s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7534s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1855s, heartbeat 5s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7564s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1885s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7594s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1915s, heartbeat 6s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7624s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1945s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7654s, heartbeat 5s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 1975s, heartbeat 1s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7684s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 2005s, heartbeat 4s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7714s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 2036s, heartbeat 3s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7745s, heartbeat 1s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 2066s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7775s, heartbeat 3s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 2096s, heartbeat 2s, argv 'tools/run_pytest scoped'
Waiting for a SASE pytest worker-token grant of 4-5 worker tokens; 0 tokens were available below the floor. Current holders: 6 tokens: pid 2403310, grant 6, age 7805s, heartbeat 2s, argv 'tools/run_pytest cost'; 5 tokens: pid 2847830, grant 5, age 2126s, heartbeat 6s, argv 'tools/run_pytest scoped'
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, xdist-3.8.0, mock-3.15.1, asyncio-1.4.0, hypothesis-6.167.1, inline-snapshot-0.35.4
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 5/5 workers
5 workers [43073 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
............................s........................................... [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
.........................................................s.............. [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
................................................................s....... [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
.......................................s................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
.................................................................s...... [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
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
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
..............................................s......................... [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
..........................................F..........................F.. [ 43%]
................s......F........F..............F....................F... [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
...............................................................F......F. [ 44%]
.....F.......F.....F........................................F........... [ 44%]
F....................................................................... [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
..............................s......................................... [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
...........................s............................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
..............sss.s..................................................... [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
.......................................................................F [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
...............ssss..................................................... [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
..........................................F............................. [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
............s........................................................... [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
..............................................s...........s.s........... [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
.................................F.FF................................... [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
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
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.................                                                        [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_fresh_init_records_and_seeds_root_beads_sidecar _____________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/widget--plans.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/clone-plans')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/.sase-sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/widget--plans.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/.sase-sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x764421538500>

    def test_fresh_init_records_and_seeds_root_beads_sidecar(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        project, _remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=False,
        )
    
>       initialize_sidecars(project, 1, specs)

tests/sdd_store/test_sidecar_bead_adoption.py:140: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/clone-plans')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/.sase-sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_r...sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/.sase-sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_fresh_init_records_and_se0/.sase-sdd-clone-staging/clone-plans-1363628e2ec19b56-1baeaf26b2714ec58adf32eca75a7a95/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_____ test_migration_imports_pushes_cleans_and_reruns_without_new_commits ______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/widget--research.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/clone-research')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/.sase-sdd-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/widget--research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/.sase-sdd-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441fcf4b00>

    def test_migration_imports_pushes_cleans_and_reruns_without_new_commits(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        project, remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=True,
        )
    
>       initialize_sidecars(project, 1, specs)

tests/sdd_store/test_sidecar_bead_adoption.py:165: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/clone-research')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/.sase-sdd-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_im...-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/.sase-sdd-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_imports_pushes_0/.sase-sdd-clone-staging/clone-research-368b055443e8c5f3-9070fa468d8d497b91b4080572379b88/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
____ test_migration_no_publish_copies_and_cleans_without_commits_or_pushes _____
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/widget--research.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/clone-research')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/.sase-sdd-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/widget--research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/.sase-sdd-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441fde7c20>

    def test_migration_no_publish_copies_and_cleans_without_commits_or_pushes(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        project, remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=True,
        )
        from sase.sdd import _bead_adoption
    
        monkeypatch.setattr(
            "sase.sdd._sidecar_init.push_sidecar",
            lambda _root: pytest.fail("--no-commit must not push seeded sidecars"),
        )
        monkeypatch.setattr(
            _bead_adoption,
            "push_sidecar",
            lambda _root: pytest.fail("--no-commit must not push bead adoption"),
        )
        plans_head = _git_output(clones["plans"], "rev-parse", "HEAD")
    
>       initialize_sidecars(
            project,
            1,
            specs,
            publish_sidecar_changes=False,
        )

tests/sdd_store/test_sidecar_bead_adoption.py:212: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/clone-research')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/.sase-sdd-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no...-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/.sase-sdd-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_no_publish_copi0/.sase-sdd-clone-staging/clone-research-6ba0aebcc7364085-85c4b45197aa4e8297b581d8b1e2392b/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
__________ test_migration_accepts_minimal_config_and_projection_store __________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/widget--research.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/clone-research')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/.sase-sdd-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/widget--research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/.sase-sdd-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x764422ed0050>

    def test_migration_accepts_minimal_config_and_projection_store(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        project, _remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=True,
        )
        shutil.rmtree(clones["plans"] / "beads" / "events")
        metadata = clones["plans"] / "beads" / "metadata.json"
        if metadata.exists():
            metadata.unlink()
        git(clones["plans"], "add", "-A")
        git(clones["plans"], "commit", "-m", "Keep only the minimal bead store")
        git(clones["plans"], "push", "origin", "HEAD")
    
>       initialize_sidecars(project, 1, specs)

tests/sdd_store/test_sidecar_bead_adoption.py:254: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/clone-research')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/.sase-sdd-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_ac...-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/.sase-sdd-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_migration_accepts_minimal0/.sase-sdd-clone-staging/clone-research-b569fde33585a8fa-d649101415a74f739c984b2f818bc884/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
________ test_failed_import_push_preserves_schema_two_and_rerun_retries ________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_import_push_preser0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441ee51940>

    def test_failed_import_push_preserves_schema_two_and_rerun_retries(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        project, _remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=True,
        )
        from sase.sdd import _bead_adoption
    
        real_push = _bead_adoption.push_sidecar
        beads_pushes = 0
    
        def fail_import_push(root: Path) -> None:
            nonlocal beads_pushes
            if root == clones["beads"]:
                beads_pushes += 1
                if beads_pushes == 1:
                    raise SddMaterializationError("simulated import push failure")
            real_push(root)
    
        monkeypatch.setattr(_bead_adoption, "push_sidecar", fail_import_push)
    
>       with pytest.raises(SddMaterializationError, match="simulated import push"):
E       AssertionError: Regex pattern did not match.
E         Expected regex: 'simulated import push'
E         Actual message: 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_import_push_preser0/.sase-sdd-clone-staging/clone-research-b70a8efdf04da3a7-151bb7d63ef44419993384c3684683eb/clone does not have a resolvable HEAD'

tests/sdd_store/test_sidecar_bead_adoption.py:287: AssertionError
______ test_failed_cleanup_push_warns_and_next_run_pushes_existing_commit ______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/widget--research.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/clone-research')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/.sase-sdd-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/widget--research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/.sase-sdd-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441ffb27e0>
caplog = <_pytest.logging.LogCaptureFixture object at 0x76441ffb3860>

    def test_failed_cleanup_push_warns_and_next_run_pushes_existing_commit(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        caplog: pytest.LogCaptureFixture,
    ) -> None:
        project, remotes, clones, specs = _configure_transaction(
            tmp_path,
            monkeypatch,
            legacy_state=True,
        )
        from sase.sdd import _bead_adoption
    
        real_push = _bead_adoption.push_sidecar
    
        def fail_post_switch_plans_push(root: Path) -> None:
            record = read_sdd_store_record(project)
            if root == clones["plans"] and record is not None and record.has_split_beads:
                raise SddMaterializationError("simulated cleanup push failure")
            real_push(root)
    
        monkeypatch.setattr(
            _bead_adoption,
            "push_sidecar",
            fail_post_switch_plans_push,
        )
        caplog.set_level(logging.WARNING)
    
>       initialize_sidecars(project, 1, specs)

tests/sdd_store/test_sidecar_bead_adoption.py:330: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/clone-research')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/.sase-sdd-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_clean...-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/.sase-sdd-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_failed_cleanup_push_warns0/.sase-sdd-clone-staging/clone-research-ba3be832092f1505-f7e8edcf34c349e6ad6eacce603d127c/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
________ test_custom_sidecar_init_uses_pinned_private_provider_options _________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/shared-artifacts.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/artifacts-clone')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/.sase-sdd-clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/shared-artifacts.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/.sase-sdd-clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x764421571010>

    def test_custom_sidecar_init_uses_pinned_private_provider_options(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        remote = bare_remote(tmp_path, "shared-artifacts")
        clone = tmp_path / "artifacts-clone"
        captured: list[dict[str, object]] = []
        spec = SidecarInitSpec(
            role="artifacts",
            repo="acme/shared-artifacts",
            remote_url=str(remote),
            visibility="private",
            description="Durable build artifacts.",
        )
    
        def create_remote(
            _primary: str,
            _workspace: str,
            options: dict[str, object],
        ) -> dict[str, object]:
            captured.append(options)
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": "acme/shared-artifacts",
                "remote_url": str(remote),
                "discovery": "found",
                "created": True,
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, _role: str(clone),
        )
    
>       outcome = initialize_sidecars(
            project,
            1,
            (spec,),
            creation_authorized={"artifacts": True},
        )

tests/sdd_store/test_sidecar_init_creation.py:82: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/artifacts-clone')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/.sase-sdd-clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidec...clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/.sase-sdd-clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_custom_sidecar_init_uses_0/.sase-sdd-clone-staging/artifacts-clone-5c58db8f93019bca-348beab8334749b496e8f4f9b6c4cc26/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
___________ test_split_init_creates_both_repos_before_writing_record ___________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/plans.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/widget--plans')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/.sase-sdd-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/plans.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/.sase-sdd-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x764421ffb380>

    def test_split_init_creates_both_repos_before_writing_record(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        (project / "sase.yml").write_text("is_sase_managed: true\n")
        remotes = {kind: bare_remote(tmp_path, kind) for kind in ("plans", "research")}
        clones = {kind: tmp_path / f"widget--{kind}" for kind in remotes}
        calls: list[tuple[str, bool]] = []
    
        def create_remote(
            _primary: str, _workspace: str, options: dict[str, object]
        ) -> dict[str, object]:
            kind = str(options["sdd_sidecar_suffix"])
            calls.append((kind, options["sdd_creation_authorized"] is True))
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": f"acme/widget--{kind}",
                "remote_url": str(remotes[kind]),
                "discovery": "found",
                "created": True,
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, kind: str(clones[kind]),
        )
    
>       outcome = initialize_sidecars(
            project,
            1,
            (SidecarInitSpec(role="plans"), SidecarInitSpec(role="research")),
            creation_authorized={"plans": True, "research": True},
        )

tests/sdd_store/test_sidecar_init_creation.py:131: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/widget--plans')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/.sase-sdd-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_c...d-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/.sase-sdd-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_creates_both_r0/.sase-sdd-clone-staging/widget--plans-afb1c68bfab3dc43-c6a8f562fc8b49bb84ec7a27f576fa53/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_ test_split_init_no_publish_writes_plans_and_beads_without_commits_or_pushes __
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/plans.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/widget--plans')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/.sase-sdd-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/plans.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/.sase-sdd-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441f92e720>

    def test_split_init_no_publish_writes_plans_and_beads_without_commits_or_pushes(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        roles = ("plans", "beads")
        remotes = {role: bare_remote(tmp_path, role) for role in roles}
        clones = {role: tmp_path / f"widget--{role}" for role in roles}
    
        def create_remote(
            _primary: str, _workspace: str, options: dict[str, object]
        ) -> dict[str, object]:
            role = str(options["sdd_sidecar_suffix"])
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": f"acme/widget--{role}",
                "remote_url": str(remotes[role]),
                "discovery": "found",
                "created": True,
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, role: str(clones[role]),
        )
        monkeypatch.setattr(
            "sase.sdd._sidecar_init.push_sidecar",
            lambda _root: pytest.fail("--no-commit must not push sidecars"),
        )
    
>       initialize_sidecars(
            project,
            1,
            tuple(SidecarInitSpec(role=role) for role in roles),
            creation_authorized=dict.fromkeys(roles, True),
            publish_sidecar_changes=False,
        )

tests/sdd_store/test_sidecar_init_creation.py:195: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/widget--plans')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/.sase-sdd-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_n...d-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/.sase-sdd-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_no_publish_wri0/.sase-sdd-clone-staging/widget--plans-71b391e877058265-dc6497f5dfb048c5806402fd644757ee/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_____ test_split_init_materializes_plans_and_custom_role_without_research ______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/plans.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/widget--plans')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/.sase-sdd-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/plans.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/.sase-sdd-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441f92e810>

    def test_split_init_materializes_plans_and_custom_role_without_research(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        roles = ("plans", "designs")
        remotes = {role: bare_remote(tmp_path, role) for role in roles}
        clones = {role: tmp_path / f"widget--{role}" for role in roles}
    
        def create_remote(
            _primary: str, _workspace: str, options: dict[str, object]
        ) -> dict[str, object]:
            role = str(options["sdd_sidecar_suffix"])
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": f"acme/widget--{role}",
                "remote_url": str(remotes[role]),
                "discovery": "found",
                "created": True,
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, role: str(clones[role]),
        )
    
>       outcome = initialize_sidecars(
            project,
            1,
            tuple(SidecarInitSpec(role=role) for role in roles),
            creation_authorized=dict.fromkeys(roles, True),
        )

tests/sdd_store/test_sidecar_init_creation.py:256: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/widget--plans')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/.sase-sdd-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_m...d-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/.sase-sdd-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_materializes_p0/.sase-sdd-clone-staging/widget--plans-f2d7284ec309bab0-6bdaf3f5787f408b9a1d99a77726662a/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_______ test_agents_init_uses_hidden_root_and_records_every_sidecar_role _______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/plans.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/widget--plans')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/.sase-sdd-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/plans.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/.sase-sdd-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x764421da84d0>

    def test_agents_init_uses_hidden_root_and_records_every_sidecar_role(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        remotes = {
            role: bare_remote(tmp_path, role) for role in ("plans", "research", "agents")
        }
        visible_clones = {
            role: tmp_path / f"widget--{role}" for role in ("plans", "research")
        }
        state_root = tmp_path / "state"
        captured: list[tuple[str, str, bool]] = []
        monkeypatch.setenv("SASE_HOME", str(state_root))
        monkeypatch.setattr(
            "sase.bead.project_name.infer_project_name_from_cwd",
            lambda _root: "gh_acme__widget",
        )
    
        def create_remote(
            _primary: str,
            _workspace: str,
            options: dict[str, object],
        ) -> dict[str, object]:
            role = str(options["sdd_sidecar_suffix"])
            captured.append(
                (
                    role,
                    str(options["sdd_visibility"]),
                    options["sdd_creation_authorized"] is True,
                )
            )
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": f"acme/widget--{role}",
                "remote_url": str(remotes[role]),
                "discovery": "found",
                "created": True,
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, role: str(visible_clones[role]),
        )
        specs = (
            SidecarInitSpec(role="plans"),
            SidecarInitSpec(role="research"),
            SidecarInitSpec(
                role="agents",
                visibility="private",
                description="Private commit-associated agents.",
            ),
        )
    
>       outcome = initialize_sidecars(
            project,
            1,
            specs,
            creation_authorized={"plans": True, "research": True, "agents": True},
        )

tests/sdd_store/test_sidecar_init_creation.py:335: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/widget--plans')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/.sase-sdd-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_...d-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/.sase-sdd-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_agents_init_uses_hidden_r0/.sase-sdd-clone-staging/widget--plans-389be68ecd8b3c1d-e90356714b394f01b37ffc4a50d7845c/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_______________ test_split_init_cuts_over_changed_pinned_sidecar _______________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/research-clone')
primary_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/.missing-primary')
remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/shared-research.git'
deadline = None

    def _replace_workspace_sdd_clone(
        workspace_sdd: Path,
        primary_sdd: Path,
        remote_url: str | None,
        *,
        deadline: float | None = None,
    ) -> None:
        """Atomically replace legacy workspace content after primary adoption."""
    
        backup = workspace_sdd.with_name(f".sdd.recovery-{uuid.uuid4().hex}")
        try:
>           with _staged_sdd_clone_replacement(
                workspace_sdd,
                primary_sdd,
                remote_url,
                deadline=deadline,
            ) as staged:

src/sase/sdd/_store_link.py:289: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/usr/lib/python3.12/contextlib.py:137: in __enter__
    return next(self.gen)
           ^^^^^^^^^^^^^^
src/sase/sdd/_store_clone_ops.py:423: in staged_sdd_clone_replacement
    _validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/.sase-sdd-clone-staging/research-clone-f3e4183fa6e9f5ca-53f63692498e4c8c826b5276fecd5160/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/shared-research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/.sase-sdd-clone-staging/research-clone-f3e4183fa6e9f5ca-53f63692498e4c8c826b5276fecd5160/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441f92f5c0>

    def test_split_init_cuts_over_changed_pinned_sidecar(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        old_remote = bare_remote(tmp_path, "widget--research")
        shared_remote = bare_remote(tmp_path, "shared-research")
        clone = tmp_path / "research-clone"
        git(tmp_path, "clone", str(old_remote), str(clone))
        captured: list[dict[str, object]] = []
        write_sdd_store_record(
            project,
            {
                "schema_version": 2,
                "storage": "sidecar_repos",
                "provider": "github",
                "host": "github.com",
                "sidecars": {
                    "plans": {
                        "repo": "acme/widget--plans",
                        "remote_url": "git@github.com:acme/widget--plans.git",
                    },
                    "research": {
                        "repo": "acme/widget--research",
                        "remote_url": str(old_remote),
                    },
                },
            },
        )
    
        def create_remote(
            _primary: str, _workspace: str, options: dict[str, object]
        ) -> dict[str, object]:
            captured.append(options)
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": "sase-org/shared-research",
                "remote_url": str(shared_remote),
                "discovery": "found",
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, _kind: str(clone),
        )
    
>       outcome = initialize_sidecars(
            project,
            0,
            (
                SidecarInitSpec(
                    role="research",
                    repo="sase-org/shared-research",
                    remote_url=str(shared_remote),
                ),
            ),
        )

tests/sdd_store/test_sidecar_init_reconciliation.py:194: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:84: in ensure_sidecar_sdd_clone
    _replace_workspace_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/research-clone')
primary_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/.missing-primary')
remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/shared-research.git'
deadline = None

    def _replace_workspace_sdd_clone(
        workspace_sdd: Path,
        primary_sdd: Path,
        remote_url: str | None,
        *,
        deadline: float | None = None,
    ) -> None:
        """Atomically replace legacy workspace content after primary adoption."""
    
        backup = workspace_sdd.with_name(f".sdd.recovery-{uuid.uuid4().hex}")
        try:
            with _staged_sdd_clone_replacement(
                workspace_sdd,
                primary_sdd,
                remote_url,
                deadline=deadline,
            ) as staged:
                had_existing = os.path.lexists(workspace_sdd)
                if had_existing:
                    workspace_sdd.replace(backup)
                try:
                    staged.replace(workspace_sdd)
                except Exception:
                    if (
                        had_existing
                        and os.path.lexists(backup)
                        and not os.path.lexists(workspace_sdd)
                    ):
                        backup.replace(workspace_sdd)
                    raise
                if had_existing:
                    if backup.is_dir() and not backup.is_symlink():
                        shutil.rmtree(backup, ignore_errors=True)
                    else:
                        try:
                            backup.unlink()
                        except OSError:
                            pass
        except SddMaterializationError:
            raise
        except Exception as exc:
>           raise SddMaterializationError(
                f"could not replace legacy workspace SDD path at {workspace_sdd}"
            ) from exc
E           sase.sdd._store_types.SddMaterializationError: could not replace legacy workspace SDD path at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_cuts_over_chan0/research-clone

src/sase/sdd/_store_link.py:319: SddMaterializationError
______________ test_split_init_re_records_stale_research_sidecar _______________
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

remote_url = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/widget--research.git'
workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/research-clone')
reference_repo = None, strict = True, deadline = None

    def clone_sdd_store(
        remote_url: str,
        workspace_sdd: Path,
        *,
        reference_repo: Path | None = None,
        strict: bool = False,
        deadline: float | None = None,
    ) -> bool:
        workspace_sdd = workspace_sdd.expanduser()
        if is_http_git_remote(remote_url):
            return handle_failed_sdd_clone(
                workspace_sdd,
                f"refusing HTTP(S) SDD sidecar remote {remote_url!r}; "
                "materialization requires an SSH or local Git remote and Git was "
                "not invoked",
                strict=strict,
                cleanup_path=None,
            )
    
        try:
            with _clone_materialization_transaction(
                workspace_sdd,
                deadline=deadline,
            ) as transaction:
                if os.path.lexists(workspace_sdd):
                    if _valid_published_sdd_clone(
                        workspace_sdd,
                        expected_remote=remote_url,
                        deadline=deadline,
                    ):
                        return True
                    return handle_failed_sdd_clone(
                        workspace_sdd,
                        f"refusing to overwrite existing SDD store at {workspace_sdd}; "
                        "the concurrently materialized destination is not a healthy "
                        "clone of the configured remote",
                        strict=strict,
                        cleanup_path=transaction.clone_path,
                    )
    
                cloned = _clone_sdd_store_to_path(
                    remote_url,
                    transaction.clone_path,
                    reference_repo=reference_repo,
                    strict=strict,
                    deadline=deadline,
                    canonical_sdd=workspace_sdd,
                )
                if not cloned:
                    return False
                try:
>                   transaction.publish(
                        expected_remote=remote_url,
                        deadline=deadline,
                    )

src/sase/sdd/_store_clone_ops.py:96: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_store_clone_transaction.py:83: in publish
    validate_staged_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/.sase-sdd-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone')
expected_remote = '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/widget--research.git'
deadline = None

    def validate_staged_sdd_clone(
        path: Path, *, expected_remote: str | None, deadline: float | None
    ) -> None:
        if not (path / ".git").is_dir():
            raise ClonePublicationError(f"staged SDD clone at {path} has no .git directory")
        branch = _git_validation_stdout(
            path,
            ["symbolic-ref", "--quiet", "--short", "HEAD"],
            op="sdd.clone.validate_branch",
            deadline=deadline,
        )
        if branch is None:
            raise ClonePublicationError(
                f"staged SDD clone at {path} is not on an attached branch"
            )
        head = _git_validation_stdout(
            path,
            ["rev-parse", "--verify", "HEAD"],
            op="sdd.clone.validate_head",
            deadline=deadline,
        )
        if head is None:
>           raise ClonePublicationError(
                f"staged SDD clone at {path} does not have a resolvable HEAD"
            )
E           sase.sdd._store_clone_transaction.ClonePublicationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/.sase-sdd-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_transaction.py:175: ClonePublicationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x76441f92d550>

    def test_split_init_re_records_stale_research_sidecar(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        configure_git_environment(monkeypatch)
        project = tmp_path / "widget"
        project.mkdir()
        (project / ".git").mkdir()
        research_remote = bare_remote(tmp_path, "widget--research")
        clone = tmp_path / "research-clone"
        write_sdd_store_record(
            project,
            {
                "schema_version": 2,
                "storage": "sidecar_repos",
                "provider": "github",
                "host": "github.com",
                "sidecars": {
                    "plans": {
                        "repo": "acme/widget--plans",
                        "remote_url": "git@github.com:acme/widget--plans.git",
                    },
                    "research": {
                        "repo": "sase-org/sase--research",
                        "remote_url": "git@github.com:sase-org/sase--research.git",
                    },
                },
            },
        )
    
        def create_remote(
            _primary: str, _workspace: str, options: dict[str, object]
        ) -> dict[str, object]:
            assert options["sdd_repo"] == "acme/widget--research"
            assert options["sdd_remote_url"] == str(research_remote)
            return {
                "schema_version": 1,
                "storage": "separate_repo",
                "provider": "github",
                "host": "github.com",
                "repo": "acme/widget--research",
                "remote_url": str(research_remote),
                "discovery": "found",
            }
    
        monkeypatch.setattr("sase.workspace_provider.create_sdd_remote", create_remote)
        monkeypatch.setattr(
            "sase.linked_repos.sidecar_repo_clone_dir",
            lambda _workspace, _kind: str(clone),
        )
    
>       outcome = initialize_sidecars(
            project,
            0,
            (
                SidecarInitSpec(
                    role="research",
                    repo="acme/widget--research",
                    remote_url=str(research_remote),
                ),
            ),
        )

tests/sdd_store/test_sidecar_init_reconciliation.py:274: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_sidecar_init.py:204: in initialize_sidecars
    ensure_sidecar_sdd_clone(root, sidecar.remote_url, strict=True)
src/sase/sdd/_store_link.py:116: in ensure_sidecar_sdd_clone
    cloned = _clone_sdd_store(
src/sase/sdd/_store_clone_ops.py:101: in clone_sdd_store
    return handle_failed_sdd_clone(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_sdd = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/research-clone')
message = 'staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/.sase-sdd-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone does not have a resolvable HEAD'
strict = True
cause = ClonePublicationError('staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_r...-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone does not have a resolvable HEAD')
transient = False
cleanup_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/.sase-sdd-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone')

    def handle_failed_sdd_clone(
        workspace_sdd: Path,
        message: str,
        *,
        strict: bool,
        cause: Exception | None = None,
        transient: bool = False,
        cleanup_path: Path | None = None,
    ) -> bool:
        """Remove partial clone output and optionally fail the setup transaction."""
    
        if cleanup_path is not None:
            _remove_partial_sdd_clone(cleanup_path)
        if strict:
            error_cls = (
                SddTransientMaterializationError if transient else SddMaterializationError
            )
            error = error_cls(message)
            if cause is not None:
>               raise error from cause
E               sase.sdd._store_types.SddMaterializationError: staged SDD clone at /var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw1/test_split_init_re_records_sta0/.sase-sdd-clone-staging/research-clone-5c9137d69f56cd3d-3d430fb2f77a4f1592f477405691b02a/clone does not have a resolvable HEAD

src/sase/sdd/_store_clone_ops.py:577: SddMaterializationError
_______ test_persist_monitor_result_waits_for_a_starter_still_finalizing _______
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw2/test_persist_monitor_result_wa0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f80902497f0>

    def test_persist_monitor_result_waits_for_a_starter_still_finalizing(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A starter that settles mid-wait still yields a hydrated parent id.
    
        Reproduces the sase-11o.1 race: the monitor's result-capture publish
        happens while the starter is still finalizing (no ``continuation_node_id``
        or ``done.json`` yet). The publish path must wait, bounded, instead of
        stamping ``needs_recovery`` immediately.
        """
        from sase.continuation_capture import persist_monitor_result
    
        monkeypatch.setattr(
            "sase.shells.followup.DEFAULT_STARTER_SETTLE_TIMEOUT_SECONDS", 2.0
        )
        monkeypatch.setattr("sase.shells.followup.STARTER_SETTLE_POLL_SECONDS", 0.02)
    
        starter = tmp_path / "starter"
        starter.mkdir()
        (starter / "agent_meta.json").write_text(
            json.dumps({"name": "acme"}), encoding="utf-8"
        )
        monitor = tmp_path / "monitor"
        monitor.mkdir()
        meta = _base_monitor_meta(tmp_path, starter)
    
        def _settle_starter() -> None:
            time.sleep(0.15)  # sase-test-wait: create a deterministic starter-settle race
            (starter / "agent_meta.json").write_text(
                json.dumps(
                    {"name": "acme", "continuation_node_id": "agent-delta:starter:1"}
                ),
                encoding="utf-8",
            )
            (starter / "done.json").write_text("{}", encoding="utf-8")
    
        thread = threading.Thread(target=_settle_starter)
        thread.start()
        try:
            with (
                patch("sase.core.continuation_facade.validate_monitor_result"),
                patch("sase.core.continuation_facade.validate_continuation_node"),
            ):
                started = time.monotonic()
                published = persist_monitor_result(
                    artifacts_dir=monitor,
                    meta=meta,
                    monitor_state="completed",
                    exit_code=0,
                    elapsed_seconds=1.0,
                    stopped_at="2026-09-16T00:00:01Z",
                    diagnostic_manifest=None,
                    retained_log={"log_ref": "local:log", "complete": True},
                    project_name="proj",
                    update_meta=False,
                )
                elapsed = time.monotonic() - started
        finally:
            thread.join(timeout=5.0)
        assert not thread.is_alive()
>       assert elapsed < 2.0
E       assert 3.5434073908254504 < 2.0

tests/continuation/test_monitor_result.py:153: AssertionError
________ test_sidecar_materialization_uses_remote_not_divergent_primary ________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw4/test_sidecar_materialization_u0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x75135cee6bd0>

    def test_sidecar_materialization_uses_remote_not_divergent_primary(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        remote = tmp_path / "research.git"
        primary = tmp_path / "primary-research"
        remote_seed = tmp_path / "remote-seed"
        target = tmp_path / "workspace" / "sase" / "repos" / "research"
        wrong_remote = tmp_path / "wrong.git"
        init_bare_repo(remote)
        clone(remote, primary)
        readme = primary / "README.md"
        readme.write_text("initial\n", encoding="utf-8")
        commit_all(primary, "Initialize research")
        git(["push", "-u", "origin", "main"], primary)
        clone(remote, remote_seed)
    
        readme.write_text("durable primary only\n", encoding="utf-8")
        commit_all(primary, "Unpushed durable-primary research")
        primary_only_head = git(["rev-parse", "HEAD"], primary).stdout.strip()
        (remote_seed / "README.md").write_text("authoritative remote\n", encoding="utf-8")
        commit_all(remote_seed, "Advance research remote incompatibly")
        git(["push"], remote_seed)
        remote_head = git(["rev-parse", "HEAD"], remote_seed).stdout.strip()
    
        target.mkdir(parents=True)
        git(["init", "-q"], target)
        init_git_identity(target)
        git(["remote", "add", "origin", str(wrong_remote)], target)
        (target / "stale.txt").write_text("wrong clone\n", encoding="utf-8")
        commit_all(target, "Commit stale workspace content")
        clone_commands: list[list[str]] = []
        from sase.sdd import _commit
    
        original_run_sdd_git = _commit.run_sdd_git
    
        def record_git(args: list[str], **kwargs):
            if args and args[0] == "clone":
                clone_commands.append(args)
            return original_run_sdd_git(args, **kwargs)
    
        monkeypatch.setattr("sase.sdd._commit.run_sdd_git", record_git)
    
        result = materialize_linked_repo_workspace(
            primary_dir=str(primary),
            workspace_dir=str(target),
            workspace_num=10,
            expected_remote_url=str(remote),
        )
    
        assert result == str(target.resolve())
        assert not (target / "stale.txt").exists()
        assert (target / "README.md").read_text(encoding="utf-8") == (
            "authoritative remote\n"
        )
        assert git(["rev-parse", "HEAD"], target).stdout.strip() == remote_head
        assert (
            primary_only_head not in git(["rev-list", "--all"], target).stdout.splitlines()
        )
        assert git(["status", "--porcelain"], target).stdout == ""
        assert not (target / ".git" / "rebase-merge").exists()
        assert not (target / ".git" / "rebase-apply").exists()
        assert not (target / ".git" / "objects" / "info" / "alternates").exists()
        assert git(["remote", "get-url", "origin"], target).stdout.strip() == str(remote)
>       assert clone_commands == [
            [
                "clone",
                "--reference-if-able",
                str(primary),
                "--dissociate",
                str(remote),
                str(target),
            ]
        ]
E       AssertionError: assert [['clone', '-...65fc9/clone']] == [['clone', '-...os/research']]
E         
E         At index 0 diff: ['clone', '--reference-if-able', '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw4/test_sidecar_materialization_u0/primary-research', '--dissociate', '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw4/test_sidecar_materialization_u0/research.git', '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-gw4/test_sidecar_materialization_u0/workspace/sase/repos/.sase-sdd-clone-staging/research-45674b33d13d052b-dbc4001d102a445ebd1d7f916c165fc9/clone'] != ['clone', '--reference-if-able', '/var/tmp/sase-0eb6951e/pytest-of-bryan/pytest-0/popen-...
E         
E         ...Full output truncated (2 lines hidden), use '-vv' to show

tests/test_linked_repo_workspaces.py:235: AssertionError
______ test_watcher_active_clean_agents_tick_refreshes_selected_file_only ______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

    @pytest.mark.asyncio
    async def test_watcher_active_clean_agents_tick_refreshes_selected_file_only() -> None:
        """Clean Agents-tab ticks refresh the selected live diff, not the loader."""
        app = _FakeApp(watcher_active=True)
        agent = _make_agent()
        app._agents = [agent]
    
>       await app._run_auto_refresh()

tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py:80: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/event_refresh/_auto_refresh.py:69: in _run_auto_refresh
    await self._run_auto_refresh_body()
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:99: in _run_auto_refresh_body
    axe_file_opens = await self._run_auto_refresh_surfaces(
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:424: in _run_auto_refresh_surfaces
    self._refresh_selected_agent_file_panel()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.ace.tui._event_handlers_dirty_flags_helpers._FakeApp object at 0x7644211bb4d0>

    def _refresh_selected_agent_file_panel(self) -> bool:
        """Refresh only the selected agent's file panel when it is safe to do so."""
        if self.current_tab != "agents":
            return False
        if getattr(self, "current_attempt_number", None) is not None:
            return False
    
        agent = self._get_selected_agent()  # type: ignore[attr-defined]
        if agent is None or not agent_has_live_file_panel(agent):
            return False
    
        from textual.css.query import NoMatches
    
        from ...widgets import AgentDetail
    
        try:
            agent_detail = self.query_one(  # type: ignore[attr-defined]
                "#agent-detail-panel", AgentDetail
            )
        except NoMatches:
            return False
    
>       if not agent_detail.is_file_visible():
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AttributeError: '_FakeAgentDetail' object has no attribute 'is_file_visible'

src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:56: AttributeError
______ test_watcher_active_clean_tick_skips_non_file_detail_modes[tools] _______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

panel_mode_label = 'tools'

    @pytest.mark.asyncio
    @pytest.mark.parametrize("panel_mode_label", ["tools", "none"])
    async def test_watcher_active_clean_tick_skips_non_file_detail_modes(
        panel_mode_label: str,
    ) -> None:
        app = _FakeApp(watcher_active=True)
        app._agents = [_make_agent()]
        app.agent_detail.panel_mode_label = panel_mode_label
    
>       await app._run_auto_refresh()

tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/event_refresh/_auto_refresh.py:69: in _run_auto_refresh
    await self._run_auto_refresh_body()
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:99: in _run_auto_refresh_body
    axe_file_opens = await self._run_auto_refresh_surfaces(
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:424: in _run_auto_refresh_surfaces
    self._refresh_selected_agent_file_panel()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.ace.tui._event_handlers_dirty_flags_helpers._FakeApp object at 0x76441fe951f0>

    def _refresh_selected_agent_file_panel(self) -> bool:
        """Refresh only the selected agent's file panel when it is safe to do so."""
        if self.current_tab != "agents":
            return False
        if getattr(self, "current_attempt_number", None) is not None:
            return False
    
        agent = self._get_selected_agent()  # type: ignore[attr-defined]
        if agent is None or not agent_has_live_file_panel(agent):
            return False
    
        from textual.css.query import NoMatches
    
        from ...widgets import AgentDetail
    
        try:
            agent_detail = self.query_one(  # type: ignore[attr-defined]
                "#agent-detail-panel", AgentDetail
            )
        except NoMatches:
            return False
    
>       if not agent_detail.is_file_visible():
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AttributeError: '_FakeAgentDetail' object has no attribute 'is_file_visible'

src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:56: AttributeError
_______ test_watcher_active_clean_tick_skips_non_file_detail_modes[none] _______
[gw1] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/bin/python

panel_mode_label = 'none'

    @pytest.mark.asyncio
    @pytest.mark.parametrize("panel_mode_label", ["tools", "none"])
    async def test_watcher_active_clean_tick_skips_non_file_detail_modes(
        panel_mode_label: str,
    ) -> None:
        app = _FakeApp(watcher_active=True)
        app._agents = [_make_agent()]
        app.agent_detail.panel_mode_label = panel_mode_label
    
>       await app._run_auto_refresh()

tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py:107: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/event_refresh/_auto_refresh.py:69: in _run_auto_refresh
    await self._run_auto_refresh_body()
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:99: in _run_auto_refresh_body
    axe_file_opens = await self._run_auto_refresh_surfaces(
src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:424: in _run_auto_refresh_surfaces
    self._refresh_selected_agent_file_panel()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.ace.tui._event_handlers_dirty_flags_helpers._FakeApp object at 0x76441fcde4e0>

    def _refresh_selected_agent_file_panel(self) -> bool:
        """Refresh only the selected agent's file panel when it is safe to do so."""
        if self.current_tab != "agents":
            return False
        if getattr(self, "current_attempt_number", None) is not None:
            return False
    
        agent = self._get_selected_agent()  # type: ignore[attr-defined]
        if agent is None or not agent_has_live_file_panel(agent):
            return False
    
        from textual.css.query import NoMatches
    
        from ...widgets import AgentDetail
    
        try:
            agent_detail = self.query_one(  # type: ignore[attr-defined]
                "#agent-detail-panel", AgentDetail
            )
        except NoMatches:
            return False
    
>       if not agent_detail.is_file_visible():
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AttributeError: '_FakeAgentDetail' object has no attribute 'is_file_visible'

src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py:56: AttributeError
=============================== warnings summary ===============================
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:859: DeprecationWarning: This process (pid=3214642) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3214636) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /usr/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=3214639) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/actions/update_toast.py:91: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
121.44s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
110.02s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
98.00s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
65.02s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
49.60s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
41.32s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
40.01s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
36.68s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
30.66s call     tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
28.20s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
26.27s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
24.78s call     tests/test_agent_load_tiering_production_oracle.py::test_production_oracle_query_battery_matches_source_scan
23.37s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
23.26s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
22.55s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
21.65s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
21.04s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
20.23s call     tests/test_command_palette_wiring.py::test_palette_context_uses_current_tab_badge
20.07s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
18.35s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
=========================== short test summary info ============================
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_fresh_init_records_and_seeds_root_beads_sidecar
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_imports_pushes_cleans_and_reruns_without_new_commits
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_no_publish_copies_and_cleans_without_commits_or_pushes
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_migration_accepts_minimal_config_and_projection_store
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_import_push_preserves_schema_two_and_rerun_retries
FAILED tests/sdd_store/test_sidecar_bead_adoption.py::test_failed_cleanup_push_warns_and_next_run_pushes_existing_commit
FAILED tests/sdd_store/test_sidecar_init_creation.py::test_custom_sidecar_init_uses_pinned_private_provider_options
FAILED tests/sdd_store/test_sidecar_init_creation.py::test_split_init_creates_both_repos_before_writing_record
FAILED tests/sdd_store/test_sidecar_init_creation.py::test_split_init_no_publish_writes_plans_and_beads_without_commits_or_pushes
FAILED tests/sdd_store/test_sidecar_init_creation.py::test_split_init_materializes_plans_and_custom_role_without_research
FAILED tests/sdd_store/test_sidecar_init_creation.py::test_agents_init_uses_hidden_root_and_records_every_sidecar_role
FAILED tests/sdd_store/test_sidecar_init_reconciliation.py::test_split_init_cuts_over_changed_pinned_sidecar
FAILED tests/sdd_store/test_sidecar_init_reconciliation.py::test_split_init_re_records_stale_research_sidecar
FAILED tests/continuation/test_monitor_result.py::test_persist_monitor_result_waits_for_a_starter_still_finalizing
FAILED tests/test_linked_repo_workspaces.py::test_sidecar_materialization_uses_remote_not_divergent_primary
FAILED tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py::test_watcher_active_clean_agents_tick_refreshes_selected_file_only
FAILED tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py::test_watcher_active_clean_tick_skips_non_file_detail_modes[tools]
FAILED tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py::test_watcher_active_clean_tick_skips_non_file_detail_modes[none]
==== 18 failed, 43034 passed, 22 skipped, 85 warnings in 2324.72s (0:38:44) ====
error: Recipe `test-scoped` failed on line 472 with exit code 1
error: Recipe `check` failed on line 682 with exit code 1

