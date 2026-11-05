# Chat History - ace-run (sase-1ra.6--mon)

- **TIMESTAMP:** 2026-11-04 19:05:25 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1ra.6--mon

## Prompt

sase monitor start --command 'ssh apollo /tmp/sase-1ra6-20261104-1730/run.sh && sase tool run check' --reason 'Run the Apollo command-line panel pilot matrix and verify this checkout'

## Response

sase tool run 005fc0dc71fe831673e9523a8e622cee
Apollo host: apollo
Scratch base commit: 0cc9fad474e83e9993a0771a083879e34c398e84 plus the submitted test patch
Using CPython 3.12.13
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
Resolved 98 packages in 559ms
   Building sase @ file:///tmp/sase-1ra6-20261104-1730
Downloading virtualenv (5.4MiB)
 Downloaded virtualenv
      Built sase @ file:///tmp/sase-1ra6-20261104-1730
Prepared 11 packages in 1.28s
Installed 98 packages in 115ms
 + ast-serialize==0.13.1
 + asttokens==3.0.2
 + attrs==26.1.0
 + bracex==3.2.1
 + build==1.6.1
 + cachetools==7.2.8
 + certifi==2026.10.23
 + cffi==2.1.1
 + charset-normalizer==3.5.2
 + colorama==0.4.6
 + coverage==7.17.2
 + cryptography==50.0.2
 + distlib==0.4.4
 + docutils==0.23
 + execnet==2.1.2
 + executing==2.3.0
 + filelock==4.2.9
 + hypothesis==6.170.14
 + id==1.6.1
 + idna==3.20
 + iniconfig==2.3.1
 + inline-snapshot==0.36.1
 + jaraco-classes==3.4.0
 + jaraco-context==6.1.2
 + jaraco-functools==4.6.0
 + jeepney==0.9.0
 + jinja2==3.1.6
 + jsonschema==4.26.0
 + jsonschema-specifications==2025.9.1
 + keyring==25.7.0
 + librt==0.16.0
 + linkify-it-py==2.2.0
 + markdown-it-py==4.2.0
 + markupsafe==3.0.4
 + mdit-py-plugins==0.6.1
 + mdurl==0.1.2
 + more-itertools==11.2.1
 + mypy==2.4.1
 + mypy-extensions==1.2.0
 + nh3==0.3.7
 + packaging==26.3
 + pathspec==1.1.1
 + pillow==13.0.0
 + platformdirs==4.14.5
 + pluggy==1.7.0
 + pycparser==3.12
 + pygments==2.19.2
 + pyinstrument==5.1.3
 + pyproject-api==1.12.4
 + pyproject-hooks==1.3.3
 + pytest==9.2.0
 + pytest-asyncio==1.4.1.post1
 + pytest-cov==7.1.0
 + pytest-mock==3.17.0
 + pytest-xdist==3.8.0
 + python-discovery==1.9.4
 + pyyaml==6.0.3
 + readme-renderer==46.0
 + referencing==0.37.0
 + requests==2.34.2
 + requests-toolbelt==1.0.0
 + resvg-py==0.3.3
 + rfc3986==2.0.0
 + rich==15.0.0
 + rpds-py==2026.9.1
 + ruamel-yaml==0.19.1
 + ruff==0.17.3
 + sase==0.18.1 (from file:///tmp/sase-1ra6-20261104-1730)
 + sase-core-rs==0.43.3 (from file:///tmp/sase-1ra6-20261104-1730/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
 + schedule==1.2.2
 + secretstorage==3.5.0
 + sortedcontainers==2.4.0
 + symvision==0.1.0
 + textual==8.0.1
 + tomli-w==1.2.0
 + toobig==0.1.0
 + tox==4.67.10
 + tree-sitter==0.26.0
 + tree-sitter-bash==0.25.1
 + tree-sitter-css==0.25.0
 + tree-sitter-go==0.25.0
 + tree-sitter-html==0.23.2
 + tree-sitter-java==0.23.5
 + tree-sitter-javascript==0.25.0
 + tree-sitter-json==0.24.8
 + tree-sitter-markdown==0.5.4
 + tree-sitter-python==0.25.0
 + tree-sitter-regex==0.25.0
 + tree-sitter-rust==0.24.2
 + tree-sitter-sql==0.3.11
 + tree-sitter-toml==0.7.0
 + tree-sitter-xml==0.7.0
 + tree-sitter-yaml==0.7.2
 + twine==7.0.0
 + typing-extensions==4.16.0
 + urllib3==2.8.0
 + virtualenv==21.15.5
 + wcmatch==12.0
Python 3.12.13
sase_core_rs imported
RUN serial-1: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
7.86s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
5.25s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.68s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
1.56s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 24.52s
RUN serial-2: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.61s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.75s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.12s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 21.45s
RUN serial-3: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.19s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
1.03s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.09s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.02s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
3 passed in 23.98s
RUN serial-4: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.58s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
5.15s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.69s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.74s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.05s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.05s
RUN serial-5: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
7.27s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
5.00s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.66s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.98s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.89s
RUN serial-6: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.75s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.32s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.72s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.09s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 19.03s
RUN serial-7: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.43s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
5.74s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.86s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.73s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.10s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 21.02s
RUN serial-8: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.46s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.33s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.91s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 21.59s
RUN serial-9: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
1.27s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.04s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.98s
RUN serial-10: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
1.06s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.08s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(1 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 22.15s
RUN serial-11: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.44s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.38s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.69s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.07s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 19.94s
RUN serial-12: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.87s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.75s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.08s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back

(2 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.46s
RUN serial-13: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.65s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
4.97s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.45s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.82s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 19.90s
RUN serial-14: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.64s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.20s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.74s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 18.66s
RUN serial-15: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.12s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.14s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.75s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.08s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 19.50s
RUN serial-16: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.27s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.96s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
4.34s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.71s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.08s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.50s
RUN serial-17: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.73s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
4.71s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.34s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.76s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.04s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 19.35s
RUN serial-18: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.34s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
5.08s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
4.26s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.76s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.10s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen

(4 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 20.00s
RUN serial-19: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
6.10s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
1.06s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.06s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.01s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
3 passed in 25.54s
RUN serial-20: .venv/bin/pytest -q -p no:cacheprovider -n 0 tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.99s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
5.07s call     tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
0.73s setup    tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_semicolon_hops_to_palette_and_back
0.08s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_panel_escape_keeps_draft_across_reopen
0.01s teardown tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding

(3 durations < 0.005s hidden.  Use -vv to show these durations.)
3 passed in 22.99s
PASS: pilot trio passed 20 serial iterations
RUN tui-xdist-1: .venv/bin/pytest -q -p no:cacheprovider -n 8 tests/ace/tui/
  /tmp/sase-1ra6-20261104-1730/tests/ace/tui/_agent_archive_column_helpers.py:179: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    def __init__(self) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /tmp/sase-1ra6-20261104-1730/tests/ace/tui/_agent_archive_column_helpers.py:49: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    "last_activity_at": f"{day}T{hour:02d}:00:00Z",
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /tmp/sase-1ra6-20261104-1730/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:933: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    @property
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_early_open_paints_loading_and_queues_until_gate
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/_weakrefset.py:88: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    self.data.add(ref(item, self._remove))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /tmp/sase-1ra6-20261104-1730/src/sase/config/loading.py:92: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /tmp/sase-1ra6-20261104-1730/src/sase/ace/tui/keymaps/key_validation.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    return tuple(part.strip() for part in key.split(","))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /tmp/sase-1ra6-20261104-1730/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /tmp/sase-1ra6-20261104-1730/.venv/lib/python3.12/site-packages/textual/strip.py:110: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    ] = FIFOCache(4)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_proc_submit_captures_confirm_flags
  /tmp/sase-1ra6-20261104-1730/.venv/lib/python3.12/site-packages/textual/strip.py:101: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    self._style_cache: FIFOCache[Style, Strip] = FIFOCache(16)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:176: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    def _select_from(self, parent_path, scandir):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/copy.py:118: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /tmp/sase-1ra6-20261104-1730/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
69.81s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
51.68s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
31.90s call     tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
29.74s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
27.68s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
26.13s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
19.57s call     tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
19.44s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
19.05s call     tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
18.94s call     tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
18.03s call     tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
17.73s call     tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
17.35s call     tests/ace/tui/modals/test_agent_action_chooser_modal.py::test_chooser_direct_keys_select_rows
17.10s call     tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
16.19s call     tests/ace/tui/test_agent_archive_shelf_panel_cycle.py::test_jk_wrap_tribe_panels_past_the_visible_archive_shelf
15.88s call     tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
15.83s call     tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
15.34s call     tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
14.92s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
14.76s call     tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
=========================== short test summary info ============================
FAILED tests/ace/tui/modals/test_prompt_history_modal_project_filter.py::test_project_filter_matches_complete_identity_not_prefix_or_prose
FAILED tests/ace/tui/modals/test_prompt_history_modal_project_filter.py::test_project_and_text_filter_combine_with_and
FAILED tests/ace/tui/modals/test_prompt_history_modal_project_filter.py::test_alias_equivalent_rows_match_by_canonical_key
FAILED tests/ace/tui/modals/test_prompt_history_modal_project_filter.py::test_unresolved_project_value_matches_raw_historical_ref
FAILED tests/ace/tui/modals/test_prompt_history_modal_project_filter.py::test_clearing_project_filter_restores_full_results
FAILED tests/ace/tui/test_agent_completion_prompt.py::test_workflow_from_tag_prompt_resolves_project
FAILED tests/ace/tui/test_agent_completion_prompt.py::test_raw_tag_for_tag_prompt_returns_canonical_ref
FAILED tests/ace/tui/test_agent_completion_prompt.py::test_ref_prompts_still_resolve_when_catalog_is_cold
FAILED tests/ace/tui/test_launch_submit_vcs_replay.py::test_submit_refreshes_replay_from_cycled_vcs_prefix
FAILED tests/ace/tui/test_launchable_mru.py::test_warm_identity_resolves_aliased_project
FAILED tests/ace/tui/test_launchable_mru.py::test_cold_identity_project_falls_back_to_global_namespace
FAILED tests/ace/tui/test_launchable_mru.py::test_bare_host_without_hook_canonicalizes_synchronously
FAILED tests/ace/tui/test_pending_launch.py::test_submit_time_vcs_replay_is_recorded_off_the_ui_thread
FAILED tests/ace/tui/util/test_pane_grid_properties.py::test_outputs_stay_valid
FAILED tests/ace/tui/widgets/test_agent_display_tribe_prompts.py::test_digest_project_ignores_patch_unknown_and_cold
FAILED tests/ace/tui/widgets/test_agent_tribe_prompts.py::test_split_preamble_strips_frontmatter_directives_and_vcs_tag
FAILED tests/ace/tui/widgets/test_agent_tribe_prompts.py::test_split_preamble_keeps_vcs_tag_between_directive_runs
FAILED tests/ace/tui/widgets/test_agent_tribe_prompts.py::test_prompt_snippet_outputs_are_unchanged
FAILED tests/ace/tui/widgets/test_agent_tribe_prompts.py::test_same_body_in_different_projects_does_not_coalesce
19 failed, 18639 passed, 29 skipped, 29 warnings in 1798.17s (0:29:58)
failed  exit=1  duration=2412022ms

