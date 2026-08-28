# Chat History - ace-run (research.1c.cld)

- **TIMESTAMP:** 2026-08-28 15:57:17 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1c.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260828_150907.md`

## Prompt

%id(cld, clan=research.1c) %m:@research_b  #gh:gh_sase-org__sase I'm thinking about migrating sase's memory files, which are
currently treated like configuration, into sase artifacts, which would require, for
example, adding a new "Memory" subtab to the "Artifacts" tab. Can you do some research
with the goal of critiquing this idea, helping me decide whether it is worth doing, and
(if so) how? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this properly before critiquing. Let me start by understanding both systems as they exist today.

I have a complete evidence base. Writing the report now.

Report written. Now finalizing the turn.

Report written to `sase/repos/research/202608/memory_as_artifacts.md` (529 lines), and linked as `derives-from` the glossary→memory-webs report.

## Verdict: don't migrate — unbundle it

The proposal is really four separable changes with very different economics:

| | Verdict |
|---|---|
| A `memory:` **artifact-reference kind** | **Do it** — highest value, lowest cost |
| **Read-log consolidation** | Do a narrow version (collapse the loaders, not the logs) |
| A **Memory sub-tab under Artifacts** | **Don't** |
| Memory files **into the artifact store** | Never |

## What the evidence showed

**The demand is real, but it's for citation, not browsing.** 392 of 4,051 plans (9.7%) and 97 of 450 research reports (21.6%) cite `sase/memory/<note>.md` as a hand-typed path string — 210 of 679 plans *this month*, up from 12% to 31% in two months. Those citations are untyped, don't follow renames, and are invisible to a link graph that holds 14,209 rows and exactly zero memory rows. Samples are overwhelmingly pointers ("Read `sase/memory/tui_perf.md` before starting") — a hand-rolled `@memory:` ref.

**Three hazards that a UI framing hides:**
- The cheap path doesn't exist. Document ref kinds are keyed strictly to `repos.sidecar` roles; memory is in the primary repo, so this needs a `sase-core` kind variant, not a config edit.
- Managed `Links`/`Referenced By` tables are written *into* the Markdown file. Memory bodies are inlined into `AGENTS.md` and four provider shims — a naive migration ships a link table to every agent on every turn against a ~5,098-token core budget.
- Memory's 8,772 reads dedup to 7,137 distinct (agent, note) pairs — a 50% increase in graph size and 56× the entire existing `read` relation, for rows that say "some agent read `sase_beads.md`".

**Cost, from your own precedents:** `sase-tj` took 9 phases plus a follow-on child epic to add *one* Artifacts pane for a class that already had a ref kind, a store, and a query profile. A Memory pane starts behind that and has a working 5,741-LOC pane to reconcile.

**Two cautionary datapoints:** `#memory/<stem>` already exists as prompt expansion and is used in 6 of 4,853 archived prompts — because it inlines the whole body instead of pointing. And `sase memory write`/`review` is 2,362 LOC with **zero proposals ever written across all 31 projects**.

## Recommended solution

Add a `memory:` ref kind in `sase-core` with a Python resolver reusing the existing memory selector, **pointer expansion**, and publication suppressed from day one (≈4 medium phases). Then collapse the three near-clone read loaders (845 → ~350 LOC). Keep the Memory pane in Config, where tiering, priority, and `sase memory init` legitimately live; let memory show up in the Bead/Plan/Agent relations rails and route back to the Config pane.

§8 has a pre-committed falsification test for my own recommendation, and §9 leaves four vocabulary decisions to you (scope semantics, strand addressing, the proposal subsystem's fate, and `#memory/` deprecation).

Both sides of the conflict are complete, independently-written research reports on the same question. Let me set up the repo's documented multi-report layout.

Conflict resolved and staged. Now the verification gate:

Gates all green (615 scoped tests passed, every lint gate ✓, no fixes to fold in). Continuing the paused rebase:

Rebase completed successfully. Now resuming the stitch:

The stitch resumed and pushed. Let me check the other repos I touched and look into the warning:

Found a concrete defect while resuming. Let me file it properly:

All repos clean. Finishing the turn:

`submission_required: false` — no obligations remain, since the resumed stitch already committed and pushed the research work and every other repo is clean.

## Conflict repaired and resumed

**The conflict.** The paused rebase was replaying `862e0ea docs(research): assess migrating sase memory into artifacts` onto upstream `50167df docs(research): assess memory as artifacts`. Both commits added `202608/memory_as_artifacts.md` — two complete, independently-written 500-line research reports on the same question, written 4 minutes apart. This was exactly the semantic hazard you flagged: the markers were trivially removable, but any single-file resolution either destroyed one agent's report or concatenated two frontmatter blocks and two titles into one broken document.

**The resolution** follows the layout `research/README.md` documents for multiple reports on one topic (`<YYYYMM>/<topic>/` with `__a`/`__b` drafts plus a consolidated report), matching three existing examples including `202608/glossary_to_memory_webs/`:

- `202608/memory_as_artifacts/memory_as_artifacts__a.md` — upstream report, verbatim
- `202608/memory_as_artifacts/memory_as_artifacts__b.md` — replayed report, verbatim
- `202608/memory_as_artifacts/memory_as_artifacts.md` — consolidated report (new)

The two reports agree on three of four sub-proposals (add a `memory:` ref identity; never move memory bytes into the artifact store; never let managed link tables reach a memory note) and genuinely disagree on the fourth — whether to build an Artifacts Memory sub-tab. §3.1 resolves that for report B on its measured cost evidence rather than splitting the difference, while carrying forward report A's scope-identity invariants and its ACE startup constraint, which report B never identified.

I also moved `links/202608/memory_as_artifacts.md.json` into the topic directory and repointed both link indexes (its own and the glossary one) at `research:202608/memory_as_artifacts/memory_as_artifacts.md` — otherwise the replayed commit's own link rows would have dangled. Nothing outside the research repo referenced the old path; I checked the sase workspace and the plans, beads, and agents sidecars.

**Verification.** `just check` — every lint gate green, 615 scoped tests passed. No fixes to fold in. The first run needed a cold sase-core rebuild and outran the window; the second completed the gates and I ran the scoped lane separately.

**Resume.** `git rebase --continue` landed `a82e179`, and `sase stitch create --resume` committed and pushed; `research` is clean at `main == origin/main`.

Two things worth your attention:

1. The stitch warned `referenced-by write-back failed: sequence item 0: expected str instance, bytes found`. I traced it: `_pull_rebase_if_remote` calls `run_sdd_git` without `text=True` (which defaults to `False` at `src/sase/sdd/_git.py:40`), so a failed `git pull --rebase` yields a bytes `issue.message`, which then crashes the join at `referenced_by_publication.py:64`. Beyond hiding the real git error, the `TypeError` escapes *before* `update_referenced_by_requests`, so those outbox rows never increment attempts and never quarantine. Filed as **`sase-va`** (bug, small — root cause is precise), linked `related` to `sase-u9`, which shares the same `run_sdd_git` helper.
2. The stitch also reported 239 quarantined agent-hood publication requests with a 120s timeout; it suggests `sase agent sync --retry-quarantined`. I left that alone — it's a standing environment condition, not something this turn's scope covers.
