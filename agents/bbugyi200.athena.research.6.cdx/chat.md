# Chat History - ace-run

- **TIMESTAMP:** 2026-07-09 16:15:29 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** research.6.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260709_160924.md`

## Prompt

%name:research.@.cdx %model:@research %g:research #gh:gh_sase-org__sase When preparing a workspace directory for a SASE agent, we currently always clone the sdd repo locally. I've been wondering if that is necessary and if we could instead have a single clone of the sdd repo live locally on each machine. Agents can just share that and sync it when they need to and push changes to it when they need to. Can you do some research to help me understand if this is a good idea and if we can solve the concurrent rights problem where multiple agents try to make changes to sdd files at the same time? When you have concluded your research, express your answer by setting some sase variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I’ll inspect the workspace-prep path and the current SDD handling first, then I’ll write the research note and set SASE variables with the conclusion. I’m using the `sase_var` skill because you asked for variables to be set at the end.

The initial search was too broad, so I’m narrowing to the storage and workspace-preparation modules plus SDD docs. The shape I’m looking for is: where the companion repo is materialized, how agents see it, and where SASE already serializes writes.

Current docs already say numbered workspaces get their own companion checkout or a fast-forwarded copy from the primary checkout. I’m checking the implementation now to see whether that is just documentation or an enforced invariant in launch paths.

Launch prep does enforce the per-workspace SDD clone after the code workspace is prepared, and tests lock that in. Next I’m reading the clone helper and commit/push path because that is where a shared-store design would need stronger concurrency rules.

The clone helper is best-effort and deliberately does not fail agent launch; commit logic commits locally first and treats push failures as warnings. That is good for per-agent clones, but it also means a single shared checkout would need explicit locking around every local mutation, not just around push.

Agent-facing `SASE_SDD_DIR` is resolved to the workspace-local path for `separate_repo`, so many callers can be unaware of the storage layout. A machine-global store would mostly be a resolver change, but the mutation model is the risky part.

There are a few SDD writers outside agent launch, including plan approvals, bead commands, and commit finalizers. That matters because a shared checkout lock would have to cover all of those code paths, not just the runner’s initial clone/sync step.

Bead state introduces an additional class of conflicts: SQLite is intentionally not committed, while JSONL is. Sharing one working tree would also share the transient SQLite database, so concurrent bead mutations would need a database/write lock and a rebuild/export policy, not only Git serialization.

The Python bead API delegates actual JSONL mutation to the Rust core, so I need to inspect that linked repo through the SASE workspace command rather than guessing about its locking behavior.

The Rust core uses `fs2` locks for some stores, but the first scan did not show the same lock pattern in bead mutation files. I’m reading the bead mutation implementation directly to confirm whether there is any hidden serialization.

At this point the evidence points to “possible, but not by just changing the path.” I’m taking a quick local measurement of SDD clone size and checking current workspaces so the recommendation can distinguish correctness risk from disk/performance payoff.

I have enough evidence now. I’m going to add a research note under the requested SDD research directory with the recommendation, failure modes, and two implementable designs.

I added the research note. I’m doing a quick sanity check on the file and then I’ll set the SASE variables with the conclusion.

Wrote the research note here: [shared_sdd_clone_research.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.sase/sdd/research/202607/shared_sdd_clone_research.md:1).

Conclusion: a single shared mutable SDD checkout is not a good default. The better design is a machine-local SDD cache or bare mirror plus per-agent isolated worktrees/reference clones. A single shared checkout can be made safe only if every SDD write is routed through an exclusive transaction lock/broker.

Set SASE variables on `research.6.cdx`:
`recommendation=shared_cache_per_agent_worktree`, `shared_mutable_checkout_safe=no`, `single_checkout_possible_with_lock=yes_but_not_recommended`, `research_path=...`, `concurrency_solution=...`, `confidence=high`, `status=complete`.

External references used in the note: Git worktree docs, Git push docs, SQLite isolation/WAL docs. No code checks run; this was only an SDD research markdown change.
