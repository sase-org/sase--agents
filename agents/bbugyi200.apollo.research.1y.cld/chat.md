# Chat History - ace-run (research.1y.cld)

- **TIMESTAMP:** 2026-10-17 15:28:46 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1y.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_150918.md`

## Prompt

%id(cld, clan=research.1y)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.1y.cdx`, `research.1y.grk`, `research.1y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

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
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Reading done. I've gone through the context report; next I'm checking GitHub's merge-queue docs and its answers to the pilot's open questions.

Confirmed on two public repos (Homebrew/brew, bevy) that `main` moves to the exact merge-group SHA that was tested. Now getting the ruleset parameter defaults and plan availability.

Pulling the merge-queue schema from GitHub's GraphQL API (two types per query to stay under its limit).

Writing the report next; first a quick look at sase's own workflow triggers so the SASE section is concrete.

Report written; registering it as a durable artifact now.

I've written the report and registered it as a snapshot.

- **Report:** `sase/repos/research/202610/github_native_merge_queue_how_it_works__cld.md`
- **Artifact:** `explicit:e7923b23e357f71fb82b51ad`, label `research:202610/github_native_merge_queue_how_it_works__cld.md`
- **Commit:** declared for the research repo; the host commits it after this turn ends.

**How it works:**
- **It's a line in front of `master`.** Clicking merge puts a PR in line. GitHub then builds a temporary commit: current `master`, plus every PR ahead of it, plus this PR. CI runs on that commit. If it passes, `master` moves to it; if it fails, the PR is removed and nothing lands.
- **`master` becomes the exact commit that was tested.** GitHub's docs never say this directly, so I checked live public data. On Homebrew/brew (which uses merge commits, like your plan) and bevy, 34 of 35 recent landings were a tested queue commit. The 35th most likely started testing just before my sample window.
- **Each PR gets its own build, stacked on the ones ahead of it.** When a build near the front fails, every build behind it restarts. The report walks through a real example from bevy. Batching settings only change how many passed PRs land at once; they never combine builds. This is why flaky tests cost so much under a queue.
- **CI has to run on a new event, `merge_group`.** Every required check has to pass on the queue commit as well as on the PR. A required check that never reports on the queue commit leaves the PR waiting until the timeout, and then it's ejected.
- **Real configurations:** GitHub's own docs repo runs almost exactly what your plan proposes: two builds at once and every queued PR must pass. Homebrew runs a much looser, flake-tolerant setup.

**Your pilot's open questions:**
- **Landed SHA equals tested commit:** answered yes, in practice.
- **Checks skipped by a job-level `if:`:** they count as passing. A workflow skipped by a path filter instead stays "pending" and blocks the merge.
- **PRs opened with your credentials:** they trigger workflows normally. The no-new-runs rule only applies to events caused by Actions' own `GITHUB_TOKEN`.
- **Direct pushes:** no GitHub page says the queue rule alone blocks them. The plan's required-PR rule blocks them anyway, but confirm it in the rehearsal.

**Two sase gotchas:**
- **`pr-title.yml`:** it only runs on PRs, so if it ever became a required check, every queued PR would time out.
- **The push-triggered Master Gate:** keeping it during the pilot just re-tests the same commit, about 43 extra builds a day.

Also still unverified: GitHub publishes no default values for the queue settings, so the report recommends setting every one explicitly.

I didn't create or change any GitHub repo, ruleset or workflow; everything I checked was read-only.
