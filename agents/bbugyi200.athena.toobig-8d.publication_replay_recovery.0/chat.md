# Chat History - ace-run (toobig-8d.publication_replay_recovery.0)

- **TIMESTAMP:** 2026-10-21 07:28:05 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8d.publication_replay_recovery.0

## Prompt

%id(publication_replay_recovery.0, clan=toobig-8d)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agents_sync/publication_replay_recovery.py` file into multiple files? Use your best
%wait:toobig-8d.commit_publication.0
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

I'll split that module into files of 500 lines or fewer while keeping the public import path and test monkeypatch targets. First I'll read the file, related tests, and the split/lint conventions.

The source is 1023 lines; next I’ll map its structure, the existing split pattern, and the tests that monkeypatch private names.

I'll inspect a prior split in this package and the tool that consumes this module so the new layout matches existing conventions.

I’ll split along recovery, backup, and apply, put shared helpers in a private module under public names, and keep a thin public facade.

I’ll clean up the recover helpers, fix the missed imports, and put the public facade in place.

Formatting is clean. Next I’ll run the three requested linters on the split files.

The three lints passed. I’ll run the replay-recovery tests first, then `sase tool run check`.

Check succeeded. I’ll gather the finalizer context and submit the declaration.

Split `publication_replay_recovery.py` (1023 lines) into a public facade plus five private modules, each under 500 lines.

`publication_replay_recovery.py` still exports `ReplayRecoveryReport`, `recover_stale_replay`, and the backup path constants. Implementation lives in:

- `_publication_replay_recovery_types.py` — report, progress I/O, shared constants
- `_publication_replay_recovery_support.py` — `git_text` and `file_bytes`
- `_publication_replay_recovery_backup.py` — inventory and verified backup
- `_publication_replay_recovery_apply.py` — reset, restore, and republish
- `_publication_replay_recovery_recover.py` — lock, classify, and orchestrate

Shared helpers use public names inside those private modules. The interrupted-apply test now monkeypatches `_replay_export_pass` on the apply module.

Verification: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` passed, the replay-recovery tests passed (7/7), and `sase tool run check` succeeded.
