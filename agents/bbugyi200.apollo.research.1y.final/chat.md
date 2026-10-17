# Chat History - ace-run (research.1y.final)

- **TIMESTAMP:** 2026-10-17 15:42:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1y.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_150918.md`

## Prompt

%clan(research.1y, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research with the goal of helping me understand how GitHub's native
merge queues work? See the merge_queue_fenced_master_and_exact_sha_releases.md file in
the research sidecar repo for context. Make sure your report is concise and easy to
understand.]]) %id:research.1y.final %m:@xlarge
%wait:research.1y.cdx %wait:research.1y.cld %wait:research.1y.grk %wait:research.1y.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research with the goal of helping me understand how GitHub's native
merge queues work? See the merge_queue_fenced_master_and_exact_sha_releases.md file in
the research sidecar repo for context. Make sure your report is concise and easy to
understand.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.1y.cdx`, `research.1y.cld`, `research.1y.grk`, `research.1y.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.1y.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1y.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

I've read all four reports. The big disagreement is whether `master` ends up on the exact commit CI tested. I'm checking that against live public repos now.

The live data settles it: on both Homebrew/brew and github/docs, `master` lands on exactly the commit the queue tested. Next I'll move the four reports into a new folder and write the merged report.

Folder created and reports moved. Now writing the consolidated report.

Registered. Now submitting the final declaration.

I merged the four reports and my own checks into one report and registered it for the linker. The registration succeeded (`file:explicit:bc9ddf631a7b2065858440a5`). The research repo changes are declared for commit, and the host commits them after this turn ends.

**Layout:** `202610/github_native_merge_queue_primer/` holds `__cdx`, `__cld`, `__grk`, `__gem` and `__final.md`. I moved the four reports unchanged, and I did not create the bare `github_native_merge_queue_primer.md`.

**How the merge queue works:**
- **It's a line in front of `master`.** Merging a PR only puts it in line. GitHub builds a temporary commit: current `master`, plus every PR ahead of it, plus this PR. CI runs on that commit, and the PR lands only if it passes. If it fails, the PR is removed and the PRs behind it are rebuilt without it.
- **Each PR gets its own CI build.** Builds can run in parallel, but batching settings only control how many already-passed PRs land at once. They never share a build.
- **CI must trigger on the `merge_group` event.** A required check that runs only on PRs never reports in the queue, so the PR times out and is ejected.
- **A CI check that skips itself can let untested code in.** A job skipped by `if:` counts as passed. A whole workflow skipped by a path filter stays Pending and blocks the queue.
- **`gh pr merge` returning 0 means "queued", not "merged".** Automation has to wait for the actual merge.
- **sase qualifies.** `sase-org/sase` is a public repo owned by an organization, which can use the queue on any plan. Zero required approvals works.

**Disagreements I settled:**
- **Does `master` end up on the exact commit CI tested?** One report (grk) said no. I checked the live history of Homebrew/brew (merge method) and github/docs (squash method): every queue landing I sampled was exactly a tested queue commit. cld found the same in 34 of 35 landings. GitHub's docs don't promise this, so the report recommends the landing watcher check it.
- **Does the April 2026 GitHub incident prove the opposite?** No. The status page says the incident came from a wrong merge-base calculation. It doesn't say whether CI tested the bad commits.
- **Does the merge-queue rule alone block direct pushes?** Still unconfirmed. The report recommends adding "require a pull request" with zero approvals and "restrict updates", keeping the bypass list empty, then testing with a probe push.

**sase-specific findings from today's workflows:**
- **Master Gate isn't wired yet.** It runs only on pushes to `master`, so it needs a `merge_group` trigger before it can be the required check.
- **`pr-title.yml` must stay optional.** It runs only on PRs, so making it required would time out every queued PR.
- **The push-triggered gate would duplicate work.** `master` lands on an already-tested commit, so it would re-test about 43 commits a day.

**Starting settings:** merge method, 2 builds in parallel, one PR landing at a time, every PR must pass, 60-minute timeout.

The moved cdx and cld reports link to the context report by a relative path. Since they now sit one folder deeper, those links are broken; I left the reports unedited rather than change other agents' files.
