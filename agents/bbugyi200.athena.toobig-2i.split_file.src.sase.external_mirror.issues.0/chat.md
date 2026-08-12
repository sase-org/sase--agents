# Chat History - ace-run (toobig-2i.split_file.src.sase.external_mirror.issues.0)

- **TIMESTAMP:** 2026-08-12 17:10:09 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-2i.split_file.src.sase.external_mirror.issues.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260812_161224.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.external_mirror.issues.0, clan=toobig-2i)
%wait:toobig-2i.split_file.src.sase.bead.cli_query.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/external_mirror/issues.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I’ll map the module’s responsibilities and imports first, then split it along cohesive boundaries while preserving its public API. Afterward I’ll run the repository’s required install/check workflow and tighten any compatibility issues the tests expose.

The module has three clean seams: orchestration/state checkpointing, reconciliation planning, and locked mutation application. I’m keeping `issues.py` as the stable public entry point (including its current patchable provider/store seams), and moving only internal models, planning logic, and application logic into private sibling modules.

The split is now in place: the public module is 288 lines, and each extracted module is under 250 lines. I’m checking static types and the existing monkeypatch-based test seams now; those are the main regression risk in a structural refactor like this.

The focused reconciliation, chop, and CLI suites all pass (42 tests), and the extracted modules type-check cleanly. The existing `sase.external_mirror.issues` imports and test patch points remain intact; I’m moving on to the repository-wide required verification.

The required install step is rebuilding the linked Rust core for this fresh workspace and is still progressing; no errors so far. Once it finishes, the final `just check` will exercise the whole-repo lint gates plus the diff-selected tests.

`just check` found one formatter-only issue in an extracted function signature; there are no semantic failures in that run. I’m applying the exact Ruff formatting change and rerunning the full check.

All required gates now pass, including formatting, Ruff, mypy, Symvision, the file-size gate, SASE validation, and 106 diff-selected test files. I’m doing a final diff review for accidental API or workspace changes before handing it back.

Split complete, with all files under 500 lines:

- [issues.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/external_mirror/issues.py) — 284 lines; public API and orchestration
- [_issue_models.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/external_mirror/_issue_models.py) — 95 lines; reports, budgets, candidates
- [_issue_planning.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/external_mirror/_issue_planning.py) — 216 lines; reconciliation planning
- [_issue_apply.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/external_mirror/_issue_apply.py) — 175 lines; locked bead mutations

Existing imports and test monkeypatch seams remain compatible.

Verification passed:

- 42 focused tests
- `just check`, including all lint/type gates and 106 scoped test files

The refactor is complete and verified; the finalizer requires committing these four files now. I’m using the `sase_git_commit` skill to create the commit through the repository’s required stitch workflow.

The commit scope is clean: it contains only the intended structural refactor, preserves `issues.py` as the public entry point, and moves models, planning, and mutation application into three cohesive private modules. All four files are below 500 lines.

Committed the completed refactor as `bd854998a` (`refactor: split external issue mirror module`).

All four files are under 500 lines, required checks passed, and the working tree is clean and synced.
