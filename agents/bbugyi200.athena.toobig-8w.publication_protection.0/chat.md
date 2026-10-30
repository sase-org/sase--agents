# Chat History - ace-run (toobig-8w.publication_protection.0)

- **TIMESTAMP:** 2026-10-30 12:58:13 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8w.publication_protection.0

## Prompt

%auto
%id(publication_protection.0, clan=toobig-8w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agents_sync/publication_protection.py` file into multiple files? Use your best
%wait:toobig-8w.staged_handoff.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll start by reading the lint/split conventions and the current `publication_protection.py` so the split stays under 500 lines without changing public imports.

The module is 708 lines. Next I’ll map its public API, tests, and how nearby agents_sync splits were structured.

I’ll inspect the tests’ monkeypatch targets and a recent split so the new layout matches existing agents_sync conventions.

I’ll split the module into private models, scan, and ledger files, keep a public facade, and retarget monkeypatches that currently hit private names.

Next I’ll retarget tests that patched `sase_home`, `sase_projects_dir`, `_scan_file`, and the private ledger reader on the old module.

Formatting is clean. I’ll run the three requested lints next.

Symvision and mypy are clean. The toobig failure is a pre-existing file I didn’t split, so I’m moving on to `sase tool run check`.

`sase tool run check` passed. I’ll pull the finalizer context and submit the commit declaration.

Split `publication_protection.py` into private modules under 500 lines and kept the original public import path.

**Layout**
- `publication_protection.py` — facade that re-exports the public API
- `_publication_protection_models.py` — constants and types (`PublicationBytesVerdict`, `PublicationProtectionScope`)
- `_publication_protection_scan.py` — staging, scanning, `ScannedPublicationCandidate`
- `_publication_protection_ledger.py` — durable ledger reads/writes

Shared helpers used by more than one module got public names in the private models/scan modules. Single-module helpers stayed private in that file. The facade does not re-export `_private` names.

**Tests**
Monkeypatches that targeted `sase_home`, `sase_projects_dir`, `_scan_file`, and `_read_publication_protection_ledger` now hit the implementation modules. Public patches such as `scan_publication_bytes` still go through the facade.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — still red on pre-existing `publication_state_repair.py` (1790 lines); none of the split files are over the limit
- `sase tool run check` — pass (scoped tests included)
