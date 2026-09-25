- **PLAN:**
  [202609/agents_deck_picker_other_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_deck_picker_other_panel.md)
- **AGENTS:**
  - [bbugyi200.apollo.1p.f0--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1p.f0.md)

%xprompts_enabled:false

# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first
projections of exact continuation nodes; any historical source without recoverable node
provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `3`

## Continuation Block `block:v1:cfb1b77da7c3e8e1c7d64174061c2790`

- **Node:** `legacy-boundary:20260925100044:641f55ad36f06627`
- **Kind:** `legacy_boundary`
- **Parents:** (none)
- **Content:** `compat:legacy-boundary:641f55ad36f06627`

### Opaque Legacy Boundary

This source lacks recoverable continuation node provenance, so replay does not guess
transcript turns from Markdown headings.

- **Source:** agent session `1p` member `1p--plan`
- **Reason:** source lacks a recoverable continuation node
- **Transcript:**
  `~/.sase/chats/202609/gh_sase_org__sase-ace_run-1p__plan-260925_100044.md`

### Protected Legacy Content

**Protected.** This opaque snapshot is included within budget and is not reconstructed
into guessed local turns.

```text
# Chat History - ace-run (1p--plan)

- **TIMESTAMP:** 2026-09-25 10:10:44 EDT
- **MODEL:** claude/opus
- **AGENT:** 1p--plan

## Prompt

#gh:gh_sase-org__sase Can you help me add a new `p` keymap to the "Agents" tab that triggers a panel
which allows the user to select which deck to display in the current deck panel with a
single keypress? This will sometimes be faster than using the `<ctrl+n/p>` keymaps to
cycle between decks (especially when we add more decks in the future). I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:opus@xhigh

## Response

# Gate handoff

This agent handed the remaining decision to a gate shell.
Decision: Tale ready for review: agents_deck_picker.md
Gate ID: 0ceebf59-d8ec-422e-8c1b-aaa857f22f1d
Inspect with: sase gate show --id 0ceebf59-d8ec-422e-8c1b-aaa857f22f1d --kind plan
Gate shell: 1p--gate


```

## Continuation Block `block:v1:4079262bcbaabcc8e4f44b3ed8ce3e6d`

- **Node:** `legacy-boundary:20260925101043:d96758c579c30a76`
- **Kind:** `legacy_boundary`
- **Parents:** (none)
- **Content:** `compat:legacy-boundary:d96758c579c30a76`

### Opaque Legacy Boundary

This source lacks recoverable continuation node provenance, so replay does not guess
transcript turns from Markdown headings.

- **Source:** agent session `1p` member `1p--gate`
- **Reason:** source lacks a recoverable continuation node
- **Transcript:**
  `~/.sase/chats/202609/gh_sase_org__sase-ace_run-1p__gate-20260925101043.md`

### Protected Legacy Content

**Protected.** This opaque snapshot is included within budget and is not reconstructed
into guessed local turns.

````text
# Chat History - ace-run (1p--gate)

- **TIMESTAMP:** 2026-09-25 10:12:44 EDT
- **MODEL:** claude/opus
- **AGENT:** 1p--gate

## Prompt

sase gate answer --id 0ceebf59-d8ec-422e-8c1b-aaa857f22f1d --kind plan

## Response

# Tale ready for review: agents_deck_picker.md

Gate state: answered
Reason: gate answered
Selected options: approve, commit

Branches:

- [x] Launch coder agent + Commit plan file to the plans sidecar (approve+commit)
- [ ] Reject (reject)
- [ ] Send Feedback (feedback)

Option results:

[
  {
    "id": "approve",
    "result": {
      "action": "approve",
      "commit_plan": true,
      "plan_archive_owner": "host",
      "plan_archive_protocol": "host_v2",
      "plan_archive_ref": "plan:202609/agents_deck_picker.md",
      "plan_archive_state": "archived",
      "run_coder": true,
      "saved_plan_path": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/plans/202609/agents_deck_picker.md"
    }
  },
  {
    "id": "commit",
    "result": {
      "action": "approve",
      "commit_plan": true,
      "run_coder": false
    }
  }
]

Output tail:

```text
$ commands/approve
{"action": "approve", "commit_plan": false, "run_coder": true}
$ commands/commit
{"action": "approve", "commit_plan": true, "run_coder": false}
```


