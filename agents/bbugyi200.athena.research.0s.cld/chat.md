# Chat History - ace-run (research.0s.cld)

- **TIMESTAMP:** 2026-08-20 09:49:51 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.0s.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260820_093205.md`

## Prompt

%id(cld, clan=research.0s) %wait(priority=20) %m:@research_b  #gh:gh_sase-org__sase Sase's commit finalizer is currently a hard-coded part of the
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

I'll start by loading the research, repo, memory, and artifact skills, then find the earlier finalizer work so this analysis builds on it instead of repeating it.

Next I’ll audit the relevant memory notes and glossary terms, then open the research sidecar so I can find the earlier finalizer work.

The glossary call used the wrong separators, so I’ll retry that and then hunt prior finalizer research in the sidecar.

The July research on pluggable finalizers is the prior work. I’ll read it next, then check how the current finalizer actually behaves so the new report isn’t based on stale assumptions.

I found the July pluggable-finalizers report. Next I’ll reread that plus the current finalizer, plugin, flag, and conflict-handling code so the recommendation reflects today’s system.

The July design still looks relevant, but I need to check what landed since then—especially vars-driven commits, flags, and the conflict path—before recommending a path.

I have enough to write the report: the July design still holds in outline, but several of its premises are stale, and the new `/sase_final` plus host-executed stitches need a conflict contract that the old write-up never specified.

I’m writing the report into the research sidecar now, citing the July work and the current tree so the recommendation is grounded rather than inherited.

The recommended design is: **a keyed `finalizers:` registry, an agent-facing `/sase_final` + `sase final` intent document, host-executed `sase stitch create`, additive `%final` over an implicit commit default, plugin opt-in, and a beta flag that keeps today’s path until the new one has soaked.**

The full analysis is at:

`sase/repos/research/202608/pluggable_finalizers/pluggable_finalizers.md`

Cite it as `@research:202608/pluggable_finalizers/pluggable_finalizers.md`.

### What I treated as prior work, not truth

The July 2026 report (`@research:202607/pluggable_finalizers_final_directive`) is still the right *engine shape*: config map, chop-like script, `%final` as selection, plugin opt-in. Three of its premises are now false:

- The `sase-be` “vars-driven commit finalizer” epic is **gone** from the plans tree; `commit --vars` never landed.
- **`sase var` is the wrong store** for stitch intent (it leaks into ACE/Telegram and has the wrong size/schema).
- Feature flags now exist, and this is exactly the kind of dual path they are for.

I re-verified the live finalizer at `b6864fdb6`. It is still one hard-coded function in `_invoke.py`, still a *turn* hook, still agent-executed via `/sase_git_commit`, and the conflict/`--resume` path from 2026-04 **did** land.

### Recommended contract

| Piece | Recommendation |
| --- | --- |
| Agent | Last action of a completing turn: `/sase_final` → `sase final status` / `commit` / `refuse` |
| Host | Validate the JSON, then run `sase stitch create` per repo |
| Conflicts | Exit 2 leaves `commit_state.json`; follow-up is resolve + `sase final resume`. Do not start repo B while repo A is paused |
| Refusal | Required for every remaining dirty repo the agent will not stitch; **still fails the run**, but with `reason: refused` plus the prose |
| `%final` | Omitted ≡ `%final:commit`. `%final:lint` **adds** lint; it must not drop commit. Use `%final:!commit` or `%final:none` to drop it |
| Plugins | Declare via `sase_config` `finalizers:` map, implement as a console script, **opt-in** (`pip install` must not activate post-run code) |
| Flag | `pluggable_finalizers`, **beta, default off**. Permanent knobs stay `finalizers.commit.enabled` and `%final` |
| Handoffs | `/sase_plan`, `/sase_monitor`, `/sase_pipe`, `/sase_questions` stay exempt because they `SIGTERM` inside `invoke()` — mechanical, not honor-system |

Happy path: the original turn declares intent, the host commits, **no extra LLM turn**. Missing `/sase_final` on a dirty completing turn: one forced follow-up, then fail.

The product bet is phase 2 in the report: if host-executed stitches plus `--resume` cannot preserve the discarded-work guard, bead publication check, and conflict recipe, stop and keep today’s agent-executed commits rather than generalizing a broken `commit` entry.

I'll commit the research sidecar file now, using the git-commit skill and then verifying the repo is clean.

I'll inspect the research sidecar's uncommitted files, then create the stitch with a docs-style commit message.

The first status was the sase workspace, not the sidecar. I'll inspect the research checkout next.

The sidecar only has the new report. I'll write the conventional commit message and create the stitch.

The stitch command is still running, so I'll wait on it in this turn until it finishes.

Committed the research report in the `research` sidecar.

- **Commit:** `1ce11b6` — `docs(research): recommend a pluggable finalizer and %final design`
- **File:** `202608/pluggable_finalizers/pluggable_finalizers.md`
- **Status:** `main` is clean and matches `origin/main`

Cite the report as `@research:202608/pluggable_finalizers/pluggable_finalizers.md`.

`sase stitch create` also warned that this project already has 41 quarantined agent-hood publication requests, so the stitch link written into the commit may stay unpublished until the outbox is cleared (`sase agent sync --retry-quarantined`). That does not affect the git commit itself.
