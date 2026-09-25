# Chat History - ace-run (0am--code)

- **TIMESTAMP:** 2026-08-22 13:12:01 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** 0am--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0am__plan-260822_120315.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0am__code-260822_120315.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase @sase/repos/plans/202608/move_final_declaration_to_memory.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement the approved plan to move final-declaration guidance into generated memory. First I'll load the relevant skills and inspect the current injection path.

I'll load the long-term memory notes and the current injection code so the change stays aligned with the existing finalizer flow.

Next I’ll inspect the template, declaration helper, and invoke path so the move is a drop-in replacement rather than a rewrite.

I’ll update the template and drop the per-query append, then adjust tests and docs to match the new source of truth.

Next I’ll retarget the tests and docs so they expect the declaration in generated memory, not in the provider prompt.

Install finished. I’ll preview the memory-init diff, then regenerate with `--no-commit`.

The planned diff is only the declaration section plus matching README stats. Regenerating with the workspace `sase`.

Focused tests passed. Next I’ll format, then run the repo-wide `just check` gate.

`just check` escalated to the full suite; I’ll inspect the failures to see which ones our change actually caused.

Implemented the approved plan: `/sase_final` now comes from generated agent instructions, not from appending a block onto every provider prompt.

**Instruction source.** The packaged `memory-sase.template.md` now has a `SASE Final Declaration` section (outside the project-name conditional). `sase memory init --no-commit` regenerated `sase/memory/sase.md`, `AGENTS.md`, and the provider shims. Home instructions received the same section.

**Prompt path.** `append_finalizer_end_turn_instructions()` is gone. Invocation still persists the finalizer plan, projects metadata, mints the turn nonce, and runs the controller/recovery flow. The provider query and saved prompt stay the preprocessed user text.

**Recovery.** A missing or stale required declaration still gets one recovery turn that tells the agent to use `/sase_final`. Clean contexts and intentional handoffs still skip that turn.

**Tests and docs.** Prompt-injection assertions now check that the processed prompt is unchanged. Memory init checks that project and home notes plus shims carry the contract; a custom `memory.sase_template` still replaces that prose. Docs in `init.md`, `memory.md`, `llms.md`, `commit_workflows.md`, and `configuration.md` match the new source and fallback model.

**Verification.** Focused tests passed (65). `sase memory init --check` is clean. Lint gates passed. The first `just check` escalated after `just install` rebuilt `sase_core_rs` and ran the full suite; a second run selected 4,282 tests and passed 4,281. The only failure is the known xdist path-truncation flake `tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift` (serial rerun passed). That was corroborated on `sase-rv` (+14). Missing `.venv/bin/sase-xprompt-lsp` after `just install` was noted on epic `sase-s1` (phases `sase-s1.1` / `sase-s1.2`).