````

## Continuation Block `block:v1:62cb4fe2cd681ff5de4e8183bf97ae99`

- **Node:** `agent-delta:20260925101249:373509f3ad8df157`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:**
  `local:continuation/records/agent_delta/agent-delta:20260925101249:373509f3ad8df157.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update
supersedes it.

%model:@medium @plan:202609/agents_deck_picker.md

The above plan has been reviewed and approved. Implement it now.

### Assistant

Done. The Agents deck picker plan is implemented, tested, and verified as far as this
environment allows.

## What landed

**Picker core** — pressing `p` on the Agents tab opens a centered `Switch deck` picker
acting on the focused deck panel; `m`/`f`/`t` pick directly, `j`/`k` wrap, `Enter`
selects, `Esc`/`q`/`pp` cancel, clicks work, and all other keys are swallowed:

- [picker.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/widgets/decks/picker.py)
  (new): pure model — `panel_position_label`, `DeckPickerState`/`DeckPickerRow`,
  `build_deck_picker_rows`, `deck_picker_heading`
- [deck_picker_modal.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/modals/deck_picker_modal.py)
  (new): `DeckPickerModal`, modeled on the grouping modal, with dismiss-once guard and
  close-key collision drop
- [titles.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/ace/tui/widgets/decks/titles.py):
  `DECK_PICKER_KEYS`, `DECK_BLURBS`, `DECK_COUNT_NOUNS`, `DECK_PICKER_RESERVED_KEYS`

**Wiring** — `pick_deck` (`p`) plumbed through `default_config.yml`, `AppKeymaps`,
keymap metadata, fallback bindings, and the `pick_deck`/`pick_artifacts_project`
tab-disjoint duplicate pair; Agents-only + modal-guard availability; `p` added to
deck-search structural exit keys. `action_pick_deck` / palette-only
`action_show_deck_at` go through the existing `show_deck` path with footer refresh.
Palette gained `app.pick_deck` plus `agents.show_deck.<main|files|tools>` (`p f` style
chords, rebound-aware); help modal and the empty-state hint
(`p pick deck · Ctrl+N/Ctrl+P cycle decks`, old text as fallback) updated.
`choose_agent_view` stays retired. Docs updated in `ace.md` (new Agents Deck Picker
section, `p` rows in both key tables) and `configuration.md` (allowlist pair,
retired-keys note, fixed in-picker letters).

**Tests** — 3 new files (pure picker + hint, modal behavior, 9 mounted integration tests
incl. split-focus, no-stack, Artifacts disambiguation, prompt-owns-keys,
committed-search exit), plus keymap/palette/execution/help assertions. Two new PNG
goldens inspected and accepted (no tofu; split golden shows the heading and
`○ in top panel` badge); 5 existing deck goldens regenerated — pixel diffs confirm 4 are
hint-line-only.

## Verification

- `sase tool run check`: all lint gates pass (fmt, ruff, mypy, keep-sorted,
  feature-flags, symvision with full flags). Scoped tests I ran directly: 177
  deck-widget, all new picker/modal/integration tests, keymap/command suites — all
  green.
- Two deviations from the plan, both forced: `deck_count_label` is private
  (`_deck_count_label`) — the symvision gate rejects a same-file-only public symbol; and
  the empty-state golden also picked up a pre-existing staleness (Command-Line
  onboarding row, confirmed stale on the clean tree).

## Caveats (environment, not code)

- The full `just check` test-scoped lane doesn't fit the 10-minute synchronous command
  limit (reached 21% with zero failures before the timeout); same for `just lint` while
  the Rust rebuild held its lock. The directly-affected suites above all pass.
- Two failures exist on the clean tree too (stale `sase_core_rs` wheel): any test
  pressing `space` for the prompt bar, and the bare-symvision `scripts/_run` notice. I
  routed my prompt-ownership test around the Rust path.

Declaration accepted for the commit finalizer. The Agents deck picker work is authorized
for the host to preserve.

---

%xprompts_enabled:true

# New Query

Can you now help me add support for pressing the corresponding capital letter on that
new panel to open that deck in a new horizontal deck panel (or in the non-focused deck
panel if another panel already exists--if a verttical deck layout is currently used,
don't change it to horizontal; just update the deck shown in the other deck panel)?
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
