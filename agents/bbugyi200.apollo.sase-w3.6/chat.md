# Chat History - ace-run (sase-w3.6)

- **TIMESTAMP:** 2026-09-04 11:43:22 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-w3.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-w3, bead=sase-w3.6)
%model:@small
%auto
%w:sase-w3.4
%w(bead=sase-w3.4)
Can you complete the work for bead sase-w3.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-w3.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-w3.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-w3.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Good, LinkReveal already exists from Phase 4. Let me read the full file and check where trail breadcrumb chips are rendered in the UI.

I've kicked off a research agent to survey the integration points across all Artifacts panes, the Links panel modal, help modal, and PNG snapshot precedent. I'll wait for that to come back before implementing.

I've started work on sase-w3.6 (Reveal visibility and Links-panel pre-flagging). I read the epic plan and confirmed the phase's scope: a lens chip for live `LinkReveal`s, Links-panel pre-flagging for rows needing a reveal or dangling, a help-modal update, and PNG snapshot coverage. I found that `LinkReveal`/`app._link_reveals` already exist from the prior reveal-ladder phase but nothing renders them yet — only the older `RelationReveal` mechanism has a chip, wired for the Patches pane only.

I've dispatched a research agent to map out the render entry points for every Artifacts pane (stitches/beads/files/plans/agents), the Links panel modal internals, the help modal's current link-follow section, and the PNG snapshot test precedent, so I can implement this correctly across all panes rather than just Patches. I'll continue once that comes back.

It's a package directory, not a single file.

Now let's check keybinding_footer.py and the visual snapshot tests.

Now let's check the artifact_links_panel snapshot test and png_diff / golden update mechanics, plus test-visual justfile recipe.

This is an excellent precedent for task 4 (dangling row already covered pattern). Let's grab the Justfile recipe and png_diff.py update mechanics.

I now have all findings. Let me also quickly check the patches `_display.py` call site context (lines ~480-520) for exact wiring pattern, since it will be the template for other panes.

I now have everything needed. Here is the structured report.

## A. Per-pane header/info render entry points

