# Chat History - ace-run (research.0f.cld)

- **TIMESTAMP:** 2026-08-13 18:03:17 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0f.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260813_174823.md`

## Prompt

%id(cld, clan=research.0f) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase Sase procs, which are currently called "tasks" but will soon
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

I'll research this. Let me start by understanding the current proc/task architecture.

The sase repo working tree is clean — the only new file is the research note in the `research` sidecar, so no `just check` run is needed.

## Written to `sase/repos/research/202608/tui_procs_to_detached_procs.md`

**Your premise is correct.** `_validated_argv()` (`src/sase/tasks/runner.py:337-341`) rejects an empty argv for both supervised kinds, and it's not incidental — the supervisor's whole job is to `Popen` that argv. But the enforcement is Python-only: the Rust store's `validate_task()` deliberately omits `command` from its non-empty checks, so TUI rows land commandless legally. Empirically, **277 of 281 TUI rows in your live store (98.6%) have `command: []`**. The 4 exceptions are the ones that happened to call `TaskReporter.run()`.

Key findings beyond the verification:

**Two axes, not one.** `kind` conflates *ownership* (supervisor vs. TUI worker thread) with *attribution* (session or none). Migrating TUI procs collapses ownership; removing `-d|--detached` collapses attribution. The second is nearly free afterward — `--detached` becomes exactly `--session none`, which already exists. One behavior change to accept: `_ListScope.matches()` currently keeps `detached` rows in scope for every query while session-less rows depend on `include_unattributed`.

**57 call sites, ~24 proc types, three buckets.** ~13 map to real domain operations, ~6 already have a CLI equivalent (`sase gate answer`, `sase launch approve`, `sase bead <verb>`) and can flip almost immediately, and ~5 shouldn't be procs at all — `prompt-stash` has a *median lifetime of 0.09s*, and a detached proc pays 0.6–1.0s of startup (measured: `sase --version` = 0.31s min, `sase task list` = 0.62s, doubled for supervisor + child).

**The command is the easy half.** Four capabilities have no detached equivalent: `on_complete` callbacks (30+ sites, no per-row completion mechanism exists — only an aggregate count poll), store-wide dedup (`dedup_key`/`exclusive_scopes` are in-memory per-process; needs a new wire field and a coordinated schema bump since `TASK_WIRE_SCHEMA_VERSION` is checked for exact equality), closure capture over live TUI objects, and the typed in-memory log.

**On where the command lives:** distribute into existing domain groups (`sase patch sync/mail/revert/…`, `sase agent dismiss/cleanup/…`), not a new `sase ace` namespace and not a generic dispatcher. `sase ace` is a leaf command with an optional `query` positional — hosting subcommands there is a breaking parser change. More decisively, your own Rust-core boundary litmus test in CLAUDE.md ("would another frontend need this to match the TUI?") already prescribes this shape; the proc migration is just the forcing function. Cost: ~16–20 new public subcommands. I kept a hidden dispatcher as a ≤2-proc escape hatch.

Worth flagging: the highest-volume proc (`kill`, 89 rows, max 1232s) closes over live `Agent` objects, wire snapshots, *and* a bound TUI method used as a callback — that one needs a serialization contract before it can be commanded at all. And `sase-lh` touches every file this migration touches, so I recommend sequencing this as a separate epic starting after it closes.

I'll commit the research note. The finalizer lists the same path twice (linked repo and SDD sidecar resolve to the same directory), so this is one commit.

Confirmed: one untracked file, the research note I wrote this session. Committing with the skill.

Committed. The `research` repo is clean and in sync with `origin/main` (no divergence marker, so the push landed).

**Commit `327b2ac`** — `docs: research migrating TUI-attached procs to detached procs`

Added `202608/tui_procs_to_detached_procs.md` (538 lines), the research note from this session. The `-x` flag wasn't needed — the note was the only pending change in the repo, and the finalizer's two entries (linked repo and SDD sidecar) resolve to the same directory, so one commit covered both.

One non-blocking warning from the commit hook: prompt-archive publication was deferred because the agents sync lock is busy, and the project already has 1 quarantined agent-hood publication request. The primary commit succeeded; the agent-hood link recorded in the commit may stay unavailable until `sase agent sync --retry-quarantined` clears the outbox. I did not run that — it touches shared state beyond this commit, so it's your call whether to clear it now.
