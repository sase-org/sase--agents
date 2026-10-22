# Chat History - ace-run (research.3z.final)

- **TIMESTAMP:** 2026-10-07 13:22:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3z.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_122939.md`

## Prompt

%clan(research.3z, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some web research with the goal of finding some recent articles/papers that
are likely to inspire the current and future direction of this project? See the
sase_related_reading_history.md file in the research sidecar repo for an idea of some of
the things I've already read related to sase. End your analysis with a ranked list of
articles/papers that you think I should consider reading (make sure to clearly call out
why I should read each article/paper).]]) %id:research.3z.final %m:@xlarge
%wait:research.3z.cdx %wait:research.3z.cld %wait:research.3z.grk %wait:research.3z.mus %wait:research.3z.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some web research with the goal of finding some recent articles/papers that
are likely to inspire the current and future direction of this project? See the
sase_related_reading_history.md file in the research sidecar repo for an idea of some of
the things I've already read related to sase. End your analysis with a ranked list of
articles/papers that you think I should consider reading (make sure to clearly call out
why I should read each article/paper).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3z.cdx`, `research.3z.cld`, `research.3z.grk`, `research.3z.mus`, `research.3z.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3z.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3z.linker`, can find it:

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
├── <name>__mus.md
├── <name>__gem.md
├── <name>__final.md
└── <name>_narration.md
```

## Response

I've opened the research repo and read the cdx and cld reports. Next I'll read the remaining three, then do my own research and write the consolidated report.

All five reports are read. Now I'm checking the earlier reading lists for duplicates, then I'll verify the disputed and weakly sourced claims myself.

I'm searching the web now to check the weakly sourced picks (gem's Consort, ECT, MAGE, SWE-Router; mus's Cognition follow-up) and to look for anything the five reports missed.

Verification is done. Before ranking, I'm checking my new candidates against your Bob library so I don't recommend something you've already read.

Research is finished and the library check came back clean (only the Hassan paper is already queued). I'm checking one SASE detail, then writing the report.

Now I'll move the five reports into the new topic directory in my research checkout.

Reports are moved. Before writing, I'm confirming the bead IDs cld cited so the final report doesn't repeat a wrong one.

Bead IDs check out. Writing the consolidated report now.

Now registering the consolidated report as a durable artifact for the linker.

The report is registered (`file:explicit:ce10c4e2ed54c5bf8c6e0213`). Submitting the final declaration now.

I merged the five reports with my own research and verification into one ranked reading list. It's registered for the linker as `research:202610/sase_next_direction_reading_list/sase_next_direction_reading_list__final.md`, and the commit is declared.

**Top three:**
1. **Chronicle** (Microsoft, 2026-09-17): a small API for "re-run from step *k*, earlier steps served from the record." It is the most concrete answer to your two replay annotations, and no bead tracks this kind of replay today. Its evidence is thin: six incidents its authors built themselves.
2. **Ledger** (Hassan's group, 2026-08-01): the best-tested replay-related paper. Giving agents a view of what they've already read, changed and tried raised pass rates on 500 tasks and lowered cost.
3. **Loopjacking** (2026-09-17): shipping agent frameworks ran a different operation from the one the human approved. Its approval record (§6.1) and regression tests (§6.4) apply directly to the sudo, gate-handoff and plan-approval epics now in progress (`sase-110`, `sase-11t`, `sase-18i`).

**New from my research:** none of the five researchers covered agents that pass alone but break once merged. Four recent papers do (Claim Plane ×2, STALE, NP-Bench), and I ranked them #4. They bear on today's dispatch conflict-repair work:
- Declaring scope before writing and serializing overlap improved reliability, but mainly by running almost everything in sequence.
- The selective mode that tried to keep work parallel did slightly worse than no coordination.
- A short note to sibling agents saying "this interface changed" recovered 82% of broken merges.

I also added ParallelPilot, a controlled study of a dashboard for supervising parallel agents, which is relevant because ACE dominates recent commits.

**Corrections to the swarm reports (full table in the report):**
- gem credited the Evidence-Carrying Termination paper to "Hsu et al." Its sole author is Jason Liu (UCSD).
- gem described the 19.8% merge-conflict rate as "sequential PRs." Both rates are for PRs open at the same time. gem's claim that a merge queue would "eliminate" the 41.7% rate isn't supported.
- cld's "3.8× tokens" for Proof-or-Stop belongs to a different comparison. The headline 31→2 result was at matched compute.
- mus mixed SlopCodeBench v1 and v2 numbers, and presented as new a paper that's already in your started pile.

**Dropped as repeats:** six of the swarm's picks were already on your earlier memory or Goals reading lists, including cdx's #3, *Evaluating AGENTS.md*.

**Library check:** 2 of 49 candidates are already in your library, 0 finished. The Hassan SASE paper is still queued from 2025-11-28; it's rank 5, and its v3 Appendix A is the new part.

**Layout:** the five reports now sit in `202610/sase_next_direction_reading_list/` with the `__final.md`. I didn't create the bare `<name>.md` or `_narration.md`; going by the earlier reading list, the linker or a later step adds those.

Sources (main ones):
- [Chronicle](https://arxiv.org/abs/2609.20625)
- [Ledger](https://arxiv.org/abs/2608.00808)
- [Loopjacking](https://arxiv.org/abs/2609.21081)
- [Claim Plane confirmatory](https://arxiv.org/abs/2608.00947)
- [STALE](https://arxiv.org/abs/2609.25396)
- [NP-Bench](https://arxiv.org/abs/2610.07261)
- [Proof-or-Stop](https://arxiv.org/abs/2607.14890)
- [ECT](https://arxiv.org/pdf/2608.23623)
- [What Does a Harness Buy?](https://arxiv.org/abs/2610.04433)
- [Finding the Right Fit](https://arxiv.org/abs/2610.00917)
- [ParallelPilot](https://arxiv.org/abs/2609.33113)
- [Anthropic CI post](https://claude.com/blog/agentic-coding-is-straining-ci-heres-how-we-scaled-test-impact-analysis-at-anthropic)
- [Consort](https://databricks.com/blog/introducing-consort-test-driven-development-branching-database)
- [MAGE](https://arxiv.org/pdf/2608.25174)
- [SWE-Router](https://arxiv.org/abs/2607.00053)