- **Stitches (commits):** `build_commits_info_header()` at `src/sase/ace/tui/widgets/artifacts/commits_rendering.py:59-76`, called from `build_commits_info()` (same file, line 43) which is invoked at `src/sase/ace/tui/widgets/artifacts/commits_pane.py:276`. No `change_hint`/reveal parameter today — it's a purpose-built Text builder (accent chip + optional `limit:` + optional state badge). A reveal chip could be appended as another `text.append_text(...)` branch inside `build_commits_info_header`, gated on a new param, called from the same site.
- **Files:** `build_files_info()` at `src/sase/ace/tui/widgets/artifacts/files_rendering.py:46-123`, called from `src/sase/ace/tui/widgets/artifacts/files_options.py:394`. No reveal/hint threading beyond a hardcoded "change" hint (line 66-68); natural insertion point is right after the scope chip (~line 68) before the kind-summary chips.
- **Agents:** No shared rendering module — built inline as `_scope_text()` method at `src/sase/ace/tui/widgets/artifacts/agents_options.py:299-309`, called from `self._update_static("#agents-info", self._scope_text())` at line 206 (inside the options-sync method). This is the single call site to extend.
- (For contrast, Beads/Plans use `build_shell_scope()` from `shell.py:96-121` via `build_beads_scope`/`build_plans_scope`, called at `beads_options.py:277` / `plans_options.py:457` — `build_shell_scope` already accepts `change_hint` but that's semantically the "how to change scope" hint, not a reveal chip.)

`build_reveal_chip()` already exists generically at `src/sase/ace/tui/widgets/artifacts/shell.py:124-142` (built for `RelationReveal`, but pane-agnostic in signature: `label`, `accent`, `return_hint`) — reusable as-is for `LinkReveal` too.

## B. Canonical query string per pane

There is **one** generic, app-level property: `AceApp.canonical_query_string` at `src/sase/ace/tui/app.py:358-361`, defined as `self._canonical_patch_query(self.query_string, self.parsed_query)`. It is used identically for Patches (`_display.py:514`) and is already the same expression `_link_follow_ladder.py:60` uses (`getattr(app, "canonical_query_string", source)`) to populate `app._link_reveals`. There is **no per-pane duplicate** — beads/files/stitches/agents/plans do not have their own `canonical_query_string`; the single query bar/property reflects whichever pane is currently active. So `is_link_reveal_active(reveal, pane_id=<pane>, current_canonical=self.canonical_query_string)` is directly reusable everywhere, exactly like Patches.

## C. Links panel modal + staleness pass

`src/sase/ace/tui/modals/artifact_links_panel_modal.py`:
- `_is_missing(chip)` (line 75-78): dangling == `chip.neighbor_target is None and neighbor_kind != "chop"`, where `neighbor_kind` comes from `parse_link_ref(chip.neighbor_ref)`. `chip.neighbor_target` is already an `ArtifactEntryTarget | None` (see `LinkChip.neighbor_target` at `src/sase/ace/tui/relations/link_index.py:43`), resolved by `entry_target_for_ref` (defined `src/sase/ace/tui/widgets/artifacts/entry_navigation.py:126`) at chip-construction time in `link_index.py:213-234` — the modal itself never calls `entry_target_for_ref`; it only reads `chip.neighbor_target`. To flag "would need a reveal," extend `_is_missing`'s sibling logic to also test `is_link_reveal_active`/pane-ref resolution using `chip.neighbor_target.pane_id` + `chip.neighbor_ref`, reusing the same resolved target rather than re-resolving.
- Rows are built in `_artifact_link_option_text()` (lines 118-146): label, direction glyph, missing marker `⊘`, target label, metadata lines, "why" text — all driven by `_is_missing(chip)` styling (`_MISSING_STYLE`). A "needs reveal" flag would slot in next to the existing `⊘` glyph logic the same way.
- Modal build-time data available: only `LinkChip` objects (`self._chips`), no direct pane instances — so any reveal check must be computable from `LinkChip` fields alone (mainly `neighbor_target.pane_id` + a canonical-query lookup against the *live* app, not chip data).

`src/sase/ace/tui/actions/link_follow.py`:
- `_open_artifact_links_panel` (starts ~line 200, push at line 252-266) builds `initial_notice` via `_cached_link_panel_staleness_notice(self)` (line 251, defined line 749) synchronously from `app._link_index_loading`/`_link_index_errors`, then pushes the modal, then calls `_schedule_artifact_links_panel_staleness_refresh(modal, initial_notice=initial_notice)` (line 267-270).
- `_schedule_artifact_links_panel_staleness_refresh` (lines 320-339): spawns one **pump-free async task** (`spawn_pump_free_task(..., name="sase-artifacts-link-panel-staleness", registry_attr="_link_rail_tasks")`) that runs `_artifact_link_index_drift_notice()` off-thread (line 764-780, calls `inspect_artifact_link_health`), then calls `modal.update_staleness_notice(_combine_notices(initial_notice, notice))` (modal method at `artifact_links_panel_modal.py:291-301`). This is a **one-shot** task at modal-open time (not a repeating tick), stored in `app._link_rail_tasks`. To add "would need a reveal" flags without a new pass, extend this same `_runner()`/`update_staleness_notice` flow (or a parallel per-row update method on the modal) so it computes reveal-flags once, off-thread-safe, and pushes them into the already-open modal — matching the existing staleness-notice update pattern rather than adding a new scheduled task.

## D. Help modal link-follow section

`help_modal.py` is a **package** (`src/sase/ace/tui/modals/help_modal/`), not a single file; `_BOX_WIDTH`/`_CONTENT_WIDTH` actually live as `BOX_WIDTH = 57` / `CONTENT_WIDTH = 50` in `src/sase/ace/tui/modals/help_modal/binding_common.py:11-12`, consumed by `sections_render.py:16,31`.
- Link-follow rows are defined independently per pane's help section via a repeated helper `_link_follow_row(key)` returning `[(f"{key}{key} / {key}1-9 / {key}0", "Follow link / open links panel")]` in three places: `patches_artifact_bindings.py:43-46` (inline, no helper), `agents_bindings.py:523-524`, `axe_bindings.py:180-181`. All three currently say exactly **"Follow link / open links panel"** — this wording (and the `$1-9`/`$0` key syntax) is what needs updating for the changed link-follow behavior and to mention lens-chip / dangling-flag behavior, subject to the 32-char description truncation rule in `sections_render.py:48-49` (`max_desc_width = content_width - _KEY_WIDTH - 2`, `_KEY_WIDTH = 16`).

## E. Footer

`src/sase/ace/tui/widgets/keybinding_footer.py` has **no** existing entry referencing `reveal`, `LinkReveal`, or `RelationReveal` (confirmed via grep — zero matches). Per `src/sase/ace/CLAUDE.md`'s footer rule ("a keymap appears in the footer iff it has a condition that is sometimes true and sometimes false"), a reveal-chip binding itself has no new key (it reuses `prev_query`/existing return key), so it does **not** need a footer entry — the per-pane lens chip already communicates the transient state visually, matching how Patches' relation-reveal chip has no footer entry either.

## F. PNG snapshot precedent

Precedent file: `tests/ace/tui/visual/test_ace_png_snapshots_artifact_links_panel.py` — already has a `_dangling_chips()` fixture (lines 111-124) and `test_artifact_links_panel_dangling_row_png_snapshots` (lines 208-229) parametrized over `(120,40)`/`(60,30)` sizes, golden names `artifact_links_panel_dangling_row_120x40`/`_60x30`. This is the direct template for task 4's panel-flag coverage — extend `_dangling_chips()`/add a "needs reveal" chip variant and a new parametrized test following the same `_assert_panel_snapshot` helper (lines 127-156).

For the lens chip itself, no existing PNG test covers `build_reveal_chip`/Patches' relation reveal (grep of `tests/ace/tui/visual/` for "reveal"/"chip" found none) — `tests/ace/tui/test_artifacts_shell.py` covers `build_reveal_chip` at the unit level only, not PNG. New PNG tests should follow the pattern in `test_ace_png_snapshots_artifacts_beads.py` (per-pane `AcePage`, `patch_startup_loaders`, `wait_for_svg_contains`, then `ace_png_visual.assert_page_png(page, name, title=...)`).

Mechanics: `Justfile:451` `test-visual` runs the visual suite; `Justfile:513-514` `update-visual-snapshots` runs `just test-visual -- --sase-update-visual-snapshots` to regenerate goldens. Missing-golden failures write actual/summary artifacts and instruct exactly this flag (`png_diff.py:239-241`); mismatches likewise (`png_diff.py:295`). Goldens land under `tests/ace/tui/visual/snapshots/png/<name>.png` (per `snapshot_path` in `_png_diff_artifacts.py`, referenced from `png_diff.py:16`).

Confirmed pane ids: `stitches`, `patches`, `beads`, `agents`, `files`, `ref:plan`. Now let me look at the other renderer files needing the chip: plans_rendering.py/plans_options.py, commits_rendering.py/commits_pane.py, files_rendering.py/files_options.py, agents_options.py, and re-check patch/_display.py.

Good, confirms `"stitches"`. Now let's check agents_options.py `_scope_text` (`_scope_text` method at line ~299).

Now plans_options.py:

Now files_options.py `_scope_text`:

I'll add the chip directly in `build_files_info` since it already takes `registry`, keeping this consistent with how files_rendering.py already reaches into `registry.app`.

Now agents_options.py `_scope_text`:

Now commits_pane.py (stitches):

Not imported. Let's add it plus `active_pane_link_reveal` and `build_reveal_chip`.

Now update `_build_info_header` (used for the live-refreshed `#stitches-header` widget):

Now let's verify the actual imports resolve correctly at runtime (no circular import issues) by importing the app module.

Now let's implement. First, edit the modal file for `needs_reveal` rendering support.

Now wire `reveal_flags` through the modal class:

Now add the `_link_panel_reveal_flags` function near `_cached_link_panel_staleness_notice`:

Good — this is a pure in-memory contract, safe to call synchronously. Now let's search for existing tests for the modal to align naming/behavior conventions, and confirm `entry_target_for_ref` default returns `None`.

Now let's syntax-check the edited files and run the relevant existing unit tests for link_follow and the modal.

Now the inline version in patches_artifact_bindings.py:

Now update the 6 call sites to use the corrected signature. Beads first:

Now plans_options.py:

Now files_rendering.py — the pane instance is not directly accessible (only `registry` is passed), so I need to pass the pane through. Let's check the `_scope_text` call site in files_options.py to see what's available (`self` there is the pane).

Now update the files_options.py call site to pass `pane=self`:

Now commits_pane.py (stitches):

Good, `CommitsFilteringMixin` is composed in. Now update `_build_info_header`:

Now Patches in patch/_display.py — keep using `self.canonical_query_string` directly:

Now let's syntax-check everything again and run pyflakes/ruff quickly on the touched files.

Now let's run `just install` (fresh workspace prerequisite) then `just check`.

Now add the new test function after the dangling row test:

Good, all methods exist as used. Let's check on the `just install` background task now.

Good, already imported. Let me wait for the `just install` background task to complete before running `just check`.

Good, well within the 16/32-char limits. Now let's review the full diff so far for consistency.

Looks good. Let's check on `just install`'s status now.

This all looks correct. Now let's wait for the `just install` background task to finish before running `just check`.

`just install` is running in the background (building the Rust `sase_core_rs` core via cargo, which can take a few minutes). I'll wait for it to finish before running `just check`.

I'll wait for the notification that the install finished before proceeding to `just check`.

I've committed the in-progress work for sase-w3.6 (lens chip wiring, Links-panel pre-flagging, and help-modal updates). `just install` is still building the Rust core in the background; I'll continue with `just check`, then the PNG snapshot suite, once it finishes, and close the bead after verification.

I've committed the work so far for sase-w3.6. `just install` (rebuilding the Rust core) is still running in the background — I'll run `just check`, then the PNG visual suite, once it completes, and close out the bead after verification passes.
