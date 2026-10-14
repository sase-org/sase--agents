# Chat History - ace-run (research.1a.final)

- **TIMESTAMP:** 2026-10-14 10:00:13 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1a.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_091543.md`

## Prompt

%clan(research.1a, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm not sure about our recent migration from agent instruction files to instruction
bundles (see the sase-1ko epic bead for context).

- The thing I am worried about is that an agent's core instructions are no longer
  transparent.
- I used to be able to just read the AGENTS.md file to understand what initial /
  project-level instructions a sase agent was given, for example. But now new users
  and/or non-sase agents need to generate it using a `sase` command I'm assuming?
- Also, it is not clear to me what the benefits are of this new solution? Your report
  should iterate over all of the immediate and long-term benefits.

Can you do some research with the goal of helping me decide whether or not I should
proceed with this work or revert it?]]) %id:research.1a.final %m:@xlarge
%wait:research.1a.cdx %wait:research.1a.cld %wait:research.1a.grk %wait:research.1a.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm not sure about our recent migration from agent instruction files to instruction
bundles (see the sase-1ko epic bead for context).

- The thing I am worried about is that an agent's core instructions are no longer
  transparent.
- I used to be able to just read the AGENTS.md file to understand what initial /
  project-level instructions a sase agent was given, for example. But now new users
  and/or non-sase agents need to generate it using a `sase` command I'm assuming?
- Also, it is not clear to me what the benefits are of this new solution? Your report
  should iterate over all of the immediate and long-term benefits.

Can you do some research with the goal of helping me decide whether or not I should
proceed with this work or revert it?

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.1a.cdx`, `research.1a.cld`, `research.1a.grk`, `research.1a.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1a.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1a.linker`, can find it:

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

I've read all four reports. Next I'm checking their disagreements and claims against the code, the bead, and live commands.

I've confirmed the cdx report's Codex fallback bug in the code. Next I'm checking the export-mode leak, the live delivery scoreboard, and the E4 roadmap details.

Live data shows about 37 post-cutover runs with 1 miss, which is too small a sample to judge. Now I'm checking some of the gem report's stronger numeric claims against the earlier research.

I've verified the parity test that ties the committed `AGENTS.md` to the bundle. Next I'm checking whether the "stale docs" and TUI-row gaps the reports flagged still exist at HEAD.

I've confirmed CI regenerates the instruction files before tests run. Now I'm checking whether anything in CI actually fails when the committed file drifts.

I've finished verification; the Muse explicit runs show the bundle twice, which is new and worth flagging. Now moving the four reports into the consolidated directory and writing the final report.

The report is written and registered. Last step: submitting the commit declaration for the research repo.

**Don't revert. Keep the new delivery (E3), but change the next epic (E4) so the repo keeps a full, readable `AGENTS.md`.** Three of the four researchers reached this on their own (`grk` with conditions), and my own checks support it. Only `gem` argued for E4 as currently planned.

**Your two concerns:**
- **Transparency hasn't been lost yet.** All 20 instruction files are still committed and still regenerated. A test checks the committed `AGENTS.md` against what the bundle builder produces. I compared my own delivered bundle with `AGENTS.md`. The only differences:
  - the `Home:` line;
  - the `chezmoi` repo entry;
  - two home reference notes;
  - a Claude single-turn section;
  - heading numbers.

  Reading `AGENTS.md` still shows about 95% of what an agent gets. You also gain something new: `sase instructions show NAME` prints the exact bytes a past agent received.
- **Nobody needs a `sase` command today.** New users, GitHub readers and raw `claude`/`codex` sessions see what they saw before. That would only change if E4 ships as planned. E4 would shrink `AGENTS.md` to an 80-line stub and require `sase instructions sync` to get the full text. That command doesn't exist, and E4 has no plan or bead.

**Benefits:** the report lists 29, immediate and long-term. The main immediate ones:
- The SASE rules arrive once instead of twice for Claude and Codex.
- Every provider gets the same instructions; Grok and Muse now get your home layer.
- The provider-specific directives, which used to be hidden in Python code, are now visible.
- Claude helpers get their own instructions.
- Each run keeps a byte-exact record of what it was given.
- Each provider has its own off switch, plus an automatic fallback if building the bundle fails.

**Only one benefit needs `AGENTS.md` deleted:** less generated-file churn, which is the weakest:
- **Churn is small:** 89 of 3,699 commits in 60 days touched `AGENTS.md`, 8 in the last two weeks. Only one touched nothing but generated files.
- **No conflict harm found:** beads and commit messages record none.
- **The original technical reason is gone:** the plan assumed Codex couldn't ignore a committed `AGENTS.md`. It can.

**Things to fix before E3 closes (none is a reason to revert):**
- **Codex fallback drops the home layer.** If building the bundle fails, Codex gets neither the bundle nor your home file. `cdx` found this; I confirmed it in `_codex_home.py:128,152`.
- **The public ("export") version still leaks home metadata:** the `chezmoi` entry. Fix this before committing it anywhere public.
- **New: both recent Muse explicit runs received the bundle twice.** Either it breaks the "exactly once" guarantee or the counting is wrong.
- **Most Claude runs are still on the old path** because installed `sase` versions are behind; my own run used the new one.
- **CI regenerates `AGENTS.md` instead of checking it**, so a stale committed file isn't caught. Adding `sase init memory --check` to CI fixes that.

I also corrected several `gem` claims. The biggest: turning the flags off would not break Grok again, because E1's fix stays. It also wouldn't bring churn back, since E3 never changed churn.

**Next steps:**
1. Fix those defects and run each provider for 7 clean days.
2. Write a new decision record that keeps `AGENTS.md` as a readable, CI-checked copy. The accepted record currently assumes the files will be removed.
3. Re-scope E4:
   - delete the `GEMINI.md`, `QWEN.md` and `OPENCODE.md` copies;
   - add the CI check;
   - add a short header pointing to `sase instructions render`/`show`;
   - make the TUI's "AGENTS.md as launched" row open the bundle;
   - drop the stub and `sync`.

It all rests on about 22 runs from launch day, so the 7-day trial still decides whether E3 helps behavior.

The report is at `research:202610/instruction_bundles_vs_readable_agents_md/instruction_bundles_vs_readable_agents_md__final.md`, registered as `file:explicit:a0f355144ca7b6f7e8fd9cdb`. The four source reports moved into that directory with their suffixes kept, and the commit has been declared.

Sources:
- [OpenAI: Agentic AI Foundation](https://openai.com/index/agentic-ai-foundation/)
- [Technology Magazine: Linux Foundation launches AAIF](https://technologymagazine.com/news/one-rule-for-all-agents-linux-foundation-launches-aaif)
- [agents-md standard summary](https://agentic-ai.readthedocs.io/en/latest/Standards/agents-md/)
