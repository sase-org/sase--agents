# Chat History - ace-run (toobig-5r.test_memory_selector_render.0)

- **TIMESTAMP:** 2026-09-22 00:03:33 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_memory_selector_render.0

## Prompt

%id(test_memory_selector_render.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/memory/test_memory_selector_render.py` file up into multiple files? Use your best
%wait:toobig-5r.test_repo_handler_open_configured.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 959-line file into 3 files, all <=500 lines, with no test changes.

- Deleted [test_memory_selector_render.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/memory/test_memory_selector_render.py)
- Created [test_memory_selector_render_batch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/memory/test_memory_selector_render_batch.py) (325 lines, 9 tests: batch labeling, children suppression, linked refs)
- Created [test_memory_selector_render_inline.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/memory/test_memory_selector_render_inline.py) (312 lines, 10 tests: inline notes, depth/truncation, shared bodies)
- Created [test_memory_selector_render_webs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/memory/test_memory_selector_render_webs.py) (465 lines, 15 tests: web sections, JSON/rich payloads, supersession)

Each new file is self-contained with only the helpers it needs, matching the existing duplicate-helper style in `tests/memory/`. Verified all 34 test names match the original set exactly.

Verified with `sase tool run check` (succeeded, including ruff/mypy/symvision/toobig + scoped tests) and direct pytest: 34 passed across the 3 new files.
