# Chat History - ace-run (research.0f.cdx)

- **TIMESTAMP:** 2026-08-13 18:06:42 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0f.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260813_174823.md`

## Prompt

%clan(research.0f, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] Sase procs, which are currently called "tasks" but will soon
be renamed to "procs" (see the sase-lh epic bead) currently support processes that are
attached to the TUI and ones that are detatched. I would like to change this and migrate
all of the current procs that attach to a TUI to detached procs (we would then remove
the `sase task run` command's `-d|--detatched` option). I think the problem with this is
that the procs that attach to a TUI do not necessarily have a command associated with
them, which should be required for a detached proc (verify this is true).

Can you help me do some research into what it would take to migrate every existing proc
that attaches to a TUI to a detached proc by creating an associated command, if
necessary for that proc? (Maybe a `sase` sub-command or sub-sub-command? Think hard
about where this command should live.)]]) %id:research.0f.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase Sase procs, which are currently called "tasks" but will soon
be renamed to "procs" (see the sase-lh epic bead) currently support processes that are
attached to the TUI and ones that are detatched. I would like to change this and migrate
all of the current procs that attach to a TUI to detached procs (we would then remove
the `sase task run` command's `-d|--detatched` option). I think the problem with this is
that the procs that attach to a TUI do not necessarily have a command associated with
them, which should be required for a detached proc (verify this is true).

Can you help me do some research into what it would take to migrate every existing proc
that attaches to a TUI to a detached proc by creating an associated command, if
necessary for that proc? (Maybe a `sase` sub-command or sub-sub-command? Think hard
about where this command should live.) Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the current attached/detached task model, inspect the `sase-lh` epic for the upcoming terminology and constraints, inventory every attached proc definition, and then design the command placement and migration path. I’m using the SASE memory, patch/bead, repository, and artifact workflows because the answer depends on project-specific lifecycle rules and the requested report lives in the separate research repository.

The project rules require audited reads of bead terminology and the long-term bead lifecycle note before I inspect `sase-lh`. I’m also recording the patch and artifact workflows now; the artifact workflow will determine whether the final committed-style research document needs a separate `file:` snapshot.

The epic confirms the rename is already split across Rust core, Python package/state, CLI, runtime, and TUI phases; the command-tree rename is phase 3 and the tracked-runtime rename is phase 4. I’m now comparing those planned boundaries against the actual task schema and every call site that creates an attached task, so the report can distinguish mechanical migrations from procs that need a real command surface.

The key premise is confirmed, with one important nuance: ordinary `sase task run` jobs are already OS-detached; `--detached` only changes ownership/scope. The truly TUI-bound jobs are `kind="tui"`, and they can be recorded with `command=[]`. In fact, ACE submits the Python callable first and only some workers discover a subprocess argv later, while the durable mirror never reliably updates that command.

The inventory is larger than the four proc primitives suggest: 54 static submission calls across 37 ACE files, one of which is the generic adapter, leaving 53 producer/wrapper sites. I’m consolidating those into domain command families now; the report will also cover the missing cross-process result, deduplication, progress, and completion-callback mechanisms needed to preserve today’s behavior.

The report is now written and formatted. Its main recommendation is to keep `sase proc` as the execution control plane while placing executable operations under their owning domains—`sase patch`, `sase agent`, `sase gate`, `sase bead`, `sase plugin`, and so on. It also identifies a few current rows, especially browser-open and tiny local mutations, that may be better reclassified as ordinary non-durable Textual workers instead of inventing fake commands for them.

I’m doing the final durability and reference checks now.

Research complete: [detached_procs_migration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202608/detached_procs_migration.md).

Key findings:

- Detached procs require non-empty argv; TUI-owned procs can record `command=[]`.
- `sase task run` is already OS-detached regardless of `--detached`; the flag only controls session ownership and visibility.
- The migration affects 53 ACE producer/wrapper sites across 37 files.
- Domain commands should live under `sase patch`, `sase agent`, `sase gate`, etc.; `sase proc` should remain the lifecycle/control plane.
- Atomic deduplication, structured request/result sidecars, cross-process progress reporting, and a non-owning ACE completion watcher are prerequisites.
- This should be a follow-on epic after `sase-lh`.

A durable snapshot was also registered:

- Ref: `file:explicit:564bf37d65b68c71b7bd6d97`
- ID: `explicit:564bf37d65b68c71b7bd6d97`
- Source: the research file above
- Stored path: `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260813174823/detached_procs_migration-4bf5432ab2c8.md`

The finalizer confirms the research file is my prior output, so I’m using the required SASE git-commit workflow now. I’ll commit the research repository change, then verify that repository is clean before handing it back.

The repository contains exactly one pending file—the requested 547-line report—and its contents match the completed research scope. I’m committing it as a documentation-only change with no exclusions.

Committed the research report successfully:

- Report: [detached_procs_migration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202608/detached_procs_migration.md)
- Commit: `f0880dc docs: research migration to detached procs`
- Repository is clean and synchronized with `origin/main`.
