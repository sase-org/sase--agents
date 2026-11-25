# Chat History - ace-run (1g5--plan)

- **TIMESTAMP:** 2026-11-25 14:46:28 EST
- **MODEL:** claude/opus
- **AGENT:** 1g5--plan

**Plan:** /home/bryan/.sase/plans/202611/research_hood_publication_scaling.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/research_hood_publication_scaling.md`

> # Plan: Stop large-hood publication cost from outgrowing the 120s drain alarm
> ## Problem
> Apollo's error digests keep reporting `agent_publication` drain timeouts for
> `gh_bobs-org__bob-cli`. On 2026-11-25 alone there were three: 07:22
> (`inventory_build did not complete within 30s`), 12:47 (the same), and 14:16
> (`agent-hood publication did not complete within 120s`). Each one opens a standing alert
> at `attempt1`. The next pass then publishes successfully, so the alert closes and opens
> again later. Nothing was lost, but the noise will keep coming, because the cause grows
> every day.
> Evidence, from apollo's `~/.sase/logs/agent_publication_drains.jsonl` (Nov 18–25):

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261125_142557_85297432.txt file for context.
%m:@xlarge

## Response

The digest file isn't on disk at that path, so I'm looking in the notification inbox and the axe logs for what it contained.

The digest isn't on athena and no athena notification references it, so it was probably written on another tailnet machine. I'll read the tailnet note to see how to reach them.

Found it — the digest lives on **apollo**, not athena. Now I'll check the surrounding digests and the run log there to see whether this keeps recurring.

Recurring on apollo: `gh_bobs-org__bob-cli` publication drain has timed out three times today (07:22, 12:47, 14:16). I'll pull the full run log to see where the time goes.

Next, the code: the agent_publication job, its 120s hood-publication budget, and how standing alerts open and close.

Apollo records per-drain stage timings in `agent_publication_drains.jsonl`. I'll pull the bob-cli records to see which stage is slow.

Publish cost tracks `runs_scanned`. Typical drains scan about 117 runs and take about 40s, but every timeout scanned 1,350–1,500 runs. I'll break this down per hood.

I'll check existing beads and recent history for prior work on large-hood publication cost.

Several earlier beads cover this exact path: `sase-1qh.3` (re-scan fix for the research hood), plus `sase-1nf.10` and `sase-1nf.10.1.9.1`, which are still in progress. I'll read them.

An earlier agent (`1bb`, 2026-11-11) already checked whether open epics cover "apollo bob-cli research hood drain timeouts". I'll look at what it concluded and at the open `sase-1nf.10` work.

The older epics are stalled waiting on acceptance decisions and don't own the research-hood cost growth. Next I'll see what agent `1bb` concluded on Nov 11.

On Nov 11 the research hood had 937 runs. It now has about 1,500, and 1bb's fix (caching the protection-ledger lookup) only shaved a constant factor. Here's whether that fix landed.

The research hood only exists at this scale on apollo; athena's largest hood is about 230 runs. Next I'll measure how fast it's growing.

An earlier plan used a read-only profiler (`tools/agents_publication_profile`). I'll check it exists and whether apollo can run it.

Apollo's checkout matches our HEAD (`df9ce4ef55`). I'll run the read-only profiler there under cProfile for the research hood, to see where the per-run cost sits today.

Self-time is spread thin across thousands of calls. The checkout venv has pyinstrument, which gives a reliable call tree, so I'll take one more read-only sample.

An open task, `sase-11n`, says "Agents-sidecar hoods have no retention … index-render cost grow without bound", which is directly relevant. I'll read it.

I'll stop on the link-drain side; the log's line-wrapping makes it noisy and it isn't what the digest reported. I have enough to plan, so I'm loading the planning skill.

I'll check where the existing agents-sync caches live (the inventory history cache and the refresh-verdict memo), so the plan can reuse the same pattern.

Before writing the plan, I need to confirm each publication tick runs in a fresh process. That decides whether an in-memory cache would be enough or the summary cache has to persist on disk.

Each tick is a fresh `sase_job_agent_publication` subprocess, so the summary cache must persist on disk, following the same `~/.sase/cache/agent-publication-history` pattern. Writing the plan now.

The plan validates. Before proposing, I'll spot-check two claims it makes: that the ledger module re-raises `PublicationDrainTimedOut`, and that full-mode rendering calls `render_machine_page`.

Both claims check out. Proposing the plan.

Yes, it's worth fixing, and I've proposed a plan; it's waiting for your approval. Nothing was lost: the next pass published every request each time. But the same error will keep reaching your digest more often, because its cause grows every day. The digest was on **apollo**, not athena, so I read it there over SSH.

**What happened.** This is the third bob-cli timeout on apollo today (07:22, 12:47, 14:16). Each one opens a standing alert, the next pass succeeds and closes it, and the next timeout reports it again as new.

**Why it keeps happening.** Every bob-cli research agent lands in one `research` group on apollo. That group has grown from 937 runs on Nov 11 to about 1,500 now, roughly 40 a day. Publishing even one research agent rebuilds the whole group. That takes about 47s typically and 74s at the slow end, against a cutoff of about 105s. The three earlier speed-ups (including the one from Nov 11) each cut a fixed amount, and growth has since used up that headroom.

**Where the time goes.** I profiled one research-group publish on apollo, read-only. It took 43s, and three spots account for about 26s of it:
- **13s re-reading every group.** Each publish fully loads all ~1,230 of bob-cli's group snapshot files, even though the index page only needs their counts and states. This is also why even tiny groups take about 10s.
- **6.5s on related-agent lists.** Building each page's neighbors list takes time that grows with the square of the group size, so it gets worse fastest.
- **6s on page links.** Every one of about 100,000 relative links calls a slow standard-library path function.

**The plan** (one coding agent, medium size):
1. Build the related-agent lists in time proportional to the group size.
2. Compute page links with plain string arithmetic, falling back to the old call for unusual paths.
3. For groups not being published, cache their counts in a small local file keyed by each snapshot's content hash. Every file is still checked against its hash on every publish, and any new content is fully validated once.
4. Add a cold-cache option and cache hit/miss counts to the publication profiling tool.

Published pages must come out byte-for-byte identical, enforced by tests that compare against the current output. The coding agent will measure before and after on athena. It won't touch apollo; it will give you a profile command to run there after you deploy. I expect warm publish time for the research group to drop to well under half.

**Not in scope:**
- Deleting old groups from the published store, which is already the open task `sase-11n`.
- Whether a timeout that will be retried should appear in the digest. You chose to keep reporting them on Nov 11.
- The 120s limit, and the separate slow artifact-link step that ran on the same tick.

If the research group keeps growing after this lands, the next step is to skip re-reading and re-checking runs that haven't changed.
