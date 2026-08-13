# Chat History - ace-run (research.0g.cld)

- **TIMESTAMP:** 2026-08-13 18:40:52 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0g.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260813_182417.md`

## Prompt

%id(cld, clan=research.0g) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I would like to merge the functionality of sase monitors (see
the sase-kp epic bead) with sase procs (see the sase-lh epic bead) by adding support for
a new type of detatched proc that we will call "named procs" (aka "sase shells") that
will be powered by the `sase proc` command under-the-hood, but that is wrapped by a new
`sase shell` command (that more-or-less takes the place of the `sase monitor` command,
which should be removed).

Can you do some research with the goal of helping me decide the best way to implement
this? See the detached_proc_convergence.md file in the research sidecar repo for some
related research you should maybe know about. End your analysis with a recommended
solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by getting oriented — reading the related research and the two epic beads.

I have what I need. Writing the research report now.

Written to `sase/repos/research/202608/named_procs_and_sase_shell.md`.

## What I found

I read both epics' code end to end (`src/sase/monitor/` — 17 modules / 3,747 lines; `src/sase/tasks/` — 8 / 1,390), the Rust proc wire in `sase-core` (already renamed, schema v2), and both prior research notes. Two things reframed the problem:

**1. The prior research is partly stale, in your favor.** `monitor_command_substrate` ranked "extract the shared supervisor kernel" as item #15, explicitly gated on items 1–4 landing first. They've landed. `BoundedLogPipe` is *already* shared by both substrates, and the monitor supervisor now has the double-fork bootstrap, start-ack, launch barrier, process identity, dual timeouts, and guaranteed terminal marker. So the extraction is now well-founded, and it's less work than either report assumed.

**2. `sase monitor` fuses two separable things, and `sase shell` is the lever to split them.** A monitor is *a supervised named command* **plus** *an agent-lane attachment*. The first duplicates procs; the second (family membership, claim transfer, `#fork` follow-up) is the valuable monitor-specific part. Evidence the fusion costs you: `resolve_lane()` requires pre-existing agent artifacts, so **a human cannot start a monitor from a terminal** — host starts only work because epic launch *borrows the planner's lane*, and `epic_launch.py` carries a whole fallback-to-`submit_detached_task` path because of it.

## Recommendation

A **named proc** = a proc with a `name`. A **sase shell** = a named proc, *optionally* lane-attached. Four moves:

- **Promote the monitor's supervisor to the proc kernel** and delete `tasks/supervisor.py`. There's no axis on which the proc supervisor is better — it's smaller because it does less.
- **`name` is the store-wide dedup key** that `detached_proc_convergence` §3.2 called a blocking prerequisite for the TUI-proc migration. One field, two features — this epic *unblocks* that one.
- **Don't add a proc `kind`.** `name` and `artifacts_dir` are orthogonal nullable fields; `kind` already conflates ownership with attribution.
- **Keep the artifacts record for lane-attached shells** — dropping it would delete `%wait`, `#fork`, family roster, and `sase chats`. Two records, one writer, one ordering rule.

Two design points I'd flag as non-obvious: **don't auto-derive the name from the command** (two lanes running `just check-full` concurrently is normal and would collide — default the name to the *lane*), and **store a shell command as `["/bin/sh","-c","…"]`** so shell-ness needs no new wire field and shows honestly in `ps` and the Procs pane.

The note ends with a 9-phase sequence (starting after `sase-lh` closes), 7 risks, and 6 decisions I need from you — the load-bearing one being whether a single unified "what's running" list is worth an additive Rust wire change plus the dual-record rule. If it isn't, Option B (shared kernel, artifacts-only record) is a legitimately cheaper answer and I say so.

One naming caveat worth your attention: `sase shell` reads like "open an interactive shell," and these are explicitly TTY-forbidden batch commands. I recommend keeping the name but shipping `sase shell attach` and a clear TTY-refusal error, which make the metaphor honest rather than misleading.

I'll commit the research file now.

This is my file from this session. Committing it.

Committed and pushed.

**Commit** `1e5d703` — `docs(research): analyze named procs and the sase shell command`, adding `202608/named_procs_and_sase_shell.md` (576 lines) to the research sidecar. Working tree is clean and `main` is in sync with `origin/main`.

Two things worth flagging:

**A parallel note landed 11 seconds before mine.** Commit `4e31b6a` from agent `bbugyi200.athena.research.0g.cdx` added `202608/named_proc_shell_convergence.md` (658 lines) answering the same question — recommending a single proc supervisor with a "shell lifecycle profile." My commit rebased cleanly on top, so both notes are now in the repo. If that parallel run was intentional you have two independent takes to compare; if it wasn't, one of them should probably be consolidated the way `detached_proc_convergence.md` consolidated the earlier pair.

**The agent-hood publication outbox is backed up.** `sase_git_commit` warned that the project has 1 quarantined publication request (`agents sync lock is busy`), so the agent link written into this commit may not resolve yet. Clearing it is `sase agent sync --retry-quarantined` — I didn't run it since it touches shared state outside this task's scope.
