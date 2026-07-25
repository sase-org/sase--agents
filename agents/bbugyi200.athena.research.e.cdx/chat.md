# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 14:25:36 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.e.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_141316.md`

## Prompt

%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I want to generalize the concept of plan / question /
launch notifications so all of them use the same structure and sase notification
constructor. We should use the existing `sase notify create` command for this,
which will need to be signifigantly enhanced I think. As a part of this change,
I intend to remove the (never used) dynamic `improve_plan` and `tester` family
member hooks (I'm not even sure how they work, but I'm pretty sure we will need
to do something about them to progress with this initiative).

Can you do some research to help me understand what this task entails? End your
analysis with a list of questions that, if answered correctly, would allow you
to confidently design and implement this functionality. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the current plan, question, and launch notification paths; inspect `sase notify create`; and identify how the dynamic `improve_plan`/`tester` family hooks interact with them. I’m using the SASE notification skill for the domain-specific commands, the repository skill because the requested report lives in the research sidecar, and audited memory reads for the xprompt/agent-launch rules that govern this area.

The first pass confirms there are three separate producer paths today: specialized sender helpers for plan/question/launch, a generic JSON-driven CLI handler, and action-specific response protocols. I’m narrowing this to the exact payload fields and side effects each path owns, because that is where a shared constructor can either simplify the design or accidentally erase necessary behavior.

The generated `/sase_questions` and `/sase_run` contracts are part of this surface, so the project’s generated-skill rules now apply. I’m pausing the code trace briefly to read that audited guidance before treating those files as migration targets.

Because the proposed design materially expands an existing CLI command, the project’s CLI compatibility rules are also relevant to the research. I’m incorporating them now so the report captures parser, JSON-output, documentation, and test obligations—not just Python call sites.

A useful connection has emerged from the project’s prior July research: the custom lifecycle roles are not merely extra UI toggles; they are an alternate launch orchestration system embedded in the plan-chain evaluator. I’m checking the recent family-to-xprompt-swarm migration work now, because removing those hooks safely likely means replacing their orchestration responsibility with generalized launch/request notifications rather than simply deleting two example YAML files.

The generic creator currently feeds the Rust-backed store without validating or normalizing most field types, while the actionable request semantics remain Python-side. Since a shared schema may cross the project’s backend boundary, I’m opening the Rust core through the required repository audit path before deciding whether it is truly in scope.

The Rust core confirms that plan, question, and launch are separate public wire variants—not just Python implementation details. A truly common actionable-notification schema would therefore affect mobile clients and transports. I’m checking the linked Telegram plugin next so the report can distinguish “central constructor refactor” from “wire-breaking protocol unification.”

The lifecycle distinction is now clear: plan and question requests terminate the current model subprocess and resume through the runner; launch requests remain asynchronous and ask the requesting agent to poll. A common envelope can cover creation and response files, but “all the same structure” cannot safely imply identical continuation behavior. I’m verifying whether any custom lifecycle definitions are active on this installation and then I’ll turn the findings into a migration boundary.

The report’s central recommendation is a staged design: first make `sase notify create` and an in-process service produce one versioned interaction bundle while preserving today’s action names; then decide whether to collapse the public Rust/mobile/Telegram wire to one generic action. This separates the valuable constructor unification from an avoidable flag-day protocol break. I’m writing that analysis now, including the full removal surface for custom lifecycle roles and ending with the decisions needed for implementation.

The report is complete and ends with 18 design questions. Its first formatting check found only Markdown layout differences, so I’m applying the repository’s available formatter and then doing a final content/status verification; no product source files are being changed.

Created [unified_interactive_notifications_research.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202607/unified_interactive_notifications_research.md>).

It covers:

- Current plan, question, and launch request lifecycles.
- Required `sase notify create` enhancements.
- Recommended common interaction envelope and adapters.
- Rust/mobile/Telegram compatibility implications.
- Full removal scope for the unused lifecycle-role hooks.
- A staged migration and validation strategy.
- 18 design questions required before implementation.

The Markdown passes Prettier validation. No product source files were changed.

The report file is my session’s change, so I’m handling the finalizer now with the required SASE commit workflow, scoped only to that new research file. Afterward I’ll verify the sidecar checkout is clean.

The sidecar contains only the intended untracked report. I’ve confirmed it documents the requested architecture, migration surface, and implementation questions; I’m committing it as a documentation-only change.

Committed the research report to the sidecar repository.

- Commit: `f727e83 docs: research unified interactive notifications`
- File: [unified_interactive_notifications_research.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202607/unified_interactive_notifications_research.md>)
- Repository is clean and synchronized with `origin/main`.
