# Chat History - ace-run (research.v.cdx)

- **TIMESTAMP:** 2026-07-30 16:35:16 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.v.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260730_161933.md`

## Prompt

%clan(research.v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to allow users to customize sase finalizers
#gh:gh_sase-org__sase via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution.]]) %id:research.v.cdx
%wait(priority=20) %model:@research_a I want to allow users to customize sase finalizers
via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the existing finalizer, directive/config/plugin architecture, and the `sase-be` epic, then compare implementation options and finish the report with a concrete recommendation. I’m using the repository, bead, and audited-memory skills because this crosses into the research sidecar, bead context, and prompt-directive rules.

The current design is a single provider-neutral commit finalizer wired into launch handling, while `%` directives are parsed and stripped before the model sees them. I’m now mapping exactly where that single-finalizer assumption leaks through the launcher, persistence, CLI, plugin discovery, and tests.

Two important constraints are emerging: `%final` must be resolved at launch and persisted in run metadata (not re-read from mutable config at completion), and finalizer definitions should be data resources while execution remains a core orchestration concern. That keeps behavior reproducible and lets plugins contribute definitions without giving them control of the runner lifecycle.

The strongest option is now clear: a declarative finalizer registry plus a generic lifecycle runner, with `%final` acting only as a per-run selector. I’m documenting the exact directive semantics, manifest/script protocol, DAG behavior, variable flow, plugin packaging, migration from `commit.finalizer`, and the Rust/Python ownership boundary.

Research complete: [custom_finalizers_percent_final_design.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202607/custom_finalizers_percent_final_design.md)

The recommendation is a declarative finalizer registry with:

- `%final:name`, `%final:!name`, and `%final:none`
- dependency-ordered execution
- prompt → live variable reload → structured script execution
- plugin definitions through a new `sase_finalizers` resource entry point
- launch-time plan snapshots
- Rust-owned validation/planning and Python-owned execution
- migration of the post-`sase-be` commit finalizer into a built-in `commit` definition

The new Markdown file passes `git diff --check`; no source files were changed.

The research file was created by this session, so I’m handling the required post-completion commit now. I’m using the `sase_git_commit` skill because the finalizer explicitly requires the research-sidecar change to be committed.

The sidecar contains only the new research report, and the diff matches the requested analysis. I’ll commit exactly that file with a documentation-scoped message, then verify the branch is clean and synchronized.

Research completed and committed: [custom_finalizers_percent_final_design.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202607/custom_finalizers_percent_final_design.md)

Recommended design: a declarative finalizer registry with a SASE-owned dependency-aware runner, `%final` selectors, launch-time plan snapshots, live SASE-variable handoff, configurable prompt/script/retry behavior, and plugin-contributed definitions.

Commit `3ebde1f` (`docs: research customizable finalizers`) is pushed; the research repository is clean.
