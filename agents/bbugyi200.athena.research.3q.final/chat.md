# Chat History - ace-run (research.3q.final)

- **TIMESTAMP:** 2026-10-06 11:30:03 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3q.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_104840.md`

## Prompt

%clan(research.3q, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm looking for some recent (published within the last year) articles that will inspire
me to improve sase's memory files and agent instruction files. Can you do some research
with the goal of finding the articles that are most likely to do that? End your analysis
with a ranked list of articles that you think I should consider reading.]]) %id:research.3q.final %m:@xlarge
%wait:research.3q.cdx %wait:research.3q.cld %wait:research.3q.grk %wait:research.3q.mus %wait:research.3q.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm looking for some recent (published within the last year) articles that will inspire
me to improve sase's memory files and agent instruction files. Can you do some research
with the goal of finding the articles that are most likely to do that? End your analysis
with a ranked list of articles that you think I should consider reading.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3q.cdx`, `research.3q.cld`, `research.3q.grk`, `research.3q.mus`, `research.3q.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3q.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3q.linker`, can find it:

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

Reading the five researcher reports now (cdx and cld done); next grk, mus, gem, then my own gap research.

All five reports are read. Next I'm pulling SASE's own memory-read stats, then running parallel checks on the claims that only one researcher made or that look shaky.

I'm pulling dates from the memory-read audit log so the frequency numbers in the report have a time window.

The numbers hold: decisions index 885 words (35%), 543 words duplicated from `~/CLAUDE.md`. Now setting up the consolidated directory and moving the five reports into it.

Report written. Registering it as a durable artifact for the linker agent.

Registration succeeded. Submitting the final declaration.

I've written the consolidated report and registered it for the linker agent (`research:202610/memory_and_instruction_file_inspiration_reading_list/memory_and_instruction_file_inspiration_reading_list__final.md`). The five researcher reports now sit beside it under the same name, with their `__cdx`/`__cld`/`__grk`/`__mus`/`__gem` suffixes. The research-repo changes will be committed by the host when this turn ends.

**Main conclusion:** sase's memory design is already what the recent articles recommend. None of the strong ones argues for a vector store, automatic linking or a runtime instruction router. Their pressure is on three things:
- **Budget:** what earns a place in the always-loaded file.
- **Wording:** prohibitions work better than "do X" directives, and a reason works better than MUST.
- **Rationale and staleness:** recording why each rule exists, and noticing when it stops being true.

**What I checked or added:**
- **Fact-check:** about 40 cited sources checked against their original pages. Nothing was invented, but several numbers were misquoted; there's a corrections table in the report.
- **Dropped picks:** gem's list included A-MEM, Zep and ACON, which predate the one-year window. Its #2 (Franko) reports numbers from a benchmark that names no model. I demoted these, and replaced mus's second-hand blog sources with the first-party pages they summarize.
- **New finds:**
  - Nakayashiki, on agents acting on superseded constraints.
  - SkillSeam, on routing conflicts between skills.
  - EA-Graph, on memory tied to code locations.
  - Claude Code's new AGENTS.md loading rules and `/doctor prompt-audit`.
  - Codex Memories.
  - Google is moving most Gemini CLI users to Antigravity CLI, which matters for the `GEMINI.md` target.
- **Measured sase:**
  - The decisions index is 35% of the generated `AGENTS.md`.
  - `~/CLAUDE.md` repeats 543 words of the project file, so Claude agents under `$HOME` get those sections twice.
  - Over the last 30 days, 62% of agents that read any memory read `lint_and_test.md`. Reads of the 25 decision records' full text totaled just 96.
  - Notes reachable only through a link phrased as an instruction ("read [[sase_sizes.md]]") are read heavily, even though one paper found agents ignore links between docs.

**Ranked reading list (top 10; the report goes to 32, plus a "not recommended" list):**
1. Chakrabarti, *Why Does CLAUDE.md Keep Growing?* (2026-08-11)
2. Gloaguen et al., *Evaluating AGENTS.md* (2026-02-12; v3 2026-09-29)
3. Segner, *Steering Claude Code* (2026-06-18)
4. Zhang et al., *Guardrails Beat Guidance* (2026-04-13)
5. Davidson, *Coding Agents Love Decision Records* (2026-10-02)
6. Nakayashiki, *When Stale Constraints Go Unchecked* (2026-08-26)
7. Shihipar, *The new rules of context engineering for Claude 5 generation models* (2026-07-24)
8. Nakasuji, *Skill Blocks* (2026-08-14)
9. Vasilopoulos, *Codified Context* (2026-02-24)
10. Gazit, *Building an agentic memory system for GitHub Copilot* (2026-01-15)

The report also has a 10-item list of ideas these readings point to. The first is dropping superseded rows from the decisions index and adding a "stop and propose a superseding record" rule for when a task conflicts with a decision.
