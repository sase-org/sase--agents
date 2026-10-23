# Chat History - ace-run (13f)

- **TIMESTAMP:** 2026-10-23 14:31:00 EDT
- **MODEL:** claude/opus
- **AGENT:** 13f

## Prompt

#gh:gh_sase-org__sase I still don't understand how GitHub merge queues will work unless sase agents all
start creating PRs (they currently all commit to master). Would I need them to start
creating PRs to use the merge queue? See the github_native_merge_queue_primer.md file in
the research sidecar repo for context. Make sure your report is useful, concise, easy to
understand, and includes mermaid diagrams if appropriate. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge
%q(1.5x,w=0.25)

## Response

Reading the context reports now; next I'll check how sase's host finalizer actually lands commits on master today.

Tracing where the agent commit finalizer pushes to master, so the report points at the real code path.

Confirming sase-github already has PR create/merge plumbing; then I'll write the report.

Checking the research repo's conventions before writing the report.

I have what I need. Writing the report now.

Validating the three mermaid diagrams render.

All three diagrams render cleanly. Registering the report as an artifact.

Registered. Now submitting the final declaration.

Yes, every change to `master` would have to arrive as a PR. But the agents wouldn't create them, and nothing about the agents changes.

- **A PR is the only thing the queue accepts.** You can't put a push or a bare commit in line. Once `master` requires the queue, a direct `git push origin master` is refused for anyone not on the bypass list. That includes you.
- **The host creates the PR, not the agent.** The step that runs `git push` to `master` today (`vcs_create_commit` in `_git_commit_dispatch.py`) would instead:
  1. push the commit to a throwaway branch (`sase/land/<op>`);
  2. run `gh pr create`;
  3. arm auto-merge with `gh pr merge --auto`.

  Agents still just edit files and end with `/sase_final`.
- **The PR is just the envelope the queue requires.** It needs zero approvals, merges itself, and nobody reads it unless something gets stuck. Expect about 43 of these auto-merging PRs a day in the PR list.
- **The real change is timing.** Today a finished agent's commit is on `master` within seconds. With a queue, the turn ends once the PR is armed. The commit lands about 13–30 minutes later (the earlier report's simulation), or gets ejected. Most of the new work is handling that gap: a watcher that confirms the landing, dependents that wait for "landed" rather than "bead closed", and a policy for ejected PRs.
- **Skipping PRs means building your own queue.** You'd need a lander that pushes a candidate branch, waits for CI, then fast-forwards `master`, coordinated across athena and apollo. You also can't exempt just the agents, because they push as you.
- **Most of the PR plumbing already exists.** The `#pr` macro's PR method already creates a branch, pushes it and opens the PR. One thing to fix: sase-github's `_submit_via_pr_merge` treats a successful `gh pr merge` as "merged", but behind a queue it only means "queued".

The report also says the finalizer must reset the workspace to `origin/master` after pushing the PR branch. Otherwise the next agent in that workspace builds on a commit that might get ejected. That point is my own inference; the earlier reports don't mention it. I found no bead yet that covers this queue-landing work.

All three mermaid diagrams in the report render without errors. The report is registered as an artifact (`explicit:6229094fd1c6e95d7efc735b`, label `research:202610/merge_queue_do_agents_need_prs.md`), and the commit to the research repo happens when this turn ends.

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/merge_queue_do_agents_need_prs.md`
