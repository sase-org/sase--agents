# Chat History - ace-run (research.1y.grk)

- **TIMESTAMP:** 2026-10-17 15:20:44 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.1y.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_150918.md`

## Prompt

%id(grk, clan=research.1y)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 4-researcher swarm.
The other researchers, `research.1y.cdx`, `research.1y.cld`, `research.1y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of helping me understand how GitHub's native
merge queues work? See the merge_queue_fenced_master_and_exact_sha_releases.md file in
the research sidecar repo for context. Make sure your report is concise and easy to
understand. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by reading the research, artifact, and repo skills, then pull the sidecar context file so the GitHub merge-queue report has the right background.

I'll record the skills in use, read artifact memory, and open the research sidecar so I can pull the merge-queue context file.

Research sidecar is open. Next I’ll locate the context file and read it through the audited artifact path.

The context file is in the research sidecar. I’ll read it as an audited artifact and pick a unique `__grk.md` stem so I don’t overwrite existing reports.

I have the design context. Next I’ll pull GitHub’s official merge-queue docs and related sources so the report can explain the mechanism clearly.

I’ll pull the official GitHub docs next so the mechanism, settings, and SHA behavior are accurate.

The SHA identity of the tested merge-group vs what lands on the branch is the key remaining question. I’ll pull the event payload, GraphQL API, and ruleset docs next.

The unique filename is free. I’ll write a concise report on how GitHub’s native merge queue works, then register it as a durable artifact.

The report is on disk. I’ll register it as a durable snapshot next, using the real absolute and repo-relative paths.

Artifact registration succeeded. I’ll pull the host finalizer context and submit the turn declaration.

GitHub's native merge queue is a server-side FIFO lane for pull requests. It tests each change on top of the current base **and** every PR already ahead of it, then lands only that combination.

The report is at `research:202610/github_native_merge_queues__grk.md` (artifact `file:explicit:80266daabca14cf8a205bfa7`).

**How it works.** Enqueueing a PR makes GitHub create a read-only branch named `gh-readonly-queue/{base}/pr-{n}-…`. CI must run on the `merge_group` event against that commit (`GITHUB_SHA` is the merge-group SHA, not the PR head). If required checks pass, GitHub merges that temporary branch into the base. If they fail, it ejects that PR and rebuilds everyone behind it.

**Three SHAs.** The PR head, the merge-group commit, and the SHA that actually lands on `master` are different objects. Native methods are merge, squash, and rebase — there is no fast-forward of the tested commit. Gate-green is a property of the merge-group tree; a release must pin the **landed** SHA (or prove tree equality). The 23 April 2026 squash-group bug is the existence proof: GitHub recomputes the land, and for a few hours those trees did not match.

**For the fenced-`master` plan.** `sase-org/sase` can use this today (public org repo). PRs are plumbing; required approvals of 1+ deadlock maintainer-authored PRs. Wire `merge_group` on Master Gate before enabling the queue. Close direct pushes with Restrict updates + Require a pull request (zero approvals) + empty bypass — the queue rule alone is not that fence. Start with merge commits, max group size 1, ALLGREEN, concurrency 2. Treat "agent finished" and "landed" as different states.
