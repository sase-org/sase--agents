# Chat History - ace-run (research.w.image)

- **TIMESTAMP:** 2026-09-30 19:28:31 EDT
- **MODEL:** codex/gpt-6-sol
- **AGENT:** research.w.image
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_183649.md`

## Prompt

%id(image, clan=research.w) %m:gpt-6-sol
%wait:research.w.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:2882cbaf7fba6bd196e65c3753b03c30`

- **Node:** `agent-delta:20260930183655:f0df090a5b8772d7`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260930183655:f0df090a5b8772d7.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.w, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] One
of the best reads I've ever had related to sase was actually the SASE paper
(2509.06216). It has been a while since I've delved into relevant literature (e.g.
papers, articles) and I am curious as to what related progress has been made in the
industry over the last 6-12 monthes.

Can you do some research with the goal of recommending 10 high-value, recent papers
and/or articles on similar topics that I am likely to understand, appreciate, and learn
from? Prioritize quality over recency but do not recommend any papers or articles that
were published more than a year ago.]]) %id:research.w.final %m:@xlarge
%wait:research.w.cdx %wait:research.w.cld %wait:research.w.grk %wait:research.w.mus %wait:research.w.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

One
of the best reads I've ever had related to sase was actually the SASE paper
(2509.06216). It has been a while since I've delved into relevant literature (e.g.
papers, articles) and I am curious as to what related progress has been made in the
industry over the last 6-12 monthes.

Can you do some research with the goal of recommending 10 high-value, recent papers
and/or articles on similar topics that I am likely to understand, appreciate, and learn
from? Prioritize quality over recency but do not recommend any papers or articles that
were published more than a year ago.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.w.cdx`, `research.w.cld`, `research.w.grk`, `research.w.mus`, `research.w.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.w.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.w.linker`, can find it:

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

### Assistant

Now reading each report through its canonical research reference.

I've read all five reports and checked about 45 citations with parallel fact-checkers. Now I'm confirming the last few finalists myself before writing the consolidated report.

The final report is written. Next I'm registering it as an artifact, then checking the layout.

Registration succeeded. Now the final declaration.

I merged the five reports and my own checks into one reading list of ten items. Everything on it was first published between 2025‑09‑30 and 2026‑09‑30, and I checked each pick and its companion reads against the arXiv or publisher page.

**The ten:**
1. **OpenAI (Lopopolo), *Harness engineering*** (Feb 2026): three to seven engineers shipped about 1M lines with no hand-written code. Its "AGENTS.md is a map, not a manual" rule matches SASE's split between always-loaded and on-demand memory. Read this one if you only read one.
2. **Anthropic, *Effective harnesses for long-running agents* plus its sequel *Harness design for long-running application development*** (Nov 2025 and Mar 2026): progress files, feature lists that start out failing, and fresh context plus a handoff note beating compressed long sessions.
3. **Davis et al., *Model-Based Agentic SE (MAGE)*** (Aug 2026): the closest thing to the SASE paper in style, backed by a 20‑week, 540k-line multi-agent build. It doesn't cite SASE, so you'd have to map the vocabulary yourself.
4. **Gorinova et al., *Coding Benchmarks Are Misaligned with Agentic SE*** (KDD '26 workshop): it cites SASE, and shows the same model scoring 79.8% vs 58.0% depending on the harness. It's paired with the SASE authors' own *Don't Blame the LLM*.
5. **He et al. (CMU), *Speed at the Cost of Quality*** (MSR '26): a causal study where velocity gains fade but complexity (+42%) and warnings (+30%) stay.
6. **METR, *Many SWE-bench-passing PRs would not be merged*** (Mar 2026): maintainers approved about 24 points fewer PRs than the tests passed. It's paired with ImpossibleBench and Spotify's production "LLM judge" gate.
7. **Tang et al., *How Coding Agents Fail Their Users*** (20,574 real sessions): ignoring the developer's constraints and misreporting their own progress are the failure types growing as a share.
8. **Wang et al., *Humans are Missing from AI Coding Agent Research*** (the SWE-bench authors): it's paired with Anthropic's 400k-session study, where people made about 70% of planning decisions but only 20% of execution decisions.
9. **Edwards & Schuster, *Ask or Assume?*** (EMNLP '26): the SASE paper's "agent asks the human" idea, measured. A separate agent whose only job is deciding whether to ask closes almost the whole gap from an unclear task.
10. **Ye et al., *Coding with "Enemy"***: 94% of developers missed code an AI agent had been told to sabotage.

**What else the report covers:**
- A section on what the SASE paper's authors published next.
- A list of honorable mentions.
- The items I left out because your earlier sase research already covers them (*Codified Context*, *Evaluating AGENTS.md*, and the multi-agent scaling pieces).

**Mistakes found in the source reports:**
- **gem:** four citations had made-up group author names, and one Anthropic study title was invented. Its "SWE-bench Pro Verified" figures actually belong to the original benchmark (the real paper has 731 tasks, not 1,865). A "35% variance" claim is also not in the paper it cited.
- **Smaller fixes:** "747 lint rules" in MAGE is actually 747 lint files; Anthropic's session value rose 27%, not 25%; and the Google scaling study had 180 setups in its first version and 260 in its third.
- **The SASE paper's v3 (June 2026)** keeps the abstract word for word and the file differs by about 1 KB, so it isn't worth rereading.

The five reports now sit in `202609/sase_paper_followup_reading_list/`, renamed with their original suffixes. The consolidated report is `sase_paper_followup_reading_list__final.md` in that folder. It's registered as `research:202609/sase_paper_followup_reading_list/sase_paper_followup_reading_list__final.md` (`file:explicit:b2beed2412e30bb495804ef2`) for the linker agent. The research repo commit happens automatically after this turn.

Sources for the Symphony mention: [Help Net Security](https://www.helpnetsecurity.com/2026/04/28/openai-symphony-codex-orchestration-linear/), [InfoWorld](https://www.infoworld.com/article/4164173/openais-symphony-spec-pushes-coding-agents-from-prompts-to-orchestration.html), [Tessl](https://tessl.io/blog/openai-open-sources-symphony-a-spec-for-orchestrating-codex-agents).

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

I’ll read the consolidated report, turn its main findings into a legible infographic, and save it beside the Markdown file after checking that the output name is free. I’m using the imagegen skill for the graphic.

The report’s central thread is the whole agent system: model, harness, durable repository state, verifiers, and human authority. I’m shaping the infographic around its five findings and a few carefully labeled study results.

The graphic is ready, and the requested filename is free. I’ve checked the labels and study numbers against the report; I’m saving the PNG now.

Created the [infographic](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202609/sase_paper_followup_reading_list/sase_paper_followup_reading_list_infographic.png) beside the research report. It summarizes the five main findings and four study results.
