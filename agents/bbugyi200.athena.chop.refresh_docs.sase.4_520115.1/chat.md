# Chat History - ace-run (chop.refresh_docs.sase.4_520115.1)

- **TIMESTAMP:** 2026-08-17 17:32:01 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.4_520115.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.4_520115.1, tribe=chop)
%wait(runners=0)
Refresh the documentation for sase.

Review the current repository behavior and the changes since the last documentation
refresh. Update user-facing documentation so it is accurate, complete, and clear to
someone new to the project. You may only create, modify, or delete documentation
files, such as Markdown or other docs-tree content, READMEs, and doc-adjacent assets.
You MUST NOT create, modify, or delete source code, tests, build configuration, or any
other non-documentation file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll start by understanding the current state of the docs and what's changed since the last documentation refresh.

Now I'll start making the documentation updates. First, the Perf runbook, which has several definitions that no longer match the code:

Now the Statistics tab documentation in `docs/telemetry.md`:

Now the ACE Statistics/Perf summary in `docs/ace.md`:

Now `docs/cli.md` — the bare-group list defaulting:

Now `docs/beads.md` for the `sase bead work` BLOCKED preview rows:

Now the `sase update` completion refresh in `docs/plugins.md`:

Documentation refresh is complete. All changes are documentation-only (Markdown plus the docs site nav); no source, test, or build files were touched.

## What I reviewed

78 commits since the last docs refresh (`a6c09c88b`, 2026‑08‑16), separating commits that already shipped docs from those that didn't, then verifying each remaining user-facing change against the code and — where possible — against the live CLI in this workspace.

## What changed

**Corrections (docs disagreed with code):**

- `docs/perf_runbook.md` — the percentile claim was wrong: log-derived numbers use nearest-rank, but telemetry-derived rows and the Agent/LLM p95 tiles are interpolated histogram-bucket estimates. Also added a per-tile value table (Stalls now counts stalls only, with hitches in the detail line; Launch is p95, not a median), the grouping-dependent count-column labels, the missing Share column under subsystem grouping, and the "Perf counts aren't comparable to run counts elsewhere" rule.
- `docs/telemetry.md` — All-time range label, Overview zero-bucket trimming and 96-bucket aggregation, per-view empty states, the two different Overview success definitions, Activity/Projects truncation disclosure, Activity honoring the project filter.
- `docs/configuration.md` — the keymap doc claimed one intentional duplicate-key pair; there are seven. Added the full table (`E`, `.`, `X`, `L`, `a`, `d`, `/`) and the actual validation behavior.
- `docs/cli.md` — the bare-group `list` defaulting list was incomplete (missing `sase glossary`, `sase repo`, `sase flag`, `sase agent`, `sase artifact`, `sase monitor`, `sase plan`); added the delegation notice and the advisory `completion` doctor group.
- `docs/completion.md` — `sase doctor -C completion.registration` is rejected without `-D/--deep`; the doc showed it without the flag. Added the shipped value kinds and the `-l`/`-p` flags.
- `docs/llms.md` — `honor_reset_hint` now parses four forms including absolute timestamps.
- `docs/memory.md` — documented the actual `sase glossary` project-inference constraint and the `-p` workaround (see bug below).

**New coverage:** memory-drift foreign-build warning (`init.md`), `sase bead work` BLOCKED cleanup rows (`beads.md`), unknown-`#ref` launch warnings (`xprompt.md`), `,x` forced-reuse relaunch (`ace.md`), completion refresh on `sase update` (`plugins.md`), `sase completion install` in the README/INSTALL onboarding path, and `agents_sidecar.md` added to the site nav (it was built but unreachable from the sidebar).

## Suspected code bug (not fixed — docs-only scope)

