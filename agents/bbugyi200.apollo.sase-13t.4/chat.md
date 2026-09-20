# Chat History - ace-run (sase-13t.4)

- **TIMESTAMP:** 2026-09-20 14:03:48 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-13t.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-13t, bead=sase-13t.4)
%model:@small
%auto
%w:sase-13t.3
%w(bead=sase-13t.3)
Can you complete the work for bead sase-13t.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13t.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13t.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13t.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Opened sase-core; now reading the release workflow and the heal-phase commit to match its conventions.

Now the workflow edits, tests, and docs.

Implementation is verified. Next I'll check for leftover epic symbols and get the finalizer context.

I added the pre-flight quota guard to the sase-core release workflow and closed `sase-13t.4`. Nothing has run in a real GitHub Actions job yet, because the workflow can't run until this is committed; `sase-13t.6` covers that.

The guard is a new script, `.github/scripts/pypi_quota.py`, run by a new "Check PyPI storage headroom" step in the `publish` job, just before "Publish to PyPI".
- **Over quota:** it fails before any upload, and the error gives the current size, incoming bytes, limit and overflow. It also points to `docs/pypi-retention.md` for the fix.
- **Incoming bytes:** only files PyPI doesn't already hold count. A heal of a partial release (with `skip-existing`) is therefore only charged for what it will upload.
- **Job summary:** every publish appends bytes used, bytes free after the upload, and roughly how many more releases fit, based on the newest ten releases.
- **PyPI API errors:** it logs a warning and continues to the upload, so the guard can't fail a good release.
- **Limit:** it is one value, `PYPI_PROJECT_LIMIT_BYTES` (10 GiB), in the workflow's `env` block. A unit test checks that `pypi_retention.py`'s copy of the limit agrees with it. If PyPI raises the limit, change both.
- **Docs:** I added a "Pre-flight quota guard" section to `docs/pypi-retention.md` and an entry in the workflow header comment.

Checks I ran:
- `./scripts/check.sh` passes: fmt, clippy, cargo test, and 37 script tests, 14 of them new.
- I ran the script against the live PyPI project (2.04 GiB used). With a 75 MB file it passed and printed the summary; with a 2 GB limit it exited 1 with the numbers and remedy.
- The workflow YAML parses.

The changes are in the sase-core repo and were handed to the host commit finalizer, so I haven't confirmed the commit landed. `sase bead epic-symbols` reported no leftover entries. I closed the bead myself with `sase bead close` and declared `keep` to the finalizer, so it doesn't close it again.
