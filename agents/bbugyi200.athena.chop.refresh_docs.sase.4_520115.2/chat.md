# Chat History - ace-run (chop.refresh_docs.sase.4_520115.2)

- **TIMESTAMP:** 2026-08-18 02:32:15 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.4_520115.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.4_520115.2, tribe=chop)
%wait:chop.refresh_docs.sase.4_520115.1
%wait(runners=0)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll start by finding the documentation changes made by the update agent.

Found it — the `refresh_docs` chop agent's commit `5411f5d4a`. Let me set up the environment and pull the full diff.

Now let me verify the claims against the actual code. Starting with the perf/telemetry claims.

Install finished. Now runtime verification of the CLI claims.

Let me check the doc-check tooling and re-read the changed sections for clarity.

All claims verified. Now applying the corrections I found. Starting with `docs/cli.md` — the nested-group list is missing a group added after that commit.

Now `docs/llms.md` — the reset-hint parser has five passes, not four, and that distinction is what makes the no-fall-through rule coherent.

Now `docs/ace.md` — the forced-reuse rewrite description is wrong for family members and overstates the plain case.

Now `docs/beads.md` — the prose field order doesn't match what actually prints.

Now `docs/configuration.md` — the table shows display keys, but the config file spells two of them differently, which would block a new user trying to act on it.

Now the two clarity fixes in `docs/telemetry.md` and `docs/perf_runbook.md`.

Both anchors resolve. Now running the repository's documentation checks.

Strict build passes. Final review of the complete diff:

The nested list forced a loose bullet list. Let me restructure so the detail sits outside the option list.

I'll add the detail as a proper subsection at the end of the Usage-Limit section.

I inspected the update agent's docs commit (`5411f5d4a`, the `refresh_docs` chop) and verified each changed description against the code.

## Verification results

Most of the refresh held up under checking. I confirmed against source and, where possible, at runtime:

- **perf_runbook** — tile table (Startup=median visible-ready, Stalls=stall count, Launch=p95), the `Freeze records by context` panel name, count-column labels (`LLM invocations`/`Agent runs`/`Count`), Share omitted under subsystem grouping, `—` vs `0`, and both percentile methods (nearest-rank in logs, histogram interpolation in telemetry — the in-app `?` help states both).
- **telemetry** — the exact All-time label string, 96-bucket aggregation with edge-zero trimming, per-view empty-state routing, and the two success-rate definitions (the legend does state both).
- **configuration** — all seven duplicate-key pairs and their defaults match `_CONTEXTUAL_APP_DUPLICATES` exactly.
- **cli / completion** — the 26 top-level list-defaulting groups are exactly right; `shipped_kinds()` returns precisely the 18 documented kinds; the delegation notice and the deep-check rejection message reproduce verbatim.
- **beads, xprompt, plugins, init, INSTALL** — verified, including exact toast/error strings.
- **memory** — the documented `sase glossary` limitation is real. I reproduced it: from this workspace it exits 1 with `no enabled project matched the active workspace`, and `-p sase` works.

## Corrections I made

Four claims were wrong or incomplete:

1. **`docs/ace.md`** — the forced-reuse description said family members get `%id(!name, clan=…)`. Family members actually get `family=`, the value is the member *suffix* not the full name, and a prompt with no `%id` isn't rewritten at all. Replaced with a form-by-form table.
2. **`docs/llms.md`** — said "four forms" for `honor_reset_hint`; the parser runs **five** passes. Zoned and bare clock times are separate, and that separation is exactly what makes the documented "no fall-through" rule coherent — as written it contradicted itself. Promoted to a `Reset-Hint Forms` subsection (the long bullet was also forcing the whole option list loose).
3. **`docs/cli.md`** — nested-group list was missing `sase bead task-type`, added after that commit. Also noted the behavior is parser-derived, so the list won't silently rot.
4. **`docs/beads.md`** — prose field order didn't match what prints (`ACTION (state) name bead=… reason`).

