# Chat History - ace-run (research.0s.cdx)

- **TIMESTAMP:** 2026-08-20 09:49:30 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0s.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260820_093205.md`

## Prompt

%clan(research.0s, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] Sase's commit finalizer is currently a hard-coded part of the
system.

- I would like to generalize the concept of sase's finalizer so users can define their
  own finalizers via plugins and/or configuration.
- I think we should also consider supporting a new `%final` directive to override the
  finalizer for a specific sase agent.
  - I'm thinking this could then default to something like `%final:commit` if not used
    explicitly in a sase agent's prompt?
- One way to implement this is to add a new `/sase_final` xprompt skill and tell agents
  that they must invoke it at the end of every turn (sase agents that get intentionally
  terminated early--when using their /sase_plan or /sase_monitor skills, for
  example--are exempt).
  - The finalizer could then force a new turn if the agent doesn't use /sase_final for
    some reason (and then fail if the agent doesn't use /sase_final on that turn
    either).
  - This skill could instruct agents how to use a new `sase final` command to persist
    some JSON data somewhere that is associated with that agent and can be read,
    validated, and acted on (e.g. by creating commits, creating task beads, etc...) by
    the finalizer.
  - We should figure out a way for agents to specify the commits/stitches that should be
    created for each repo that contains files that that agent modified using the
    `sase final` command. We'll also need to be careful that we don't break sase's
    current merge conflict workflow (e.g. make sure merge conflicts are still always
    caught and handled by sase agents--when they can't be auto-resolved). Think hard
    about how to get this right.
    - One new requirement we should add: sase agents that do not commit to certain repos
      should be required to specify a refusal reason via the `sase final` command (so we
      have some more insight when the finalizer fails because an agent refused to commit
      detected file changes).
- Sase's commit finalizer is such a critical part of sase that I think this feature
  belongs behind a feature flag.

Can you do some research with the goal of helping me decide the best way to implement
this? We've already done some related research on this in the past so make sure you find
and review that before starting your own investigation. That research is old though so
don't rely on it as a source of truth. End your analysis with a recommended solution.]]) %id:research.0s.cdx
%wait(priority=20) %model:@research_a 
#gh:gh_sase-org__sase Sase's commit finalizer is currently a hard-coded part of the
system.

- I would like to generalize the concept of sase's finalizer so users can define their
  own finalizers via plugins and/or configuration.
- I think we should also consider supporting a new `%final` directive to override the
  finalizer for a specific sase agent.
  - I'm thinking this could then default to something like `%final:commit` if not used
    explicitly in a sase agent's prompt?
- One way to implement this is to add a new `/sase_final` xprompt skill and tell agents
  that they must invoke it at the end of every turn (sase agents that get intentionally
  terminated early--when using their /sase_plan or /sase_monitor skills, for
  example--are exempt).
  - The finalizer could then force a new turn if the agent doesn't use /sase_final for
    some reason (and then fail if the agent doesn't use /sase_final on that turn
    either).
  - This skill could instruct agents how to use a new `sase final` command to persist
    some JSON data somewhere that is associated with that agent and can be read,
    validated, and acted on (e.g. by creating commits, creating task beads, etc...) by
    the finalizer.
  - We should figure out a way for agents to specify the commits/stitches that should be
    created for each repo that contains files that that agent modified using the
    `sase final` command. We'll also need to be careful that we don't break sase's
    current merge conflict workflow (e.g. make sure merge conflicts are still always
    caught and handled by sase agents--when they can't be auto-resolved). Think hard
    about how to get this right.
    - One new requirement we should add: sase agents that do not commit to certain repos
      should be required to specify a refusal reason via the `sase final` command (so we
      have some more insight when the finalizer fails because an agent refused to commit
      detected file changes).
- Sase's commit finalizer is such a critical part of sase that I think this feature
  belongs behind a feature flag.

Can you do some research with the goal of helping me decide the best way to implement
this? We've already done some related research on this in the past so make sure you find
and review that before starting your own investigation. That research is old though so
don't rely on it as a source of truth. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the `sase_repo` skill to access the linked research repository correctly, plus `sase_memory_read` for the mandatory xprompt and feature-flag context. I’ll first locate and critically review the earlier research, then trace today’s finalizer/merge-conflict behavior in code and compare relevant extension designs before writing the recommendation.

The mandatory context confirms two key constraints: `%final` belongs with stripped launch directives, while `/sase_final` would be a generated skill whose source—not deployed copies—must define the contract. I’ve also confirmed the requested directory is the opened `sase--research` linked repo, so I’ll write only through that audited checkout.

The earlier July report is directly on point, but the current tree has diverged substantially: the commit path is still singular and now spans additional baseline, auto-commit, sibling-repo, publication, and no-progress modules. I’m treating that report as hypotheses only and revalidating every load-bearing claim against today’s `b6864fdb6` tree.

A major new fact is already clear: today’s commit workflow has a durable per-run, per-repository `commit_results.json` ledger and a resumable `commit_state.json` checkpoint. That means the safest design should extend these proven protocols; a new finalization manifest should describe intent/refusal, while `sase stitch create` remains the sole executor and conflict authority. I’m now validating the shared Rust boundary and CLI conventions before fixing the schema.

The current architecture also changes the plugin recommendation from the July report. SASE now has first-class, plugin-qualified provider templates (`use: distribution@id`) with required-plugin validation; that is a better fit than letting plugins inject enabled finalizers through `default_config.yml`. Installation can make a finalizer available, but only explicit config or `%final` should activate it.

I’ve finished the historical review and current-code audit. The key shift since the July research is that SASE now has durable per-repo commit attribution and conflict-resume machinery; the design should build on those rather than introduce a parallel commit executor. I’m checking the current flag/config conventions and then I’ll write the recommendation into the research repository.

The design decision is now clear: make finalization a host-owned, fail-closed reconciliation protocol, with `/sase_final` collecting typed intent—not a plugin hook that gets to implement Git itself. That preserves SASE’s current “dirty work cannot silently disappear” invariant and gives plugins extensibility without giving prompt text authority over executables or repository paths.

One gap surfaced in the draft review: plugin providers alone would not fully satisfy “plugins and/or configuration.” I’m adding a constrained built-in command provider so a user can define a local finalizer entirely in trusted config, while keeping the command out of `%final` and executing argv without a shell.

Research completed and written to [generalized_finalizers.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/generalized_finalizers.md).

The recommendation is a feature-flagged, host-owned reconciliation controller with:

- Plugin and configuration-defined finalizers.
- `%final` selection and a default `commit` instance.
- Turn-bound JSON declarations through `/sase_final`.
- Mandatory per-repository `commit` or reasoned `refuse` decisions.
- Existing `sase stitch create --resume` machinery retained for commits and conflicts.
- One recovery turn for missing finalization declarations, then fail closed.
- Mutate, seal, and verify stages with bounded fixed-point reconciliation.

The report reviews the July research, audits the current implementation, evaluates alternatives, provides schemas and CLI/config examples, and ends with the recommended solution. No runtime code was changed.

The research file is complete and was created in this session. The commit finalizer requires it to be committed now, so I’m using the `sase_git_commit` skill and will verify the research checkout is clean afterward.

The research commit succeeded. I’m doing the required final status check now, including whether the branch was pushed; the only warning was unrelated deferred prompt-archive publication because the shared agent-sync lock is busy.

Research committed and pushed as `fbd6dd5`:

[generalized_finalizers.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/generalized_finalizers.md)

The research repository is clean and synchronized with `origin/main`. Prompt-archive publication was separately deferred due to a busy shared sync lock.
