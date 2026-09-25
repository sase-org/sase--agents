# Chat History - ace-run (088)

- **TIMESTAMP:** 2026-09-08 09:29:16 EDT
- **MODEL:** claude/opus
- **AGENT:** 088

## Prompt

#gh:gh_sase-org__sase Can each machine managed by sase's remote dispatch functionality use the same sase config once the work is complete? See the sase-xe epic bead and the remote_machine_management_enablement.md file in the research sidecar repo for context. %m:opus

## Response

I'll dig into the sase-xe epic bead and the research doc.

Short answer: **yes for the shared config *source*, no for one literally identical merged config** — and that split is already designed in, not something the remaining work needs to add.

## What's already true

SASE config selects a per-machine layer through a tiny local selector file, not through different files per host:

- `~/.sase/machine_name` holds one line (`athena` here) — `machine_name_path()`, `src/sase/core/paths.py:131`.
- Every `~/.config/sase/sase_<name>.yml` overlay that declares `id.machine_name` is merged **only** on the machine whose selector matches; overlays without that key merge everywhere — `selected_overlay_paths()`, `src/sase/config/_owner.py:67`.
- Your chezmoi source already carries `sase_athena.yml`, `sase_apollo.yml`, and `sase_kellys_mbp.yml` side by side. So one shared dotfiles tree, one shared `sase.yml`, and each machine picks its own overlay.
- Mappings deep-merge across layers (`deep_merge`, `src/sase/config/loading.py:23`), so `dispatch.*` unions rather than replaces.

## What can be identical on every machine

All of `dispatch` except the machine registry: `providers.*.enabled`, `discovery.enabled_providers`, `request_timeout_seconds`, `status_cache_seconds`, and the whole `federation_worker` block (its `run_root`/`socket_path`/`sase_home` empty-string defaults derive from SASE home plus host identity). Same for `mobile_gateway` on the target side, and for the three currently-`unbound` Focus/Fleet keymaps once item 2 of the research doc lands.

## What can't be shared: `dispatch.machines`

Four independent reasons, all in current code:

1. **The CLI already writes it per-machine.** `_registry_target_path()` (`src/sase/dispatch/config.py:228`) targets the *selected overlay* first, so `sase machine add` on athena writes into `sase_athena.yml` — through the chezmoi source, since you have `use_chezmoi: true`. There's no `--layer` flag to override that.
2. **Duplicate-alias refusal.** `add_machine` rejects an alias already in the merged config (`machine_service.py:91`). Put `apollo` in the shared `sase.yml` and the *second* viewer can never run the normal enrollment path — it'd be forced onto `sase machine repair`.
3. **`repair` rotates the credential ref into the record.** `_credential_ref_for_alias(..., rotate=True)` yields `fleet:<alias>:<8 hex>` (`machine_service.py:358`) and writes it back. In a shared layer, machine B's repair rewrites machine A's `credential_ref` → A gets `credential_missing` until it repairs too, which rotates again. Ping-pong.
4. **No self-guard exists.** Nothing in `src/sase/dispatch/` — and no check in the gateway's enroll route either — rejects a machine listing itself. A shared registry means every host lists itself and gets a permanent `credential_missing` **error** diagnostic (ironically that alone is what makes the Focus/Fleet strip appear, per §4.1 of the research doc), or duplicated self-agents in Fleet if you actually enroll against your own gateway.

Also: credentials and identity are *state*, not config, and must never sync — `~/.sase/fleet/credentials.json` (0600, `dispatch/credentials.py:26`) and `~/.sase/installation_identity.json`. Enrollment is pairwise and per-viewer: three machines fully meshed is six enrollments, each minting its own bearer token.

## Does the remaining work change this?

No. All six follow-ups in the research doc (bootstrap command, keymap binding, tailnet discovery, runbook, gateway distribution, local identity row) are config-neutral or shared-config-friendly. The end state is: **one shared `sase.yml` + one `sase_<machine>.yml` per host carrying only that host's `dispatch.machines`, all living in the same chezmoi repo.** That is "the same config" in the sense you probably mean.

The one thing I'd add to the follow-up list: make `sase machine add` idempotent when the alias exists in config but no local credential does — enroll and reuse the existing record instead of refusing. That's the only real friction for a machine-per-overlay setup, and it removes the need to reach for `repair` (and its ref rotation) on every machine after the first. Want me to file that as a task bead?
