# Chat History - ace-run (research.1o.cld)

- **TIMESTAMP:** 2026-09-08 10:07:10 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1o.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260908_094401.md`

## Prompt

%id(cld, clan=research.1o) %m:@opus_or_grok 
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1o.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

Artifact link files frequently cause merge conflicts that
sase agents need to resolve.

- See the `research.1n.cdx` sase agent for an example of one such agent (i.e. an agent
  that had to resolve an artifact link merge conflict).
- These link files are created frequently so these merge conflicts should ideally never
  happen.
- We've already done a considerable amount of work to make bead conflicts infrequent so
  you MAY be able to take inspiration from that.

Can you do some research with the goal of helping me decide the best way to implement
this (make artifact link conflicts nearly impossible--if not completely impossible)? End
your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by understanding the artifact link file format and the existing bead conflict-avoidance work.

Now I have the full picture. Writing the report.

Research complete.

**Report:** `sase/repos/research/202609/artifact_link_conflict_elimination__b.md`
**Registered:** `file:explicit:e94c860aa400ceb91ce6f134` (label `research:202609/artifact_link_conflict_elimination__b.md`)

## Core finding

This isn't a merge problem, it's a **write-topology problem**. `sase artifact read` eagerly writes a durable row into the agent's *own ephemeral workspace clone* (`artifact_cli/read.py:283`) — and every agent that reads a popular artifact writes the *same path*. The `flock` sentinel guarding that write lives inside each clone, so it gives zero mutual exclusion for the case that actually conflicts. Swarm siblings finalize seconds apart; I measured link commits to the same hot index **44 seconds apart**.

Neither rebase path can auto-resolve it: `_git_commit_dispatch._all_bead_conflicts` and `_repair_or_abort_rebase` both bail unless *every* conflicted file is under `beads/`. `links/**.json` has no automated resolution path at all.

Measured: 127 of 451 research-sidecar commits (28%) are `chore(artifact-links)`; the hottest index has 17 separate ones.

## Key leverage

Two things I didn't expect going in:

1. **Half the same graph is already conflict-safe.** `artifact_link_beads.py` stores bead endpoints as `LinkAdded`/`LinkRemoved` events on append-only streams. Only the *document* half uses a mutable JSON array. This is finishing an existing architecture, not starting one.
2. **The union-merge objection that killed it for beads doesn't transfer.** Beads rejected it because "same ID, two versions" is corruption. Link rows are facts keyed by `(source, relation, target)`, the upsert is idempotent, and `unique_rows()` already dedups — "keep both" is the *correct* merge here.

I verified merge behavior empirically rather than assuming: `merge=union` cleanly resolves both add/add (the exact `research.1n.cdx` failure) and modify/modify, on `merge` **and** `rebase`, with no per-clone `git config`. It does **not** resolve delete/modify, and it produces different line orders on merge vs rebase — both constrain the design.

## Recommendation

Three phases, leading with the one that makes conflicts *structurally impossible* rather than merely rare:

- **Phase 1 (days):** a semantic `links/` resolver mirroring `bead/conflict_resolver.py`, wired into the same two rebase paths. Stops the bleeding, no migration.
- **Phase 2 (the real fix):** agents leave the write path — enqueue-only into the existing outbox, one serialized host drain into the hidden host-owned clone that landed *today* under `sase-y3.3`. Push rejection triggers **replay, not merge** (sound only because the upsert is idempotent). An agent's clone never has `links/` dirt, so the conflict cannot be constructed.
- **Phase 3:** append-only JSONL + tombstones + `links/**/*.jsonl merge=union` so the human and cross-machine lanes self-heal without SASE driving the rebase.

Main cost I'd flag: under Phase 2, an in-agent `link add` reports *queued* rather than *published* — a real semantics change for the ~8% manual traffic, mitigated because the machine-local aggregate (already the default source for `link list`) updates immediately.

I explicitly recommend **against** a custom git merge driver — it needs per-clone `git config`, which is the distribution problem the bead work deliberately avoided.
