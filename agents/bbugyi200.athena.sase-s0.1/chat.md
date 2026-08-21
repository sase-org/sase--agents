# Chat History - ace-run (sase-s0.1)

- **TIMESTAMP:** 2026-08-21 20:58:24 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-s0.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-s0.1, bead=sase-s0.1)
%clan(sase-s0, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-s0.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-s0.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-s0.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-s0.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the relevant SASE skills so I can complete sase-s0.1 without changing status by hand.

The bead is a phase for typed host-catalog completion and hidden-directive LSP presentation. Next I’ll read the plan, bead page, and the relevant SASE memory.

Phase 1 lives in the linked `sase-core` repo. I’ll open it through `/sase_repo`, then load bead notes, memory, and the existing completion/LSP code.

The linked `sase-core` repo is open. Next I’ll map the editor-helper, finalizer candidate, and LSP completion surfaces this phase has to extend.

I’ll read the agent-catalog and LSP conversion patterns next so the new finalizer catalog can follow the same contract and cache behavior.

I have the contract and the existing agent-catalog/LSP patterns. Next I’ll add the typed finalizer catalog, refine candidate building, and wire a dedicated LSP conversion path while keeping `%final` hidden.

Closed **sase-s0.1** (`Shared finalizer completion and LSP contract`). The parent epic **sase-s0** is still open.

Phase 1 lives in the linked **sase-core** repo. `%final` stays hidden from name completion until Phase 3.

**Shared contract**
- Versioned `finalizer-catalog` helper wire (`schema_version` 1) with additive instance metadata: id, provider, required/default, dependencies, retry policy, documentation.
- Mixed-version JSON still deserializes; unknown extra fields are ignored.
- The method is on `HelperHostBridge`, `DynHelperHostBridge`, command-backed and static bridges.

**Candidate builder**
- Configured instances sort required → remaining defaults → optional, then `none`.
- `!` produces prefixed removal labels and insertions.
- Required instances are omitted from remove completion.
- `none` is omitted when any required instance exists.
- Replacement stays on the active clause (colon, parenthesized, repeated), including UTF-16-adjacent text.
- Prefix matching is case-insensitive.

**LSP**
- Independent catalog cache with the usual blocking-worker timeout, short TTL, stale-on-error fallback, warn-once, and config-watch invalidation.
- Catalog is fetched only for `%final` argument contexts, not via `agent-catalog`.
- Dedicated conversion path: item kinds, stable `sortText`, policy/provider `labelDetails`, Markdown docs, UTF-16 text edits.
- Colon and parenthesized snippets exist (`%final:${1:instance}` and `%final(${1:instance}, ${2:instance})`) but are not advertised while the name is hidden.

Verified with **sase-core `just check`** (fmt, clippy, full workspace tests). No leftover `--epic-symbol` entries. Declared a Conventional Commit on the dirty sase-core tree.