`sase glossary` cannot infer its project from a numbered managed workspace checkout. From `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12`, `sase glossary read Stitch -r "…"` exits 1 with `no enabled project matched the active workspace`, while `sase repo list` and `sase memory list` resolve the same directory to project `sase`. Cause: `_record_for_workspace()` in `src/sase/xprompt/glossary_catalog.py:314` only matches a cwd under the ProjectSpec's primary `workspace_dir` and doesn't consult the workspace registry. This hits every agent that follows the generated `**GLOSSARY TERMS:**` instruction, since agents run from numbered workspaces; `-p <project>` works as a workaround, which I documented.

## Verification

- `just check` — exit 0 (every lint gate, SASE validation, scoped tests).
- `just docs-check` — mkdocs strict build passes.
- `just fmt-md-check` — prettier clean.

I'll commit the documentation changes I made in this session.

These are my changes from this documentation refresh. Let me re-verify the doc checks still pass, then commit.

Both doc checks pass. Now committing via the sase commit skill.

Committed and pushed. Working tree is clean and `master` is in sync with `origin/master`.

## Commit

`5411f5d4a docs: refresh user-facing docs against current behavior` — 15 files, +233/−57, all documentation or docs-site nav. No source, test, or build files touched.

## What the refresh covered

Reviewed the 78 commits since the last docs refresh (`a6c09c88b`, 2026‑08‑16), verifying each user-facing change against the code and, where possible, against the live CLI in this workspace.

**Corrections where prose disagreed with code:**

- `docs/perf_runbook.md` — the percentile claim was wrong: log-derived numbers use nearest-rank, but telemetry-derived rows and the Agent/LLM p95 tiles are interpolated histogram-bucket estimates. Added a per-tile value table (Stalls counts stalls only, hitches live in the detail line; Launch is p95, not a median), grouping-dependent count-column labels, the Share column under subsystem grouping, and the "Perf counts aren't comparable to run counts elsewhere" rule.
- `docs/telemetry.md` — All-time range label, Overview zero-bucket trimming and 96-bucket aggregation, per-view empty states, the two different Overview success definitions, Activity/Projects truncation disclosure, Activity honoring the project filter.
- `docs/configuration.md` — the keymap section claimed one intentional duplicate-key pair; there are seven (`E`, `.`, `X`, `L`, `a`, `d`, `/`).
- `docs/cli.md` — the bare-group `list` defaulting list was missing seven groups.
- `docs/completion.md` — `sase doctor -C completion.registration` is rejected without `-D/--deep`; the example omitted the flag.
- `docs/llms.md` — `honor_reset_hint` now parses four forms including absolute timestamps.

**New coverage:** memory-drift foreign-build warning, `sase bead work` BLOCKED cleanup rows, unknown-`#ref` launch warnings, `,x` forced-reuse relaunch, completion refresh on `sase update`, `sase completion install` in onboarding, and `agents_sidecar.md` added to the site nav (it built but was unreachable from the sidebar).

## Verification

`just fmt-md-check` and `just docs-check` (mkdocs strict) both re-run clean in this pass; `just check` passed earlier in the session.

## Suspected code bug — not fixed (docs-only scope)

`sase glossary` cannot infer its project from a numbered managed workspace checkout. From `sase_12`, `sase glossary read Stitch -r "…"` exits 1 with `no enabled project matched the active workspace`, while `sase repo list` and `sase memory list` resolve the same directory to project `sase`. Cause: `_record_for_workspace()` in `src/sase/xprompt/glossary_catalog.py:314` only matches a cwd under the ProjectSpec's primary `workspace_dir` and never consults the workspace registry. This affects every agent following the generated `**GLOSSARY TERMS:**` instruction, since agents run from numbered workspaces. `-p <project>` works as a workaround, which I documented in `docs/memory.md`.

## Unrelated warning surfaced by the commit

The commit succeeded, but `sase stitch create` reported 12 pre-existing quarantined agent-hood publication requests: `could not publish agent hood 'research': invalid hood relationships: duplicate or inconsistent container global name 'bbugyi200.athena.research.h.final'`. This predates my changes and is unrelated to them. Clearing it needs `sase agent sync --retry-quarantined`, which will likely keep failing until the duplicate `research` hood container name is reconciled — worth a separate look.