Clarity edits for new users: config-file spellings (`slash`, `full_stop`) alongside the displayed keys in the keymap table; a definition of "finished" in the success-rate contrast; and a cross-link from the Stalls tile to the existing threshold section rather than restating numbers.

**Checks run:** `just fmt-md-check` and `just docs-check` (mkdocs `--strict`) both pass. I also confirmed both new cross-reference anchors resolve in the built HTML. Only files under `docs/` are modified.

## Suspected code bug (not fixed — out of scope)

The one the previous agent flagged is still live, and I reproduced it. `sase glossary` cannot infer its project from a numbered managed workspace: `_record_for_workspace()` in `src/sase/xprompt/glossary_catalog.py:332` only matches a cwd under the ProjectSpec's primary `workspace_dir` and never consults the workspace registry. So `sase glossary read Stitch -r "…"` exits 1 from `sase_12/`, while `sase repo` resolves the same directory to project `sase` in its own header. This affects every agent following the generated GLOSSARY TERMS instruction, since agents always run from numbered workspaces. The `-p` workaround is now documented in `docs/memory.md`; a scoped agent should fix the inference itself.

Both doc checks pass. Committing now.

Committed as `ad18bc319`. Working tree is clean and level with `origin/master`; the commit contains only files under `docs/`.

## What the review found

I checked each description changed by the `refresh_docs` chop (`5411f5d4a`) against the code and, where possible, at runtime. Most of it held — the perf_runbook tile semantics and percentile methods, the telemetry bucket trimming and label strings, all seven duplicate-key pairs in configuration.md, the 26 list-defaulting groups and the 18 `shipped_kinds()` values in cli.md, and the beads/xprompt/plugins/init/INSTALL sections including exact toast text.

Four claims were wrong or incomplete and are now fixed:

1. **`docs/ace.md`** — forced-reuse rewrite. Family members get `family=`, not `clan=`; the keyword carries the member *suffix*, not the full agent name; and a prompt with no `%id` isn't rewritten at all. Replaced with a form-by-form table.
2. **`docs/llms.md`** — `honor_reset_hint` runs **five** parser passes, not four. Zoned and bare clock times are separate forms, and that split is exactly what makes the "commits to the first matching keyword, no fall-through" rule coherent — as written, the two statements contradicted each other. Promoted to a `Reset-Hint Forms` subsection.
3. **`docs/cli.md`** — missing `sase bead task-type`, which landed after the refresh.
4. **`docs/beads.md`** — the documented field order didn't match what actually prints (`ACTION (state) name bead=… reason`).

Clarity edits: YAML spellings (`slash`, `full_stop`) alongside the displayed keys in the keymap table, a definition of "finished" in the success-rate contrast, and a cross-link from the Stalls tile to the threshold section.

## Checks

`just fmt-md-check` and `just docs-check` (mkdocs `--strict`) both pass, run fresh before the commit. Both new cross-reference anchors resolve in the built site.

## Suspected code bug — not fixed

`sase glossary` can't infer its project from a numbered managed workspace. `_record_for_workspace()` in `src/sase/xprompt/glossary_catalog.py:332` only matches a cwd under the ProjectSpec's primary `workspace_dir` and never consults the workspace registry. I reproduced it: `sase glossary read Stitch -r "…"` exits 1 from `sase_12/` with `no enabled project matched the active workspace`, while `sase repo` resolves the same directory to project `sase`. This affects every agent following the generated GLOSSARY TERMS instruction, since agents always run from numbered workspaces. `-p sase` works and is documented in `docs/memory.md`; the inference itself needs a separately scoped fix. It's described in the commit body too.

One note on the commit: it succeeded and pushed, but prompt-archive publication was deferred because the agents sync lock was busy, and the project already had 12 quarantined agent-hood publication requests before this run. Clearing that needs `sase agent sync --retry-quarantined` — pre-existing and unrelated to these changes.
