# Chat History - ace-run (research.03.cdx)

- **TIMESTAMP:** 2026-08-08 12:00:22 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.03.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260808_113853.md`

## Prompt

%clan(research.03, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I wanted to find a reliable way to invoke xprompts by tag
instead of by name. Can you do some research to help me decide the best way to implement
this? Make sure you audit this codebase for existing xprompt tags and understand their
purpose/usage before diving too deep into your research. End your analysis with a
recommended solution.]]) %id:research.03.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I wanted to find a reliable way to invoke xprompts by tag
instead of by name. Can you do some research to help me decide the best way to implement
this? Make sure you audit this codebase for existing xprompt tags and understand their
purpose/usage before diving too deep into your research. End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the SASE memory-read skill to load the project’s xprompt design rules, then the repo skill to open the research sidecar through its supported path. I’ll audit the existing tags and resolution flow first, then compare implementation options and finish the report with one recommendation.

The existing metadata is not merely descriptive: tags already act as semantic selector keys in several internal workflows (notably bead work and epic landing). I’m tracing those call sites and the first-wins catalog behavior now, because tag invocation has to define ambiguity and override semantics rather than just add parser sugar.

A key reliability issue has surfaced: the current resolver infers source priority from Python dictionary insertion order, while catalog merges overwrite values without moving their keys. That can select the wrong tagged definition when a same-name override coexists with another tagged name. I’m checking the editor/Rust catalog side next so the recommendation covers one grammar and one resolution contract across CLI, TUI, and LSP.

The audit is complete. The design now centers on an explicit `#tag/<role>` selector, but only for tags whose policy says they identify one callable role; multi-match traits such as `vcs` and `rollover` remain metadata, and ambiguous selectors fail with provenance instead of silently choosing by iteration order. I’m writing the report with the inventory, failure modes, alternatives, and implementation/test outline.

The report is written and passes a whitespace/diff check. The audit also uncovered an existing correctness defect independent of the new syntax—tag priority can be wrong after same-name overrides—so I’m using the SASE new-task workflow to check for an existing bead and record it only if it is genuinely new.

The new-task workflow requires the report to be attached through a stable artifact reference when it materially supports the defect. I’m using the artifact-file skill for that registration before the duplicate and active-epic checks.

The bead store is busy with another active epic operation, so the duplicate-check/create commands are waiting on its normal serialization rather than failing. The report itself is complete; I’m letting the task-recording operation finish and will verify whether it created a new bead or found no writable slot.

The task was created as `sase-hi` and moved to ready, but the bead tool’s automatic publication step failed; the local bead state is correct but not yet durable outside this workspace. I’m checking the sync log and will retry only the publication of that already-created bead if the failure is transient.

This was an ID-allocation race, not a semantic duplicate: another agent created an epic with the same `sase-hi` ID from an older bead-store view. The sync preserved my local commit on a recovery ref. I’m removing only my colliding ready-update from the working branch, restoring the sidecar to the published epic state, then I’ll rerun the mandated duplicate check against the refreshed store before deciding whether to create a new task ID.

The ID race is resolved: the bead store renumbered the report’s task to `sase-hj`, and it is now published in `READY` state with the artifact attached. I’m doing the final repository-state check; no code was changed, so the project’s research-Markdown exception means a full `just check` is not applicable.

Research completed: [xprompt-tag-invocation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202608/xprompt-tag-invocation.md).

Recommendation: introduce `#tag/<role>` backed by an explicit, precedence-aware Rust-core resolver. It should reject trait tags like `vcs`/`rollover`, use VCS context where required, and fail visibly on ambiguity.

Also:

- Recorded the existing resolver-order defect as ready task `sase-hj`.
- Registered durable artifact `file:explicit:1d025d6168ae18d8ce0f7dde`.
- `git diff --check` passes. No code changed, so `just check` was not required.

I’m handling the finalizer only: I’ll use the required SASE commit workflow to commit the completed research report, then confirm the research repo is clean.

The report is staged through the required commit wrapper. It is completing the commit/push bookkeeping now; I’m checking that result synchronously before finishing.

Committed and pushed the research report:

[xprompt-tag-invocation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202608/xprompt-tag-invocation.md)

Commit: `fd0a79e` (`docs: research reliable xprompt tag invocation`)

Recommendation: implement `#tag/<role>` with an explicit, precedence-aware Rust-core resolver that rejects trait tags and reports ambiguities. The research repository is clean and synchronized with `origin/main`.
