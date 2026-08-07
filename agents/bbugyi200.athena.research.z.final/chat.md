# Chat History - ace-run (research.z.final)

- **TIMESTAMP:** 2026-08-07 14:07:36 EDT
- **MODEL:** claude/opus
- **AGENT:** research.z.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260807_134501.md`

## Prompt

%id(final, clan=research.z) %wait(priority=20) %m:@research_lead
%wait:research.z.cdx %wait:research.z.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to better understand and improve the way that SASE
gates are able to accept custom (i.e. defined by the user when making a command
selection for the gate) inputs/arguments for the command(s) associated with the gate
that the user decides to run. Can you do some research with these goals in mind? End
your analysis with a quick overview of how custom gate command inputs/arguments work
today followed by a ranked list of recommended improvements that you think I should
consider.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.z.cdx` -> `__a`, `research.z.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both researcher transcripts to identify their report files.

Both reports are read. `research.z.cdx` → `sase-gate-custom-command-inputs.md` (`__a`), `research.z.cld` → `gate_custom_command_inputs.md` (`__b`). Now my own research, targeting the gaps and the one real disagreement between them.

Convention confirmed. Creating the directory and moving both reports:

Both preserved (`__a` = cdx, `__b` = cld). Now the consolidated report:

Consolidated report written. Final layout in `sase/repos/research/202608/gate_input_collection/`:

- `gate_input_collection__a.md` — research.z.cdx's report
- `gate_input_collection__b.md` — research.z.cld's report
- `gate_input_collection.md` — merged

## How custom gate command inputs work today

The transport exists and is sound; **the gap is collection.** Every option carries an `input_schema`, and the executor pipes one JSON value to each selected command's **stdin**, validated first (`executor.py:84-90`). `argv` is fixed and SHA-256-hashed at creation, so user input can never reach the command line — deliberate, and correct.

What no generic surface can do is *produce* that value. ACE hardcodes `input_data={}` for the one kind you can author on the fly (`_notification_custom_gate.py:61`); the shared branch controls compose exactly one text widget, the `feedback` box. Three surfaces then apply three incompatible feedback→input rules — ACE never, mobile iff an option *id* is literally `feedback`, Telegram iff a schema's `required` lists `feedback` — so the same gate answers differently depending on where you tap it. Every kind that needs real arguments bought it with a bespoke modal, or smuggles data through free text and re-parses it host-side.

## Ranked improvements

1. **Declarative per-option `inputs:`**, rendered generically — authoring layer that compiles to `input_schema`, submitted per option
2. **Unify the feedback→input rule** in shared code (live cross-surface bug)
3. **Fail closed at creation** — add `kind_validation/custom.py`
4. **Record input-validation failures** in the bundle error log (~10 lines)
5. **`sase gate answer` CLI** + cross-surface conformance matrix
6. **Surface the submitted input** in detail pane, debug, `wait --json`
7. **Document the contract** — stdin JSON fields, never argv
8. **Migrate snooze/triage** off free-text smuggling
9. **Harden AND-branch retry** semantics
10. **Decide `edit_file`'s scope** explicitly

Non-recommendation both passes reached independently: never template user input into `argv`.

## What my pass added

Three things that changed the merged conclusions:

- **The closed vocabulary already exists.** `__a` said "reuse `SchemaObjectForm`"; `__b` said "closed vocabulary, don't render arbitrary schemas." `__b` is right on direction, but the asset it wants is the xprompt `InputArg`/`InputType` model — which already has a polished ACE renderer *and* a frozen `MobileXpromptInputWire` record. ACE currently carries three non-interoperating form systems (~1,850 lines); this would be a fourth. (`InputType` lacks an `enum` member, and Telegram doesn't render xprompt inputs yet — real gaps, but far cheaper than starting over.)
- **Their ranking conflict was illusory.** `__a` put per-option submission at #1, `__b` at #5. Since `inputs:` is *declared* per option, its natural submission shape *is* per option — one decision, not two. Splitting them means designing the wire twice.
- **The mobile path is four layers across two repos and contract-frozen.** Neither traced it: app → `sase_gateway` (Rust) → host bridge → Python. `GateActionRequestWire` lives in `mobile_api_v1.json` with a freeze test (`contract.rs:947`). Per this repo's own Rust Core Backend Boundary rule, the submission contract belongs in `sase-core` — which materially prices recommendation #1.

I also confirmed `__a`'s unique non-transactional finding (`response.json` writes only after *all* options succeed, so a mid-branch failure leaves the gate answerable with side effects already applied) and `__b`'s unique error-log finding (validation raises before the `try` that records errors, so `d` shows nothing).

The sidecar has two staged renames and one untracked file — I didn't commit since you didn't ask. Say the word and I'll run the commit skill.

The final layout is in place. Committing it now.

Committed. The tree is clean and `main` is in sync with `origin/main`.

## What I did

**Commit `cb52932` — `docs(research): consolidate custom gate command input research`** in the research repo (the linked repo and the SDD sidecar are the same checkout, so one commit covered both listings):

- `202608/gate_input_collection/gate_input_collection__a.md` — research.z.cdx's report (pure rename from `sase-gate-custom-command-inputs.md`)
- `202608/gate_input_collection/gate_input_collection__b.md` — research.z.cld's report (pure rename from `gate_custom_command_inputs.md`)
- `202608/gate_input_collection/gate_input_collection.md` — the consolidated report, 510 lines

The first attempt failed because I passed the pre-rename paths as `-f` targets; the renames were already staged, so those pathspecs no longer resolved. Re-ran with the three current paths and the same preserved message file.

Two non-fatal warnings from the post-commit bookkeeping: prompt-archive publication and agent-hood publication were both deferred because the agents sync lock was busy. Both are queued to retry automatically — the primary commit and push completed.

## The report itself

Findings stand as summarized before: the input **transport** is sound (per-option `input_schema`, one validated JSON value piped to each command's stdin, `argv` fixed and SHA-256-hashed at creation), and the gap is **collection** — no generic surface can produce that value, so ACE hardcodes `input_data={}` and three surfaces apply three incompatible feedback→input rules. Ranked recommendations lead with a declarative per-option `inputs:` block rendered through the existing xprompt `InputArg`/`InputType` model, then unifying the feedback rule, then failing closed at gate creation.
