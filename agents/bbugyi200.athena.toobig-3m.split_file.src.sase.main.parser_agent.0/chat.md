# Chat History - ace-run (toobig-3m.split_file.src.sase.main.parser_agent.0)

- **TIMESTAMP:** 2026-08-23 16:56:59 EDT
- **MODEL:** claude/sonnet
- **AGENT:** toobig-3m.split_file.src.sase.main.parser_agent.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260823_160129.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.main.parser_agent.0, clan=toobig-3m)
%model:@medium
%wait:toobig-3m.split_file.src.sase.ace.tui.widgets._agent_list_render_agent.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/main/parser_agent.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file to understand its structure.

Now I'll check the `__all__`/exports convention and existing docstring style for a couple more reference files, then write the split.

Now the storage file (archive, artifacts, index, names):

Now the prompts file (with the two helper functions) and the tribe file:

Now rewrite the main `parser_agent.py` to delegate to these:

Now let's verify line counts and check for correctness — diff the generated argparse structure against the original to make sure nothing changed.

The only diffs are function object memory addresses (different `_prompt_archive_month` instances, as expected since they're now in a different module) — the full argparse tree (subcommands, arguments, help text, defaults, choices, nargs) is otherwise identical. The split is behavior-preserving.

Now let's run lint and the test suite to confirm everything works:

I'll wait for `just install` to finish in the background, then run `just check`.

All six files compile cleanly and I've already verified the resulting argparse structure is byte-for-byte identical to the original (aside from harmless function-object identity). `just install` is still running in the background — I'll run `just check` once it completes.

I split `parser_agent.py` (740 lines) into:
- `parser_agent.py` (59 lines) — top-level registrar that delegates to the rest
- `parser_agent_lifecycle.py` (203 lines) — list, kill, show, restart, wait
- `parser_agent_sync.py` (119 lines) — retire-v1, sync
- `parser_agent_storage.py` (268 lines) — archive, artifacts, index, names
- `parser_agent_prompts.py` (123 lines) — prompts + its helper functions
- `parser_agent_tribe.py` (56 lines) — tribe

This follows the same `parser_<cmd>.py` + `parser_<cmd>_<topic>.py` delegation pattern already used for `parser_bead.py`. All files are well under 500 lines.

`just install` is still running (likely rebuilding the venv/deps). I'll wait for it to complete and get notified automatically.

`just install` finished successfully. Now running `just check` per project convention.

`just check` is running in the background — I'll be notified when it finishes.

`just check` passed cleanly (exit code 0) — all lint gates (fmt, ruff, mypy, symvision, toobig, keep-sorted, etc.) and the scoped test run succeeded. The `core-floor-probe` warning is pre-existing infra noise about the `sase-core-rs` version floor, unrelated to this change.

`src/sase/main/parser_agent.py` (740 lines) is now split into six files, all under 500 lines, following the same delegation pattern already used by `parser_bead.py`:

- **`parser_agent.py`** (59 lines) — top-level `register_agent_parser`, delegates to the rest, preserving the original registration order
- **`parser_agent_lifecycle.py`** (203 lines) — `list`, `kill`, `show`, `restart`, `wait`
- **`parser_agent_sync.py`** (119 lines) — `retire-v1`, `sync`
- **`parser_agent_storage.py`** (268 lines) — `archive`, `artifacts`, `index`, `names`
- **`parser_agent_prompts.py`** (123 lines) — `prompts` + its two helper functions
- **`parser_agent_tribe.py`** (56 lines) — `tribe`

I verified the split is behavior-preserving by building the full argparse tree from both the old and new code and diffing every subcommand, argument, help string, default, and type — identical except for harmless function-object identity. `just check` then passed clean (all lint gates + scoped tests, exit 0). Nothing else in the repo imports the private helpers or split-out symbols, only the public `register_agent_parser`, so no other files needed changes.

Submission is required for a `commit` decision on the `main` repository. I'll build the manifest with a Conventional Commit message reflecting the file split work.

The declaration was accepted for the commit finalizer.

I've split `src/sase/main/parser_agent.py` (740 lines) into six files, all under 500 lines, following the same delegation pattern used by `parser_bead.py`:

- **`parser_agent.py`** (59 lines) — top-level registrar
- **`parser_agent_lifecycle.py`** (203 lines) — list, kill, show, restart, wait
- **`parser_agent_sync.py`** (119 lines) — retire-v1, sync
- **`parser_agent_storage.py`** (268 lines) — archive, artifacts, index, names
- **`parser_agent_prompts.py`** (123 lines) — prompts + helpers
- **`parser_agent_tribe.py`** (56 lines) — tribe

The argparse tree was verified identical before/after, `just check` passed clean, and the commit has been submitted via the finalizer.
