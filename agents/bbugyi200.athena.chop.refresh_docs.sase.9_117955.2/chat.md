# Chat History - ace-run (chop.refresh_docs.sase.9_117955.2)

- **TIMESTAMP:** 2026-08-07 16:27:34 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.9_117955.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.9_117955.2, tribe=chop)
%wait:chop.refresh_docs.sase.9_117955.1
%wait(runners=0)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll start by looking at what the update agent changed.

Now let me make the corrections. Starting with `docs/axe.md`:

Now `docs/sdd.md`:

Now `docs/ace.md` — the entry-jump paragraph, the commit-time chip, and the Statistics keymap example:

Now the Statistics keymap example block in `docs/ace.md`:

Now `docs/configuration.md`:

Now let me run the documentation checks:

I verified every claim in commit `2d054ed19` against current source (including the Rust core via `sase repo open sase-core`), and corrected the ones that were wrong or misleading. All six files remain docs-only; `just fmt-md-check`, `just docs-check`, and `just check` pass.

## What was accurate

- **axe.md**: the two-kind reconciliation (`TaskTriage` for `ready`, `BeadSnooze` for `snoozed`) under one lock/lane state, wrong-kind cancellation as `bead_status_changed` outranking the fingerprint compare, the generation counter, the status-only scan bypassing `sase bead ready` — all match `src/sase/scripts/sase_chop_bead_task_triage.py`. The third **Snooze (3d, 3d +2)** option matches `src/sase/bead/_task_gate_spec.py:48`.
- **notifications.md**: strip hidden only at zero tabs (`notification_modal.py:365`), zero tabs ⟺ the `No unread notifications` message, label-shedding reflow (`notification_modal_tags.py:243`).
- **init.md / configuration.md**: `--check` deferral (`init_skills_handler.py:402`) and the aggregated `Warnings:` block (`validate_handler.py:116`).
- **ace.md**: `jump_to_entry: "apostrophe"` is a real Statistics default; the chip is author time (`%at`) and is persisted as `committed_at` in the commit markers; `'` on Statistics really does arm numbered-view selection.
- **sdd.md**: `header-invalid` is emitted by both the Python link validator and the Rust `validate_header_block`, so all five named surfaces do raise it, and `sase bead work` validates before archiving.

## Corrections I made

- **sdd.md — factually wrong for `BEAD`.** The text said every link-shaped section must be "a bolded key followed by exactly one Markdown link and nothing else." `SddPlanHeaderSectionKindWire::allows_unlinked_label` permits `BEAD` to carry a bare label, which the section table two paragraphs earlier already said ("one link or label"). Documented the exception, added the empty-section/inline-content rule and the duplicate-section and `PLAN`+`PROMPT` errors, and softened "reported identically" to "the same `header-invalid` code" (the Rust message appends a remedy the Python one lacks).
- **axe.md — wrong CLI comparison.** The snooze duration does *not* use the same `"<duration> [+<N>]"` form as `sase bead snooze`; the CLI takes `-u` and `-p` as separate flags, and only the gates/ACE modal accept the compact form (`snooze_time.py:20`). Rephrased to match beads.md, and added a cross-link to the snooze workflow so a new reader knows what a `BeadSnooze` gate is.
- **axe.md — understated fingerprint.** It covers title, description, notes, size, created-at, refs, +1 evidence, and close history, not just status and snooze — so an edited description also replaces the gate. Also noted re-snooze healing only applies to a future wake time.
- **notifications.md — overclaim.** "Every tab therefore stays visible and clickable at any modal width" isn't guaranteed: the compact render can still exceed a very narrow width. Restated as what the code actually does.
- **configuration.md — misleading mechanism.** "Anything that rebuilds the tree — a filter change, `m`, `r`, or a `:` path jump — cancels an active jump" implies those keys are live during jump mode; they aren't (they're consumed as hints or as invalid keys that exit). Described the real rule.
- **ace.md — clarity.** Rewrote the garbled "`'` back pops a bounded back stack" into what a user actually does (press `'` again while hints are up), named the ten-entry bound, the empty-stack fall-through, and both footer strings (`JUMP ' back` / `JUMP ' first`). Placed the commit chip on the header's diff-path line rather than "the modal title... on its right". Added a note that the Statistics YAML block is a *partial* remap example — `cycle_range`/`cycle_range_reverse`/`refresh`/`help` are shown moved off their `t`/`T`/`r`/`?` defaults, which reads as authoritative defaults otherwise.

