# Chat History - ace-run (sase-17q)

- **TIMESTAMP:** 2026-09-24 09:47:27 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17q

## Prompt

#gh:gh_sase-org__sase
%id(sase-17q, bead=sase-17q)
%m:@medium
Can you complete the work for task bead sase-17q by running the `sase bead read sase-17q -r "Need the task scope"` command,
reviewing the command's output, doing the work, and then closing the bead by running the
`sase bead close sase-17q --note "<what you verified>"` command?

If you discover genuinely distinct follow-up work that is outside this task, use `/sase_new_task` with details
identifying the current bead; it will corroborate a duplicate, attach a causally related active-epic issue, or
create a sized task as appropriate.

## Response

Done. sase-17q is fixed and closed.

Result: the publication guard no longer reads every stream blob per revision. It takes stream-name sets from `ls-tree`, batch-reads only changed streams via one `git cat-file --batch` per rev, and lazily loads new streams only when a shrink candidate needs the relocation check; `diagnose_event_stream_history` shares the fix.

Changed files:
- [src/sase/bead/_stream_integrity_git.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/src/sase/bead/_stream_integrity_git.py): added `stream_paths_at_rev` and `batch_show_texts`; `streams_at_rev` reimplemented on top (2 subprocesses).
- [src/sase/bead/_stream_integrity.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/src/sase/bead/_stream_integrity.py): guard and diagnose use the narrowed reads plus `_read_new_streams` for relocation checks.
- [tests/test_bead/test_stream_integrity.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/tests/test_bead/test_stream_integrity.py): new regression test for bounded reads, shrink refusal, and relocation allowance.

Verification observed: focused suite 19 passed; scratch probe with 61 streams showed an append uses 2 `ls-tree` + 2 batched reads with 0 `git show` (vs ~6,850 for 1,712 streams before); shrink refused, relocation allowed, diagnose names the stream. `just check`: fmt/ruff/mypy pass; symvision fails identically on the clean tree (pre-existing, corroborated with +1 on sase-17l rather than a new bead).
