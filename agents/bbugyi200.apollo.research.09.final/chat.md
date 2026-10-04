# Chat History - ace-run (research.09.final)

- **TIMESTAMP:** 2026-10-04 10:43:55 EDT
- **MODEL:** claude/opus
- **AGENT:** research.09.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_095726.md`

## Prompt

%clan(research.09, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I need to think of a new name for sase (which conflicts with the Secure Access Service
Edge project). I doubt that I will go with a name that is longer than 8 characters.
Bonus points for any names shorter than 8 characters, but how well the name matches with
what sase is/does as a product is more important than name length (up to around 8
characters, that is).

Can you do some research with the goal of helping me pick the best possible new name for
sase? Also, critique this plan in general. Is this a good idea? End your analysis with a
ranked list of the 10 best names that you think that I should consider (and a
recommendation on whether I should move forward with this rename or not).]]) %id:research.09.final %m:@xlarge
%wait:research.09.cdx %wait:research.09.cld %wait:research.09.grk %wait:research.09.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I need to think of a new name for sase (which conflicts with the Secure Access Service
Edge project). I doubt that I will go with a name that is longer than 8 characters.
Bonus points for any names shorter than 8 characters, but how well the name matches with
what sase is/does as a product is more important than name length (up to around 8
characters, that is).

Can you do some research with the goal of helping me pick the best possible new name for
sase? Also, critique this plan in general. Is this a good idea? End your analysis with a
ranked list of the 10 best names that you think that I should consider (and a
recommendation on whether I should move forward with this rename or not).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.09.cdx`, `research.09.cld`, `research.09.grk`, `research.09.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.09.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.09.linker`, can find it:

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
├── <name>__final.md
└── <name>_narration.md
```

## Response

Registration succeeded. Now the final declaration.

Yes, I'd go ahead with the rename, but give yourself two weeks to decide. If none of the three finalists holds up in that time, keep `sase` and write down that the question is closed. My top pick is `handful`.

**Why rename.** All four researchers agree on this, and my checks back them up. Secure Access Service Edge is a major industry category, spelled the same and also pronounced "sassy". It is also moving onto your vocabulary: "SASE agent" already means a networking endpoint client, and in 2026 the vendors started selling "agentic SASE" with MCP visibility.

**Critique of the plan:**
- **It has no stopping rule.** This is the fourth naming round in eight months: gai→sase in February, the Specyard shortlist in June, `sawi` rejected in July, and now this one. Each round got the diagnosis right and none of them closed.
- **The cost is growing fast.** `sase` now appears 141,784 times in 10,762 files, about 2.4× what it was at the July `sawi` decision.
- **The real risk is the replacement.** Almost every obvious metaphor is already a coding-agent tool: bosun, jig, reins, yoke, braid, keel, weft, cadre and dozens more. New agent packages were still landing on PyPI this week, so reserve names the day you choose.
- **The audience question hasn't been asked.** The only payoff is people who don't know sase yet finding it. If adoption isn't the goal, an epic touching 140k references is hard to justify.
- **Drop the acronym, keep the lineage.** Keep "structured agentic software engineering" as a lowercase tagline, but not the letters SASE.

**Where the researchers went wrong.** Their four top-10 lists had no names in common, and my checks knocked out several leading picks:
- **`sennit`** (grk's #2) is already a terminal multi-agent coding tool.
- **`canton`** (gem's #2) is dominated by Canton Network, a blockchain with its own AI-agent ecosystem. That's the SASE problem over again.
- **gem's "completely clean" claims** (`baste`, `coterie`, `mortar`, and others) were not registry-checked, and most are already taken on PyPI and/or npm.

**Ranked top 10:**

| # | Name | Len | Why | Main risk |
|-:|---|-:|---|---|
| 1 | `handful` | 7 | "A handful of agents": as many as one person can supervise, and it keeps the "sassy" wit. Free on PyPI and crates; `.sh` and `.dev` look unregistered. | Generic word for search; may undersell scale |
| 2 | `baste` | 5 | Basting is temporary stitching before the final seam, like agent drafts before the host's commit. Fits Patch/stitch/bead. | PyPI and npm taken by old one-release packages; "baste a turkey" |
| 3 | `crewrail` | 8 | Team plus rails is the most literal fit; all registries free | Reads as a CrewAI add-on; `.com` is parked |
| 4 | `stichos` | 7 | Greek for a line of verse; reads as "stitch OS"; cleanest handles | Spelling and sound don't match, the same flaw `sase` has |
| 5 | `senju` | 5 | "Thousand hands, one mind" | Religious name; Naruto; a Japanese IT-ops suite |
| 6 | `runclasp` | 8 | Every handle free, including `.com` | Said aloud it leads to Google's `clasp run` |
| 7 | `oarlock` | 7 | The pivot that lets one person row; clean | Clunky; it's about leverage, not a team |
| 8 | `specyard` | 8 | The June pick, still clean | Only names the specs part; a `specyard` GitHub org already exists |
| 9 | `simul` | 5 | A chess simul (one master, many boards) is the best metaphor on the list | PyPI and every other registry taken; heard as "simulation" |
| 10 | `crewrill` | 8 | Every handle free, including `.com` | "Rill" is obscure; same CrewAI shadow as #3 |

`sase` itself would rank between #3 and #4. Only `handful`, `baste` and `crewrail` clearly beat it.

**Next two weeks:**
1. Register the GitHub orgs and `.sh`/`.dev` domains for the top three.
2. Live with each name for a week (`alias handful=sase`), and say each once to a few developers to see if they can spell it back.
3. Ask a couple of AI models what each name means, and run a quick trademark search.
4. Decide on day 14.

If you rename, switch everything people see (command, package, GitHub org, domain, docs) in one release. Move the internals (`SASE_*` variables, `~/.sase`) later, with the old names still accepted.

None of this includes a trademark search, domain pricing or real user testing. A domain with no DNS record is probably unregistered, not guaranteed available.

The four reports are now in `202610/sase_rename_new_name_shortlist/`, alongside the consolidated report `sase_rename_new_name_shortlist__final.md`. That report is registered as `file:explicit:8016b499ade42346ceed12d1`, and the commit is declared for the host to make.

Sources:
- [rave-soft/sennit](https://github.com/rave-soft/sennit)
- [steven3002/sennit](https://github.com/steven3002/sennit)
- [Canton Network ecosystem](https://www.cantonecosystem.com/)
- [Cantor8: AI agent payment on Canton](https://www.cantor8.io/official-blog/worlds-first-private-ai-agent-payment-settles-on-canton-network)
- [agenticrail (CrewRailGuard)](https://pypi.org/project/agenticrail/0.3.2/)
- [google/clasp](https://github.com/google/CLASP)
- [ropewalk.ai](https://ropewalk.ai/)
- [threadle](https://github.com/threadle-sh/threadle)
- [Stichos GitHub account](https://github.com/stichos)
- [oarlock repos (aurahooe)](https://github.com/aurahooe/oarlock), [oarlock repos (szTheory)](https://github.com/szTheory/oarlock)
- [awesome-agent-orchestrators](https://github.com/andyrewlee/awesome-agent-orchestrators)
- [OpenAlternative: AI coding agent orchestrators](https://openalternative.co/blog/best-ai-coding-agent-orchestrators)
