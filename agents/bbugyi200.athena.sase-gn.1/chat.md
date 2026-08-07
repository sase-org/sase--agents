# Chat History - ace-run (sase-gn.1)

- **TIMESTAMP:** 2026-08-06 20:17:41 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gn.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-gn.1, bead=sase-gn.1)
%clan(sase-gn, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-gn.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gn.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gn.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead details.

Now let me explore the relevant code. First, the Rust core repo and the Python side.

Now the Rust core side.

Now let me write the Rust core changes.

Now the wire types and store/mod wiring.

Now store.rs:

Now the pyo3 binding:

Pre-existing env issue (libpython not found), unrelated. Now rebuilding the binding while I write the Python side.

Now the Python side. Wire and facade first:

Now the facade:

Now `sase/notifications/store.py` — expose `snapshot.tabs`:

Now `build_notification_tag_tabs` becomes a thin adapter over the core:

Now the options mixin uses the cached map:

Now the reserved panels:

The multi-tab bug is structurally fixed. Now let me update the tests and run them.

Expected — Snoozed is now its own tab. Let me update the affected tests.

Now update the two remaining Python tests and rebuild the binding.

Now let me add the parity test and run the broader suite.

Now the reserved-panel tests and the broader suite:

Now the docs:

That's the intended new behavior — snoozing a row now moves it to the Snoozed tab.

Now let me run the full check.

Now consolidate the tag helpers to one public entry point:

Now update the tests that referenced the removed helpers:

Let me verify the final diff and the crate state.

Now let me record the follow-ups and close the bead.

Done. Bead `sase-gn.1` is closed.

## What changed

**Rust core** (`sase/repos/linked/sase-core`) — new `crates/sase_core/src/notifications/tabs.rs`:
- `tab_key_for` implements the D1 precedence, returning exactly one `(key, kind)` per notification: `__snoozed__` (muted + wake time) → `__muted__` → declared panel → `hitl` → `errors` → **first** stored tag → `general`.
- `tabs_and_counts_for` builds the ordered tab list and `NotificationCountsWire` in one pass; `counts_for` now delegates to it, so the two can't drift. `NotificationStoreSnapshotWire` gained `tabs` (`#[serde(default)]`).
- `classify_notification_tabs` is the pure entry point for in-memory rebuilds, returning ordered tabs **plus** a `row_tab_keys` map — that map is what keeps Python from paying an FFI hop per row.
- Exposed as a `classify_notification_tabs(list[dict]) -> dict` pyo3 binding.

One thing the plan didn't anticipate: a declared panel and a stored tag can name the same tab, and with single-valued ownership the tab's `kind` (and therefore its sort slot) would have depended on which row arrived first. I added a `kind_rank` so panel beats tag deterministically, matching the old ordering, with a test asserting both row orders agree.

**Python** — `_NotificationTabWire` + `tabs` on the snapshot wire (decoded with `known_field_kwargs`, so an older core still loads), `classify_notification_tabs` on the facade, and `notification_modal_tags.py` reduced to an adapter. `NotificationModal` caches the row-id → tab-key dict on every `_tag_tabs()` rebuild; membership is a dict lookup. `RESERVED_GATE_PANELS` is now `{errors, general, hitl, muted, snoozed}`.

## Verification

- `cargo test --workspace`: 1246 lib tests + all integration suites green; `cargo fmt`/`clippy` clean. (`sase_core_py --lib` aborts with a missing `libpython3.14.so` — pre-existing, confirmed on a stashed tree.)
- `just check`: every lint gate plus the 26.5k-test scoped lane green.
- New `tests/test_notification_modal_tags.py` pins the two-tag regression, the Snoozed/Muted split, a snoozed gate leaving its Beads tab, adapter-vs-snapshot parity, and tab counts partitioning the legacy counters.

## Left for the land agent

Both repos are **uncommitted** — you didn't ask me to commit, and the crate change needs its own commit in `sase-core`. The important one, recorded as a `PROPOSED FOLLOW-UP`: dev installs build the binding from the local checkout, but `pyproject.toml` pins `sase-core-rs>=0.18.4,<0.19.0`, which has no `classify_notification_tabs`. A published wheel would raise from `require_rust_binding`, so the crate release and window bump must land before this ships.

Both repositories are committed and pushed; bead `sase-gn.1` was already closed and the re-run confirmed the close is published (no unpublished diagnostic).

**`sase-core`** — `7ee5105 feat(notifications): make tab ownership a single-valued core rule`
New `notifications/tabs.rs` assigns each notification exactly one tab key by fixed precedence (snoozed → muted → declared panel → hitl → errors → first tag → general); `tabs_and_counts_for` builds the ordered tab list and wire counts in one pass with `counts_for` delegating to it; `NotificationStoreSnapshotWire` gains a serde-default `tabs` field; `classify_notification_tabs` exposed via pyo3 returning tabs plus a row-id→tab-key map.

**main workspace** — `5e6a94a feat(ace-tui): give each notification exactly one tab, counted in the core`
`notification_modal_tags.py` reduced to an adapter over the core classifier, snapshot wire decodes `tabs` via `known_field_kwargs`, `NotificationModal` caches the row→tab map for dict-lookup membership, `RESERVED_GATE_PANELS` gains `snoozed`, plus docs and the new/updated tests.

The first commit's wrapper was killed by a 2-minute command timeout, so I verified it directly: the commit exists, the tree is clean, and `git ls-remote` confirms `origin/master` points at it. Both pushes are confirmed against the remote.

Two `PROPOSED FOLLOW-UP` notes are on the bead for the land agent — the important one being that `pyproject.toml` pins `sase-core-rs>=0.18.4,<0.19.0`, which has no `classify_notification_tabs`, so the crate release and window bump must land before this ships as a published wheel.
