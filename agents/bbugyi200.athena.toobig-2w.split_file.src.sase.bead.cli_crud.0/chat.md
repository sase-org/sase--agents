# Chat History - ace-run (toobig-2w.split_file.src.sase.bead.cli_crud.0)

- **TIMESTAMP:** 2026-08-16 21:01:32 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2w.split_file.src.sase.bead.cli_crud.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260816_201801.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.bead.cli_crud.0, clan=toobig-2w)
%wait:toobig-2w.split_file.src.sase.ace.tui.actions.proc_actions.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/bead/cli_crud.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file and understanding its structure.

Now I have a clear picture. Let me create the focused modules, following the `cli_work.py` façade convention already used in this package.

Now the façade:

Now update the test patch targets to the modules that define each handler:

All modules are well under 500 lines. Now let me run the verification gate:

`src/sase/bead/cli_crud.py` (728 lines) is now a thin façade over six focused modules:

| File | Lines | Contents |
|---|---|---|
| `cli_crud.py` | 38 | Compatibility façade — re-exports every handler at the historical import path |
| `cli_crud_create.py` | 187 | `handle_bead_init`, `parse_type_arg`, `handle_bead_create` |
| `cli_crud_lifecycle.py` | 184 | `handle_bead_open`, `handle_bead_close` (+ phase-selector/gate-settle/print helpers), `handle_bead_rm` |
| `cli_crud_snooze.py` | 134 | `handle_bead_snooze`, snooze actor + result-line helpers |
| `cli_crud_update.py` | 127 | `handle_bead_update`, `--remove-by` parsing, update result printing |
| `cli_crud_evidence.py` | 121 | `handle_bead_plus_one`, `handle_bead_note` — the two attributed-evidence handlers |
| `cli_crud_common.py` | 20 | `mutation_outcome_ids`, `resolve_mutation_author` shared across the above |

Notes on the two judgement calls:

- **Handler bodies are byte-for-byte unchanged**, except that the three copies of the "acting agent, else store owner" author resolution (in `+1`, `note`, and `close`) now call the shared `resolve_mutation_author`, and `_mutation_outcome_ids` became public `mutation_outcome_ids` in the common module — symvision forbids importing a `_`-prefixed symbol across files.
- **The façade deliberately does not re-export `auto_commit_bead_store`**, so the ~25 test sites that patched `sase.bead.cli_crud.auto_commit_bead_store` would fail loudly rather than silently patch a no-op and hit the real git store. I repointed each of those to the module that now defines its handler (8 test files).

`just check` passes clean — every lint gate including `symvision` and `toobig`, plus the scoped test lane (107 files). I also ran the 11 directly affected bead CLI test files: 153 passed.

All changes are mine from this session's split. Committing now.

Committed as `4819a0314`; working tree clean and in sync with `origin/master`.

## What was done

`src/sase/bead/cli_crud.py` (728 lines) is now a 38-line façade over six focused modules:

| File | Lines | Contents |
|---|---|---|
| `cli_crud.py` | 38 | Compatibility façade — re-exports every handler at the historical import path |
| `cli_crud_create.py` | 187 | `handle_bead_init`, `parse_type_arg`, `handle_bead_create` |
| `cli_crud_lifecycle.py` | 184 | `handle_bead_open`, `handle_bead_close` (+ phase-selector/gate-settle/print helpers), `handle_bead_rm` |
| `cli_crud_snooze.py` | 134 | `handle_bead_snooze`, snooze actor + result-line helpers |
| `cli_crud_update.py` | 127 | `handle_bead_update`, `--remove-by` parsing, update result printing |
| `cli_crud_evidence.py` | 121 | `handle_bead_plus_one`, `handle_bead_note` |
| `cli_crud_common.py` | 20 | `mutation_outcome_ids`, `resolve_mutation_author` |

The façade follows the `cli_work.py` convention already used in this package, so no import sites outside the tests needed to change.

Two judgement calls worth flagging:

- **Handler bodies are unchanged** except for two consolidations the split forced: the three copies of the "acting agent, else store owner" author lookup (`+1`, `note`, `close`) now call a shared `resolve_mutation_author`, and `_mutation_outcome_ids` became public `mutation_outcome_ids` — symvision forbids importing an underscore-prefixed symbol across files.
- **The façade does not re-export `auto_commit_bead_store`.** Re-exporting it would let the ~25 tests that patch `sase.bead.cli_crud.auto_commit_bead_store` silently patch a no-op and hit the real git store. I repointed those patch targets to the module that now defines each handler instead (8 test files).

Verification: `just check` passed clean (all lint gates including symvision and toobig, plus the scoped test lane over 107 files), and the 11 directly affected bead CLI test files pass — 153 tests.

One unrelated note from the commit output: this project has **3 quarantined agent-hood publication requests** predating this commit, so the agent-hood link on it may not resolve until you run `sase agent sync --retry-quarantined`.
