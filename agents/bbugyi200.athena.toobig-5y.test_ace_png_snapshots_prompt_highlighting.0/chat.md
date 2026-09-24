# Chat History - ace-run (toobig-5y.test_ace_png_snapshots_prompt_highlighting.0)

- **TIMESTAMP:** 2026-09-23 21:15:39 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.test_ace_png_snapshots_prompt_highlighting.0

## Prompt

%id(test_ace_png_snapshots_prompt_highlighting.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py` file up into multiple files? Use your best
%wait:toobig-5y.test_plugins_browser_rows.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 735-line `test_ace_png_snapshots_prompt_highlighting.py` into three thematic files (original deleted), all under 500 lines:

- [test_ace_png_snapshots_prompt_highlighting_markdown.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_markdown.py) — 256 lines: TODO restored/stack, bullet, ordered, placeholder raw-only, codeblock solo/stack.
- [test_ace_png_snapshots_prompt_highlighting_search.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_search.py) — 149 lines: active search highlight, search count pill, misspelling.
- [test_ace_png_snapshots_prompt_highlighting_refs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting_refs.py) — 368 lines: xprompt solo/stack/arguments, project tags, artifact refs, glossary + wrapped glossary, repo mentions.

Test bodies are verbatim copies; each file imports only the fixtures, helpers, and prompt constants its tests use. All 18 test functions (29 cases) collect cleanly with `-m visual`.

Verification: `just fmt` clean; `sase tool run check` passes fmt, keep-sorted, ruff, mypy, feature flags, pyscripts, test-waits, changelog, and terminology gates. One caveat: the `symvision` gate fails, but it scans only `src/sase` (untouched by this change) with zero mentions of the new files, so that failure is pre-existing and unrelated.
