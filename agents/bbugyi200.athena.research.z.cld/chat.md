# Chat History - ace-run (research.z.cld)

- **TIMESTAMP:** 2026-08-07 13:55:42 EDT
- **MODEL:** claude/opus
- **AGENT:** research.z.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260807_134501.md`

## Prompt

%id(cld, clan=research.z) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to better understand and improve the way that SASE
gates are able to accept custom (i.e. defined by the user when making a command
selection for the gate) inputs/arguments for the command(s) associated with the gate
that the user decides to run. Can you do some research with these goals in mind? End
your analysis with a quick overview of how custom gate command inputs/arguments work
today followed by a ranked list of recommended improvements that you think I should
consider. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research how SASE gates handle custom command inputs/arguments. Let me start by exploring the gate implementation.

Research complete. Writing the report.

Research written to `sase/repos/research/202608/gate_custom_command_inputs.md`.

## How custom gate command inputs work today

Every gate option already carries an `input_schema`, and the shared executor pipes one JSON value to each selected command's **stdin**, validated against that schema (`notification_gates/executor.py:84-90`, `:391-437`). Command `argv` is fixed and hashed at creation — user input never reaches the command line, by design.

What's missing is collection. The one gate kind you can author on the fly, `kind: "custom"`, has **no input path at all**: ACE hardcodes `input_data={}` (`_notification_custom_gate.py:61`), and the shared branch controls compose exactly one text widget — the `feedback` box (`gate_branch_controls.py:162-163`). That note goes into `response.json` and `sase gate wait --json`, so the producing agent sees it, but the reviewed command never does.

Three findings worth flagging:

- **A custom gate with a required input field is accepted at creation and permanently unanswerable from ACE.** Nothing validates it (there is no `kind_validation/custom.py`), and the failure raises before the error-recording block, so `d` shows nothing. It hasn't bitten because the skill's example and every fixture use the permissive `{"type": "object"}`.
- **Three surfaces, three incompatible feedback→input rules.** ACE never copies it; mobile copies it iff the option *id* is literally `"feedback"`; Telegram copies it iff `input_schema.required` contains `"feedback"`. The same gate answers differently depending on where you tap it.
- **Every kind that needs a real argument paid for it with a bespoke modal** — plan's `coder_prompt`/model picker, the 654-line question form, HITL's dict — plus matching hardcoded routes on mobile and Telegram. Snooze/triage instead smuggle durations through the free-text field and re-parse host-side; `adapters.py:218-238` documents that compromise in its own docstring.

## Ranked recommendations

1. **Declarative `inputs:` on gate options**, rendered generically by `GateBranchControls` — a closed widget vocabulary that *compiles to* `input_schema` rather than a general schema-to-form renderer. This is the headline fix.
2. **Unify the feedback→input rule** across all three surfaces (lift Telegram's schema-inspection into shared Python). Cheap, fixes a live bug, prerequisite for #1.
3. **Fail closed at creation** — reject gates whose schema can't accept what clients can produce.
4. **`sase gate answer` CLI** — headless escape hatch; nothing currently tests a non-trivial `input_schema`.
5. Per-option input instead of one shared blob (removes the AND-branch workaround `plan_gate.py:559-571` comments on).
6. Record input-validation failures in the bundle error log.
7. Surface `input` in the detail pane, debug view, and `wait --json`.
8. Migrate snooze/triage off free-text smuggling once #1 lands.
9. Document the contract — arguments are stdin JSON fields, never argv.
10. Decide `edit_file`'s scope explicitly (today silently accepted, silently ignored for non-plan kinds).

One explicit non-recommendation: don't template user input into `argv` — that would break the hashed-command trust model.

I held off on filing beads since the ranked list is yours to triage; say the word and I'll run `/sase_new_task` for whichever items you want tracked (items 2, 3, and 6 are the ones I'd call defects rather than enhancements).

The file is complete. Committing it now via the commit skill.

Committed. The research repo is clean and level with `origin/main` — no divergence marker after `main...origin/main`, so the push landed.

**Commit:** `8174817 docs(research): analyze custom input handling for notification gates`

The single file committed was `202608/gate_custom_command_inputs.md` (321 lines), the report on how gates accept custom command inputs today plus the ranked improvement list. Both finalizer entries pointed at the same path — the linked repo and the SDD sidecar resolve to the same checkout — so one commit covered both.

One non-blocking warning from the commit: prompt-archive/agent-hood publication was deferred because the agents sync lock was busy. The primary commit succeeded and publication retries automatically.
