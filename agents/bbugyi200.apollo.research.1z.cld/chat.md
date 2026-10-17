# Chat History - ace-run (research.1z.cld)

- **TIMESTAMP:** 2026-10-17 16:53:41 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1z.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_163112.md`

## Prompt

%id(cld, clan=research.1z)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.1z.cdx`, `research.1z.grk`, `research.1z.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking about the best way to handle merging for an agent software factory
like sase. See the merge_queue_fenced_master_and_exact_sha_releases.md file in the
research sidecar repo for context. Can you do some research with the goal of finding
some recent (<1 year old) articles/papers that will help inspire me / point me in the
right direction? End your analysis with a ranked list of articles/papers that you think
I should consider reading. 
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

I've read the context report on merge-queue-fenced `master` and exact-SHA releases. Next I'll check Bryan's reading library, then search for recent articles and papers.

I'm running four parallel research helpers now: academic CI and flaky-test papers, papers on agentic PRs and multi-agent coordination, primary industry posts, and release-engineering sources.

The helpers came back with a large verified set. Now I'll spot-check the items I plan to rank highest, and look into whether Uber really open-sourced SubmitQueue in 2026.

Now I'll register the artifact.

The artifact is registered. Now the final declaration.

I wrote the report and registered it as an artifact (`research:202610/merge_discipline_agent_factory_recent_reading_list__cld.md`, id `explicit:0f5224b8a6fcfeee9c21b1b0`). The research repo commit has been declared, and the host makes it after this turn.

**Report:** `sase/repos/research/202610/merge_discipline_agent_factory_recent_reading_list__cld.md`

**What I found:**
- **The plan's shape holds up.** Fencing `master` with a merge queue, making the gate trustworthy first, and publishing the exact tested SHA matches what agent-heavy teams chose this year:
  - Anthropic's Claude Code team kept a merge queue at about 30,000 landings a day.
  - Uber open-sourced SubmitQueue. Its post-land "Stovepipe" service moves a last-green ref forward.
- **The strongest pushback comes from far bigger operations.** At about 1,000 commits an hour, Cursor accepts a "small and constant" error rate on trunk and releases from a separate green branch. OpenAI argues for "minimal blocking merge gates". The takeaway for sase: keep "gate-green trunk" and a forward-only "release-green" ref separate from day one. A 10× jump in volume then means relaxing the queue, not rebuilding releases.
- **Flakiness is slightly worse than the plan's simulation assumes.**
  - Flaky failures cluster, so a rerun isn't an independent second chance.
  - Agent-written tests are flakier than human ones.
  - Rerunning just the failed job turns a red into a green far more often than rerunning the whole workflow (73.6% vs 33.9%).
  - This points to a few additions: rerun once in a fresh process, run new tests several times before they can land, and don't let agents add quarantine entries or edit the gate themselves.
- **Track what happens after landing.**
  - Merged agent PRs need follow-up fixes at 1.62× the odds of human PRs.
  - Parallel agent PRs conflict textually 20–42% of the time.
  - LLMs resolve fewer than 60% of merge conflicts correctly.
  - The fixes: per-agent revert and follow-up-fix metrics, and conflict repairs that go back through the queue.
- **Four platform changes in the past year matter here:**
  - GitHub stacked PRs went GA on 2026-10-06 and land through the queue as one group, which could fit epic waves.
  - GitHub immutable releases lock a tag to a commit and attest it.
  - GitHub Actions now caps workflow reruns at 50.
  - PyPI rejects new files on releases older than 14 days.

**Top 5 of the 25 ranked reads:**
1. Tian Pan, *The Merge Queue Is the New Bottleneck* (Jul 2026)
2. Cursor, *Towards self-driving codebases* (Feb 2026), with *Agent swarms and the new model economics* (Jul 2026)
3. Anthropic, *How the Claude Code team does code review* (Oct 15, 2026)
4. Uber SubmitQueue's design docs, especially Stovepipe's promotion ref
5. Huang & Lin, *On the Reruns of GitHub Actions Workflows* (ACM TOSEM, Feb 2026), with the SCOUT paper (arXiv 2603.23054)

**Confidence:**
- The primary pages behind the top picks were re-fetched, and ten arXiv abstracts were re-checked.
- Huang & Lin's numbers came from a helper reading the PDF; I could only confirm the venue and date through a citation.
- SubmitQueue's open-sourcing date is approximate.
- I found no peer-reviewed study of GitHub's merge queue under agent load.

Library check: 5 of 68 candidates already in your library (1 finished).
