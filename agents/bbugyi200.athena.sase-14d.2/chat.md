# Chat History - ace-run (sase-14d.2)

- **TIMESTAMP:** 2026-09-20 14:43:29 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-14d.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-14d, bead=sase-14d.2)
%model:@medium
%auto
%w:sase-14d.1
%w(bead=sase-14d.1)
Can you complete the work for bead sase-14d.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14d.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14d.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14d.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Looking up the sase-core checkout so I can find the commit that `core-rules` produced.

Remote HEAD is the v0.34.70 release commit, a descendant of the delivery-rules commit. Applying the ratchet and reading the config files I need to change.

The venv rebuilt from the new pin. Checking the binding exists and reading the existing Python patterns I'll mirror.

Pin ratcheted and venv rebuilt. Now checking the binding signature, the notifications package layout, and the symvision rules for new symbols.

Now writing the code. Wire types and converter first.

Now the config surface: default config and JSON schema.

Formatting normalized. Now the Python facade module.

Writing the tests now.

All 43 tests pass against the real core binding. Now symvision, to see which symbols need epic whitelisting.

My symbols are clean in symvision now (the remaining failures exist at clean HEAD and are unrelated). Running the full `just check` gate.

Every lint stage passes except symvision, which fails only on the 26 pre-existing symbols from other in-flight work. `check` stops at lint, so I'll run the diff-scoped test lane directly.

Same 7 failures on clean HEAD, so they're pre-existing and unrelated. One last check on the published core floor, since the new call site needs a binding that only exists from v0.34.70.

v0.34.70 is on PyPI, so the package floor (`>=0.34.48`) can be raised to cover the new binding. Checking how the earlier floor ratchet was done.

Everything is in place. Recording follow-ups on the bead, then closing it with the contract for the downstream phases.

Bead closed. Now the required final declaration.

The bead is already closed (I closed it per the task instructions), so the finalizer can't re-close it. I'll submit with `keep`, which leaves the bead as it is.

Bead sase-14d.2 is closed and the work is submitted for the host to commit.

**Not fully green:**
- **`just check` (symvision):** it stops at the symvision stage, which fails on 26 unused public symbols from other in-flight work. I confirmed the same failure at clean HEAD. None of the reported symbols are mine.
- **Test failures:** the full test lane ran and 7 tests failed out of about 44,000. They are in the capacity-gate, epic-panel and lazy-tier2 tests. I stashed my changes and re-ran them, and they fail identically on clean HEAD.
- **Other checks:** ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology and keep-sorted all pass. The 43 new tests pass against the real core binding.

**What I changed:**
- **Pin:** `sase-core-revision.txt` now points at `92625404…` (the v0.34.70 release, which includes the `resolve_notification_deliveries` binding). `just install` rebuilt the venv from it, and I called the real binding.
- **Config:** `ace.notification_rules: []` is in `default_config.yml` with a comment block, and the schema has the matching array entry. It rejects unknown keys at the rule and `match` level and bounds `priority` to -1000..1000.
- **Facade:** a new `src/sase/notifications/delivery.py` reads the rules once per config token and resolves a whole batch of notifications in one binding call. The wire types and converter went into `notification_store_wire.py`, and the facade function sits beside `classify_notification_tabs`. With an empty batch or no rules it returns the defaults without calling the core, and a test checks those defaults match the core's.
- **Dropped rules:** a malformed rule is dropped whole rather than partly applied. A typo'd or blank criterion could otherwise widen a rule like `toast: false` to every notification.
- **Rule labels:** an unnamed rule's `rule[<index>]` label counts the rules that survived, not the raw config list.
- **Symvision:** I added epic-symbol entries for `NotificationDelivery` and `NotificationSound` (keyed to `sase-14d.4`) and for `notification_delivery_rules` (keyed to `sase-14d.5`). None are keyed to this bead.

I recorded two `PROPOSED FOLLOW-UP` notes on the bead:
- **Package floor:** `pyproject.toml` still declares `sase-core-rs>=0.34.48`, but the new call needs 0.34.70. `tools/ratchet_core_window --report-only` already proposes the bump. I left it out to match how the earlier `agent_hold_deadlock_reaches` pin was handled.
- **Pre-existing breakage:** the symvision failures and the 7 failing tests above.

The finalizer refused `bead_action: "close"` because the bead was already closed, so I submitted with `keep`.
