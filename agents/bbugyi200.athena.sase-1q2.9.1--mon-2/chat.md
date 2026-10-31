# Chat History - ace-run (sase-1q2.9.1--mon-2)

- **TIMESTAMP:** 2026-10-31 08:13:37 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1q2.9.1--mon-2

## Prompt

sase monitor start --command 'for run_idx in 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20; do .venv/bin/python -m pytest -q tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home || exit $?; done; for run_idx in 1 2 3; do .venv/bin/python -m pytest -q -n 8 tests/ace/tui/ || exit $?; done' --reason 'Repeat prompt-bar reveal parity and loaded ACE TUI proofs after the width lookup change'

## Response

sase tool run 89643dde64358bed85352189238294da
..                                                                       [100%]
============================= slowest 20 durations =============================
3.91s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.76s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.38s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.37s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.60s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.42s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.78s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.34s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.32s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.10s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.09s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.01s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.69s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.35s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.01s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.18s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.37s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.89s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.44s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.38s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.28s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.63s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.77s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.47s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.35s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.31s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.13s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.04s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.40s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.39s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.08s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.88s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.85s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.34s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.10s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.16s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.83s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.61s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.44s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.44s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.53s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.82s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.61s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.36s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.11s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.01s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.84s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.90s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.58s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.36s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.33s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.40s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.02s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.77s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.37s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.34s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.87s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.64s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.79s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.41s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.35s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.45s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.15s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.00s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.35s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.28s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.86s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.09s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.69s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.39s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.35s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.75s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.75s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
3.40s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.37s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.01s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.78s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.57s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
3.16s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.33s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.32s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.56s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.05s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.87s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.39s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.33s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.08s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.89s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.94s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.84s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.39s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.30s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.08s
..                                                                       [100%]
============================= slowest 20 durations =============================
4.11s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.91s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.43s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.40s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.09s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 10.66s
..                                                                       [100%]
============================= slowest 20 durations =============================
3.50s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
2.77s call     tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.39s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
0.36s teardown tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
0.10s setup    tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
2 passed in 9.22s
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................................                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_queued_explicit_open_drains_on_idle_tick
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/util/pump_tasks.py:107: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    task.add_done_callback(_done)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/core/content_layout_wire.py:288: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    agent_documents=_layout_paths(raw.get("agent_documents", [])),
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_state.py::test_load_block_tail_text_missing_log_marks_pruned
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/inspect.py:272: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def isfunction(object):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
23.29s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
21.85s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
21.26s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
18.97s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
18.25s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
12.68s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
12.27s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
10.35s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
10.08s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
9.96s call     tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
9.78s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
9.65s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
9.54s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
9.53s call     tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
9.04s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
8.93s call     tests/ace/tui/test_update_restart_lifecycle.py::test_tool_run_survives_observer_stop_and_reconnect
8.70s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
8.52s call     tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
8.52s call     tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
8.30s call     tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_cancel_cleans_up_fetched_script
18624 passed, 30 warnings in 886.58s (0:14:46)
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
.................................sase completion: built command-line spec in 0.80s
....................................... [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................................                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:112: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    doc = getattr(func, "__doc__", None)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:233: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    args = (deepcopy(arg, memo) for arg in args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/main/parser_gettext.py:54: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    tuple(os.environ.get(key) for key in _GETTEXT_ENV_KEYS)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
22.17s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
17.65s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
17.12s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
14.63s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
12.60s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
10.80s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.73s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
10.67s teardown tests/ace/tui/test_startup_stopwatch_live_update.py::test_slow_mount_state_read_does_not_block_app_key_dispatch
10.36s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
10.06s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
9.22s call     tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
8.93s call     tests/ace/tui/test_update_restart_lifecycle.py::test_tool_run_survives_observer_stop_and_reconnect
8.71s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_root_reply
8.64s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
8.51s call     tests/ace/tui/test_agents_filter_bar_session.py::test_f_opens_the_bar_and_typing_previews_then_commits
8.46s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
8.40s call     tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_from_rail_is_flush_and_restores_rail
8.38s call     tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
8.36s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
8.18s call     tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
18624 passed, 30 warnings in 1092.47s (0:18:12)
bringing up nodes...
bringing up nodes...

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
................................................                         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:200: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    memo[id(x)] = y
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_lookup.py::test_queued_explicit_open_drains_on_idle_tick
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_archive_view_parking.py:203: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def flush_pending_archive_list_scroll(owner: Any) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_list_model.py::test_future_activity_folds_into_today_and_core_counts_stay_authoritative
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/pluggy/_manager.py:516: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    plugins_to_remove = {plug for plug in remove_plugins if hasattr(plug, name)}
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreenSubmissionMixin._record_local_history.<locals>._record at 0x7ff3b0163ac0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:146: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    rv = reductor(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/.venv/lib/python3.14/site-packages/textual/strip.py:600: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    add_strip(Strip(segments, cut - pos))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
23.67s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
23.11s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
17.63s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
15.30s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
13.80s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
11.48s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
11.31s call     tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
11.31s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
11.17s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
10.29s call     tests/ace/tui/test_agents_filter_bar_session.py::test_slash_opens_the_bar_and_commits_like_f
10.17s call     tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
9.99s call     tests/ace/tui/test_plan_decision_ace_render_cards.py::test_decision_cards_never_clip_with_stylesheet
9.97s call     tests/ace/tui/test_agents_filter_bar_session.py::test_filter_commit_persists_and_restores_in_fresh_session
9.97s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
9.91s call     tests/ace/tui/test_update_restart_lifecycle.py::test_tool_run_survives_observer_stop_and_reconnect
9.69s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
9.62s call     tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
9.56s call     tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
9.50s call     tests/ace/tui/test_agents_filter_bar_session.py::test_f_opens_the_bar_and_typing_previews_then_commits
9.41s call     tests/ace/tui/modals/test_memory_panel_history.py::test_no_call_from_thread_in_async_workers_under_ace_tui
18624 passed, 30 warnings in 1071.37s (0:17:51)
succeeded  exit=0  duration=3365386ms

