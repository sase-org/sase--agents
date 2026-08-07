# Chat History - ace-run (sase-gu.1)

- **TIMESTAMP:** 2026-08-07 10:01:01 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gu.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-gu.1, bead=sase-gu.1)
%clan(sase-gu, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-gu.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gu.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gu.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now the `repos.sidecar` property:

Now the parser.

Now add `_sidecar_config_entries` and wire it in:

Now `init_memory/config.py`:

Now fix the shadowed `label` name and the import:

Now add schema tests:

Now add parser tests:

Now the CI bootstrap tool tests:

Now use the shared bucket-key constants in the doctor module:

Now move the new schema tests into the repositories-focused module:

Phase `dual_read` (sase-gu.1) is done and the bead is closed.

## What changed

**Schema** (`src/sase/config/sase.schema.json`, `src/sase/default_config.yml`)
- New `sidecarRepoEntry` definition — `sidecarRepo` minus `name`, still closed, no required fields.
- `repos.sidecar` is now a `oneOf`: the canonical `{builtin, custom}` role-keyed object (with `propertyNames` enforcing that `builtin` holds only `plans`/`beads`/`agents` and `custom` holds none of them), plus the deprecated array branch marked `deprecated`.
- Default moved from `[]` to `{}`; `default_config.yml` ships `sidecar: {builtin: {}, custom: {}}`.

**Parser** (`src/sase/_linked_repo_config.py`)
- `_sidecar_config_entries()` reads both shapes and injects `name` from the map key. Builtin roles emit in canonical `plans, beads, agents` order, then custom roles in configured order; a role in both buckets resolves to `custom`. Non-mapping values are skipped defensively. The `{role, slug}` token merge stays for the legacy list.

**Other raw readers**
- `init_memory/config.py`: `_sidecar_repos_raw` now yields `(label, role, entry)` triples — mapping errors read `repos.sidecar.custom['research']`, the list form keeps `repos.sidecar[0] ('research')`. Every existing validation rule is preserved.
- `tools/ci_bootstrap_sidecars`: `plan_sidecars` accepts either shape.

**Doctor** — new `config.repos` check (`checks_config_repos.py`, registered in `checks_config.py`) reporting the legacy list with each entry's target bucket, mis-bucketed and duplicated roles, leftover `name:` keys, non-mapping buckets/entries, and enabled lazy `custom` entries with no description.

I re-grepped `src/` and `tools/` per the plan's risk note: the only remaining raw reader is `_repo_init_config.explicit_sidecar_config_update`, which `migrate_configs` owns.

## Verification
`just install`, `just lint` (ruff, mypy, symvision, toobig all clean), `just test-scoped` (26760 passed), `sase doctor -C config.repos`, and `sase repo list` showing unchanged sidecar rows.

Two unrelated failures, both recorded as `PROPOSED FOLLOW-UP:` notes rather than fixed here — I confirmed both reproduce independently of this change:
- `sase validate` fails on a clean `master` tree: `init memory --check` wants a +2/−2 update to the chezmoi `sase/memory/README.md`. This means `just check` does not currently reach green on this repo for reasons unrelated to the phase.
- `tests/test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit` flakes under the parallel scoped lane and passes in isolation.

The bead was already closed in the prior pass. Now committing.

Committed and pushed; working tree clean, branch level with `origin/master`.

**Commit** `50bed7f99` — `feat(config): accept role-keyed sidecar repo config alongside the legacy list`

- **Schema** (`sase.schema.json`, `default_config.yml`): new `sidecarRepoEntry` definition; `repos.sidecar` is a `oneOf` over the role-keyed `{builtin, custom}` object and the now-deprecated array, with `propertyNames` pinning `plans`/`beads`/`agents` to `builtin`. Default is `{}`.
- **Parser** (`_linked_repo_config.py`): `_sidecar_config_entries` reads both shapes, injecting `name` from the map key; builtin roles emit in canonical order, then custom roles, with `custom` winning on collision.
- **Raw readers**: `init_memory/config.py` yields `(label, role, entry)` triples for precise error labels; `tools/ci_bootstrap_sidecars` plans from either shape.
- **Doctor**: new `config.repos` check (`checks_config_repos.py`) for legacy lists, mis-bucketed/duplicated roles, leftover `name:` keys, non-mapping buckets, and description-less lazy custom entries.

Bead `sase-gu.1` was already closed (close reported "Already closed", verified published); the verification note is recorded on it.

Verification carried over from the implementation pass: `just install`, `just lint` (ruff, mypy, symvision, toobig clean), `just test-scoped` (26760 passed), `sase doctor -C config.repos`, `sase repo list`. The commit's `just fix` hook ran clean. Two pre-existing, unrelated failures are recorded as `PROPOSED FOLLOW-UP:` notes on the bead: `sase validate` wanting a chezmoi `sase/memory/README.md` update on clean `master`, and a flake in `tests/test_install_coverage_contexts_tool.py::test_installing_prunes_the_cache_to_the_keep_limit` under the parallel lane.
