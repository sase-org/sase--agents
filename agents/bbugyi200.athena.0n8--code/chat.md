# Chat History - ace-run (0n8--code)

- **TIMESTAMP:** 2026-09-18 16:09:44 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0n8--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/ctrl_g_completion_selection.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by reading the implementation-plan skill and locating the approved plan in the plans sidecar.

This is an approved SASE tale, not a PR DAG. Next I’ll open the plans sidecar and read the plan.

Plans sidecar is registered. I’ll open it and read the approved plan next.

Plans sidecar is open. I’ll read the plan as an audited artifact and pull the lint/test plus TUI notes.

The plan is a prompt-widget keymap change. I’ll load TUI performance notes and map the current completion-acceptance path.

I’ll read the completion docs and the tests that currently treat Enter as accept.

I have the contract. Next I’ll change the key dispatcher, then migrate hints, tests, and docs.

Source hints are updated. I’ll align `docs/ace.md` with the new Ctrl+G / Enter contract next.

Docs are updated. Next I’ll convert the interaction tests from Enter-accept to Ctrl+G, and add the Enter-submits regressions.

I’ll run the focused prompt-widget tests first, then inspect and update any visual goldens that change.

The failing tests stubbed `action_submit_prompt` and skipped the real clear. I’ll wrap the original submit so the menu still dismisses.

Header-only diffs are the AXE vs Services tab label, not our key text. I’ll update only the alias and explicit snapshots that actually show Ctrl+G.

Prompt completion now uses **Ctrl+G** to accept a highlighted row. **Enter** always submits the typed prompt.

**Behavior**
- With a completion menu open in INSERT mode, **Ctrl+G** accepts the highlighted candidate, including the first row that was never navigated to.
- **Enter** submits the unexpanded text, or opens the existing stack/target chooser. It never inserts a candidate.
- **Ctrl+L** still accepts both manual-menu and soft subtitle completions.
- With no menu open, **Ctrl+G** still starts the prompt-local `Ctrl+G ...` prefix.

**Also updated**
- Completion hints (`[Ctrl+G] accept alias/model`, `Ctrl+G → %m:...`, provider drill-down).
- `docs/ace.md` completion key table and automatic-menu notes.
- Interaction tests for file, xprompt, argument, placeholder, word, history-word, and model providers, plus Enter-submits and first-row Ctrl+G regressions.
- Alias and explicit-model PNG goldens whose key text changed.

Lint passed. Focused prompt-widget tests and the updated visual snapshots passed. `just check` escalated to the full suite after a `sase-core-rs` install and reported 14 unrelated SDD sidecar-clone failures; none were in the completion tests.
