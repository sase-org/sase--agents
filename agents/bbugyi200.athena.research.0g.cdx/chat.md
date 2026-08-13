# Chat History - ace-run (research.0g.cdx)

- **TIMESTAMP:** 2026-08-13 18:43:53 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0g.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260813_182417.md`

## Prompt

%clan(research.0g, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to merge the functionality of sase monitors (see
the sase-kp epic bead) with sase procs (see the sase-lh epic bead) by adding support for
a new type of detatched proc that we will call "named procs" (aka "sase shells") that
will be powered by the `sase proc` command under-the-hood, but that is wrapped by a new
`sase shell` command (that more-or-less takes the place of the `sase monitor` command,
which should be removed).

Can you do some research with the goal of helping me decide the best way to implement
this? See the detached_proc_convergence.md file in the research sidecar repo for some
related research you should maybe know about. End your analysis with a recommended
solution.]]) %id:research.0g.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I would like to merge the functionality of sase monitors (see
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

I’ll trace both epic beads, inspect the current `proc`/`monitor` implementations and tests, then open the research sidecar through the required repo workflow. I’m using the `sase_memory_read` skill for the project’s bead/glossary rules and `sase_repo` for the sidecar; those rules shape how I gather and cite the repository evidence.

The repository workflow requires that I use the path returned by `sase repo open`, so I’m resolving that sidecar now rather than reading the supplied path directly. I’m also loading the bead lifecycle/glossary context before querying the two epics.

The two epics are at different maturity points: monitors are fully implemented but still awaiting land, while the proc rename is actively split across phases. I’m going deeper on their plans and current storage/process boundaries so the recommendation accounts for in-flight work rather than treating either subsystem as static.

A useful architectural signal from the earlier report is that monitors and procs already duplicate supervision, IDs, logs, reconciliation, and termination—but monitors add agent-family projection, workspace handoff, timeout policy, and follow-up dispatch. I’m now checking which of those should become generic proc capabilities versus shell-only policy, because that boundary is the crux of a maintainable design.

The hardening work after the earlier report materially changes the answer: monitors now have the stronger supervisor (startup ack, launch barrier, process identity, bounded byte logs, total/idle timeouts, crash reconciliation). The convergence should therefore move those guarantees into the proc engine—not discard them in favor of today’s simpler proc supervisor. I’m inventorying the projection and migration surface next.

The recommended shape is now clear: make the proc record/supervisor authoritative, but retain a thin agent-family “shell member” projection so lane ordering, `%wait`, chat lineage, workspace handoff, and follow-up agents keep working. I’m writing the report with the data model, transaction order, CLI contract, alternatives, migration strategy, and verification matrix—and will end it with a concrete recommendation.

Research is complete: [named_proc_shell_convergence.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/named_proc_shell_convergence.md:1).

Core recommendation:

- Model namedness as an optional immutable Proc field, not `kind="named"`.
- Make `sase shell` a direct service-level facade over `sase.procs`.
- Move the hardened monitor supervisor guarantees into the proc engine.
- Preserve agent-family behavior through a thin shell-member projection referencing the canonical `proc_id`.
- Implement this as a separate schema-3 epic after `sase-kp` and `sase-lh` land.
- Remove the public `sase monitor` command while retaining compatibility for historical monitor records.

The new Markdown file passed whitespace/diff validation. No primary-repository code was changed.

I’m finalizing the research artifact now. The finalizer explicitly requires the `sase_git_commit` workflow, so I’m using that skill to commit the report in the research sidecar, then I’ll confirm the repository is clean.

The sidecar contains only the new 658-line research report, and its recommendation ends with the requested concrete implementation choice. I found no unrelated changes, so the commit can safely include the whole sidecar working tree.

The commit workflow is running its repository sync and validation now. I’m staying in this turn until it finishes, then I’ll verify both cleanliness and upstream status as required.

The VCS provider has already reported a successful `create_commit`; the wrapper is still completing its post-commit bookkeeping. I’m continuing to poll it in-process rather than leaving any background work behind.

The commit itself is present as `4e31b6a` and the branch is already clean and synchronized. The wrapper has not exited, so I’m checking its remaining child process rather than assuming the successful provider message means all bookkeeping has finished.

Committed [named_proc_shell_convergence.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/named_proc_shell_convergence.md) as `4e31b6a`.

The research repository is clean and synchronized with `origin/main`. The commit workflow noted one pre-existing quarantined agent-publication request, which does not affect the report commit.
