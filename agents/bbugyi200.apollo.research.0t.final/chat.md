# Chat History - ace-run (research.0t.final)

- **TIMESTAMP:** 2026-10-10 17:12:21 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0t.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261010_163712.md`

## Prompt

%clan(research.0t, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research with the goal of finding the best, recent (<=1 year old)
articles related to agentic Software Engineering? Use your /bob_ref skill to make sure I
haven't already read any of the articles that you recommend. End your analysis with a
ranked list of articles that you think I should consider reading.]]) %id:research.0t.final %m:@xlarge
%wait:research.0t.cdx %wait:research.0t.cld %wait:research.0t.grk %wait:research.0t.mus %wait:research.0t.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research with the goal of finding the best, recent (<=1 year old)
articles related to agentic Software Engineering? Use your /bob_ref skill to make sure I
haven't already read any of the articles that you recommend. End your analysis with a
ranked list of articles that you think I should consider reading.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.0t.cdx`, `research.0t.cld`, `research.0t.grk`, `research.0t.mus`, `research.0t.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.0t.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0t.linker`, can find it:

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
└── <name>__final.md
```

## Response

Now reading each report through its canonical research reference.

I've read four of the five reports (cdx, cld, grk, mus). Next I'll read the gem report, then verify the disputed claims and check the library.

I've verified about 35 candidates, and several claims in the reports turned out wrong. I'm now checking one working paper, then the library.

I've run the library lookup over all ~100 merged candidates. Next I'll parse the results.

I've gathered all the evidence, so I'm moving the five reports into the new topic directory.

Now writing the consolidated report.

The report is in place. Registering it as a durable artifact:

Registration succeeded. Now the final declaration.

I merged the five reports into one ranked list of 26 articles from the past year, all checked against your library. I moved the five reports into `202610/agentic_software_engineering_reading_list/` and wrote the merged report to `agentic_software_engineering_reading_list__final.md`. It is registered for the linker as `research:202610/agentic_software_engineering_reading_list/agentic_software_engineering_reading_list__final.md`, and the commit is declared.

**Top picks (none are in your library):**
1. **Fan et al., "An Empirical Study of Harness Design for Coding Agents"** (2026-09-17). It tests which harness parts actually help, with controlled experiments. It's the natural follow-up to the eleven-system harness paper you finished today.
2. **Gloaguen et al., "Evaluating AGENTS.md"** (read v3, 2026-09-29). Instruction files don't generally improve task success and add over 20% cost, though agents do follow them. Three of the five researchers ranked it on their own, and it bears directly on SASE memory.
3. **Krentsel et al. (Berkeley), "Reality Is the Final Verifier"** (2026-09-10). It names the gaps no automated check can close, which is useful language for what receipts can prove.
4. **Ronacher, "The Coming Loop"** (2026-06-23). The best outside case for agents running inside an outer loop, and for where those loops break.
5. **Chen & Stratton, "Bottlenecks in Software Production"** (Harvard, 718 firms). After firms adopted agents, PR volume rose 23% but review time rose 49%, with no significant gain in delivered output.
6. **Böckeler, "Harness engineering for coding agent users"**, then **SlopCodeBench**, then **Stripe's "Minions" Parts 1 and 2**. None of the five researchers found Stripe's posts. Their deterministic-plus-agent "blueprints", isolated per-run machines and two-round CI cap are the closest industrial match to SASE.

Tiers 2–3 cover how practitioners build coding agents, how several agents coordinate, evaluation that looks past pass rates, plan-following, and a Purdue case study on turning each failure into a new control.

**Errors I corrected in the reports:**
- **AGENTS.md effect:** mus cited per-file-type figures from the paper's first version. The current version reports no general improvement for either generated or hand-written files.
- **Böckeler URL:** gem's link was wrong.
- **Meta-Harness:** mus said "+27 on SWE-bench." The paper has no SWE-bench result.
- **"At Equal Inference Cost":** it tests household and shopping tasks, not software engineering, and its date doesn't match its arXiv ID. I demoted it.
- **"Agentic Design Patterns":** it isn't about coding. I dropped it.
- **Otoum's IEEE Access review:** its DOI returns 404. I dropped it.
- **SWE-EVO:** the headline compares two different models.
- **Hassan et al.:** grk ranked it first, but it was first published outside the one-year window. It's in your queue, so it heads the "move up the queue" list instead.

The two TDD pieces genuinely disagree (Willison for test-first, Böckeler's small experiment against it), so I paired them rather than picking one.

Library check: 14 of 102 candidates already in your library (4 finished).

Sources:
- [Meta-Harness (arXiv 2603.28052)](https://arxiv.org/abs/2603.28052)
- [At Equal Inference Cost (arXiv 2609.04217)](https://arxiv.org/pdf/2609.04217)
- [Böckeler, Harness engineering](https://martinfowler.com/articles/harness-engineering.html)
- [Stripe Minions](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents) and [Part 2](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents-part-2)
- [Spotify Honk Part 1](https://engineering.atspotify.com/2025/11/spotifys-background-coding-agent-part-1)
- [Anthropic, How AI is transforming work at Anthropic](https://www.anthropic.com/research/how-ai-is-transforming-work-at-anthropic)
- [Anthropic, Measuring agent autonomy](https://www.anthropic.com/research/measuring-agent-autonomy)
- [Cheap Code, Costly Judgment (arXiv 2607.01087)](https://arxiv.org/pdf/2607.01087)
- [Bhati, Beyond Code Generation (arXiv 2609.04681)](https://arxiv.org/pdf/2609.04681)
- [DORA 2025 report](https://cloud.google.com/devops/state-of-devops)
