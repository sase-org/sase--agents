# Chat History - ace-run (research.u.cdx)

- **TIMESTAMP:** 2026-07-30 12:19:09 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.u.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260730_120101.md`

## Prompt

%clan(research.u, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've been thinking a lot lately about ways I can improve sase beads. Can you do some research with this goal in mind? End your analysis with a list of ranked recommended improvements.]]) %id:research.u.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I've been thinking a lot lately about ways I can improve sase beads. Can you do some research with this goal in mind? End your analysis with a list of ranked recommended improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll use the SASE repo skill to resolve the research sidecar safely, then the beads skill to map the current feature set and command model before comparing it with established issue-tracking and agent-workflow systems. I’ll finish the report with a ranked, evidence-backed improvement list and save it in the requested month directory.

The feature surface is already much richer than a basic tracker: event-sourced history, dependency graphs, typed closure resolutions, atomic append-only notes, Git synchronization, executable epics, and hosted pages are all present. I’m now separating “missing capability” from “existing capability that is hard to use or operate,” since the highest-value improvements are likely in coordination, querying, and observability rather than more CRUD commands.

Two concrete internal signals now stand out. First, the live store has 2,417 beads but only 16 active, while `stats` exposes only totals; there is almost no analytical help for understanding throughput, rework, stale work, or bottlenecks. Second, all events for an epic lineage share one root JSONL stream, so parallel phase agents contend on exactly the same Git file—the architecture’s hottest write path. I’m checking external systems for proven solutions that fit SASE’s event-sourced model without importing their entire complexity.

I found two earlier July bead research packages in the research sidecar. I’m reviewing them now so the new report can explicitly distinguish ideas already implemented, ideas still valid, and genuinely new recommendations; this should prevent the final ranking from simply rediscovering last week’s backlog.

The ranking has shifted materially from the July 14 and July 25 reports because many of their recommendations have since landed. The new report will lead with three next-stage problems: lossless concurrent journaling, truly atomic work acquisition and recovery, and eliminating the per-epic Git hotspot. It will treat richer querying, completion evidence, and flow analytics as the next layer, while keeping Dolt/daemon-style expansion out of scope.

The report is written and formatted. Its final ranking deliberately does not repeat the already-landed July work: it now prioritizes lossless journal events, atomic run-bound claims, and a conflict-minimal event layout, followed by query/selection, structured completion evidence, analytics, relations, plan reconciliation, and cross-project references. I’m doing the final integrity check on the saved file and its ending now.

Created the research report:

[SASE Beads: Next-Stage Improvements](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202607/sase_beads_next_stage_improvements_20260730.md)

The top-ranked improvements are:

1. First-class append-only journal events.
2. Atomic, run-bound ready-work claiming.
3. Conflict-minimal canonical event storage.

The report incorporates live-store measurements, prior July research, current implementation changes, and external primary sources. Formatting and file integrity checks pass. No primary-repository files were modified.

I created the listed research file in this session, so I’m handling the finalizer now. I’ll use the SASE git-commit skill to commit only that report in the research sidecar, then verify the repository is clean.

The research sidecar has exactly one uncommitted change—the new report—and no unrelated edits. I’ve confirmed the report ends with the requested ranked recommendations; I’m committing that file alone with a documentation-scoped message.

Committed and pushed the research report:

- Commit: `c8ad004 docs: research next-stage bead improvements`
- Repository is clean and synchronized with `origin/main`.