## Suspected code issues (not fixed — docs-only scope)

1. **`src/sase/ace/tui/modals/config_pane_widget.py:348` — jump mode can survive a tree rebuild invisibly.** `_invalidate_jump_after_rebuild` compares `_node_by_path` (every shown field, expansion-independent) and passes `target_count=len(current_paths)`, but hint indices address `_jump_nodes()` (only *expanded* rows). A rebuild that leaves the path set unchanged — e.g. a background reload landing while hints are up — re-renders labels without hints and re-expands every section, yet leaves `mode_active` true with a still-"valid" hint map. The next keypress then jumps to a row the user can no longer see was hinted.
2. **`crates/sase_core/src/plan/validate.rs:20` (sase-core) — `HEADER_BLOCK_REMEDY` is inaccurate for `BEAD`.** The remedy text an agent is handed says every link-shaped section needs exactly one Markdown link, but the parser accepts a bare label for `BEAD`. This is the string my sdd.md correction had to work around.
3. **Still open from the previous pass:** `docs/agents_sidecar.md` is linked from six pages but absent from the `mkdocs.yml` nav, so it's unreachable by browsing. Fixing it means editing build configuration.

Docs checks pass. Committing.

Committed as `f150ed7ed`; working tree is clean and `master` matches `origin/master`.

## What the commit contains

Corrections to six docs pages, verified against current source (including the Rust core, opened via `sase repo open sase-core`) rather than taken on faith from the previous refresh:

- **`docs/sdd.md`** — the "exactly one Markdown link" rule isn't absolute: `allows_unlinked_label` permits `BEAD` to carry a bare label, which the section table two paragraphs earlier already said. Added the empty-section rule, the duplicate-section and `PLAN`+`PROMPT` errors, and softened "reported identically" (the Rust surface appends a remedy the Python one lacks).
- **`docs/axe.md`** — the snooze field does *not* share a form with `sase bead snooze`; the CLI takes `-u`/`-p` separately, and only the gates and ACE modal accept `"<duration> [+<N>]"`. Also widened the presentation fingerprint to the fields it really covers (title, description, notes, size, created-at, refs, +1 evidence, close history) and noted the future-wake-time condition on re-snooze healing.
- **`docs/notifications.md`** — dropped "every tab therefore stays visible at any modal width"; label shedding reduces overflow but doesn't guarantee fit.
- **`docs/configuration.md`** — filter, `m`, `r`, `:` aren't live during Config jump mode, so they can't "cancel" a jump; described the real rule.
- **`docs/init.md`** — split the `--check` warning into its two distinct cases (pending chezmoi redeploy vs. source-integrity refusal).
- **`docs/ace.md`** — rewrote the `'` back-stack paragraph around what a user actually presses (ten-entry bound, empty-stack fall-through, both footer strings), moved the commit-time chip onto the header's diff-path line, and flagged the Statistics keymap block as a *partial* remap example so its non-default keys aren't read as defaults.

Claims I checked and left alone: the two-kind axe reconciliation and generation counter, the notification strip's zero-tab behavior, the `--check` deferral and aggregated `Warnings:` block, and `jump_to_entry: "apostrophe"` as a real Statistics default.

`just fmt-md-check` and `just docs-check` (strict mkdocs build) pass; the pre-commit `just fix` hook ran clean.

## Suspected code issues — not fixed, docs-only scope

1. **`src/sase/ace/tui/modals/config_pane_widget.py:348`** — `_invalidate_jump_after_rebuild` compares `_node_by_path` (every field, expansion-independent) while hint indices address `_jump_nodes()` (expanded rows only). A rebuild that preserves the path set re-renders without hints and re-expands sections, yet leaves `mode_active` true with a still-"valid" hint map, so the next keypress jumps to a row the user can't see was hinted.
2. **`crates/sase_core/src/plan/validate.rs:20`** (sase-core) — `HEADER_BLOCK_REMEDY` tells agents every link-shaped section needs exactly one Markdown link, which is wrong for `BEAD`. This is the string the `sdd.md` correction had to work around.
3. **Still open from the prior pass** — `docs/agents_sidecar.md` is linked from six pages but absent from `mkdocs.yml`'s nav (the docs build prints it), so it's unreachable by browsing. Fixing it means editing build configuration.

I did not file beads for these; say the word and I'll run `/sase_new_task` for each.
