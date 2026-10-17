# Chat History - ace-run (research.1z.final)

- **TIMESTAMP:** 2026-10-17 17:46:18 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1z.final

## Prompt

%id(final, clan=research.1z)
%m:@xlarge
%wait:research.1z.cdx %wait:research.1z.cld %wait:research.1z.grk %wait:research.1z.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've been thinking about the best way to handle merging for an agent software factory
like sase. See the merge_queue_fenced_master_and_exact_sha_releases.md file in the
research sidecar repo for context. Can you do some research with the goal of finding
some recent (<1 year old) articles/papers that will help inspire me / point me in the
right direction? End your analysis with a ranked list of articles/papers that you think
I should consider reading.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.1z.cdx`, `research.1z.cld`, `research.1z.grk`, `research.1z.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1z.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1z.linker`, can find it:

   `sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"`

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

I've read the cdx, grk and gem reports; next I'm reading the cld report and the context doc in full, then checking the reports' disputed claims.

Writing the consolidated report now. First, setting up the report folder and moving the four input reports into it.

Registration succeeded. Now submitting the final declaration.

I've merged the four reports and my own checks into one consolidated report with a ranked reading list, and registered it for the linker (ref `file:explicit:b41a00988bc13593cd037152`). The host commits it after this turn; until then the research repo shows the changes as uncommitted.

**Bottom line**

- **Your plan holds up.** The last year's reading supports what you already have: protect `master` with the native merge queue, zero approvals, make the gate reliable before enforcing it, and publish exactly the SHA that was tested. At about 43 landings a day, sase is well inside the volume where a pre-merge queue is cheap.
- **The best new idea is to keep two kinds of green apart.** "The trunk passed the gate" and "this SHA is safe to release" should be two separate refs. Uber's open-sourced Stovepipe does this with a last-green pointer that only moves forward and a promotion ref (`verified-main`). I confirmed this in its design docs. Releasing from a `release-green` ref means you could relax the queue later without rebuilding the release path.
- **Anthropic shows where the queue stops paying.** Two reports read Anthropic in opposite directions because they were looking at different repos. The monorepo, at over 30,000 merges a day, dropped its merge queue. The separate Claude Code repos still run one. That is a scale boundary, not a contradiction.
- **The landing watcher is the real engineering, and the reassessment's switch to rebase raises the bar.** Rebase rewrites the agent's commit SHA, so "`master` contains the agent's SHA" no longer proves a merge. The watcher has to map each PR to its landed commit and check that commit's tree against what the queue tested.
- **Two finds none of the reports had:**
  - *Passes Alone, Fails Together* (arXiv 2609.25396): real agent PR pairs almost never break each other, while interface changes almost always do. A short note to the other agent about what changed fixed 82% of the broken runs. That suggests having the watcher send a summary of each landed interface to agents still running.
  - A public GitHub issue (a11ign#5125) where a release-pin test ejected every queued PR on every release. That is exactly the "base drift" failure the reassessment plans for.
- **Treat the gem report with care.** Several specific claims in it are not in the papers it cites, including a "review comment sign-flip", a ">3 files → 4× rejection" effect, and the wrong model list for Merge-Bench. It also misdates or misdescribes two older papers. The other three reports needed only smaller corrections. All of them are in the final report's corrections section.

**Top of the ranked list**

1. Anthropic's two October 2026 posts, read as a pair: *Redesigning source control at Anthropic* and *How the Claude Code team does code review*.
2. Uber's SubmitQueue and Stovepipe design docs.
3. Mergify's TLA+ verification write-up, with its *When GitHub Webhooks Lie* incident post.
4. *Passes Alone, Fails Together*.
5. Cursor's *Towards self-driving codebases* and *Agent swarms and the new model economics*.

The report ranks 15 in total, followed by a short "if a specific pain shows up" list.

**Unverified:** the "Super Merge" numbers one report used couldn't be checked; the X article was unreachable and I found no other copy.

Library check: 3 of 46 candidates already in your library (1 finished).

Files are in `202610/agent_factory_merge_discipline_reading_list/` in the research repo:
- agent_factory_merge_discipline_reading_list__final.md
- agent_factory_merge_discipline_reading_list__cdx.md
- agent_factory_merge_discipline_reading_list__cld.md
- agent_factory_merge_discipline_reading_list__grk.md
- agent_factory_merge_discipline_reading_list__gem.md
