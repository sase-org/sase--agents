# Chat History - ace-run (toobig-94.workspace_retention.0)

- **TIMESTAMP:** 2026-11-02 20:11:48 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-94.workspace_retention.0

## Prompt

%id(workspace_retention.0, clan=toobig-94)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/turns/workspace_retention.py` file into multiple files? Use your best
%wait:toobig-94.settlement.0
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

I'll split `workspace_retention.py` into smaller modules while keeping the public import path. First I'll read the lint/split conventions and inspect the current file.

Next I’ll inspect the module, existing split patterns, and tests so the facade and private helpers stay compatible.

I'll look at prior module splits and the tests that patch this file so the public path stays intact.

I'll look at recent splits and how `_WorkspaceRetentionResult` is used so the facade stays public-only.

I have a split plan: a public facade plus a private `_workspace_retention` package so helpers stay public inside that package. Next I’ll add the new modules.

Formatting is clean. Next I’ll run the three requested lints on the split files.

All three lints passed. Next I’ll run `sase tool run check` as the full verification gate.

Split `src/sase/turns/workspace_retention.py` (822 lines) into a public facade plus a private package. Every new file is under 500 lines.

`sase.turns.workspace_retention` still exports the same public names. Implementation now lives in `src/sase/turns/_workspace_retention/`:

| File | Role |
|---|---|
| `workspace_retention.py` (43 lines) | Facade re-exporting public names only |
| `_workspace_retention/types.py` | Owner, repo, successor types and locators |
| `_workspace_retention/discover.py` | Repository discovery |
| `_workspace_retention/pending.py` | Pending-retention facts |
| `_workspace_retention/records.py` | Durable record persist/settle helpers |
| `_workspace_retention/settle.py` | Evidence collection and effect application |

Shared helpers used across modules are public names inside that already-private package (`persist_record`, `settle_existing_record`). No `_`-prefixed names are imported across files. Tests did not need monkeypatch retargets.

Verification:

- `just _lint-symvision` passed
- `just _lint-mypy` passed
- `just _lint-toobig` passed
- `sase tool run check` succeeded (scoped tests included)
