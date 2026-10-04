# Chat History - ace-run (research.y.cld)

- **TIMESTAMP:** 2026-10-01 01:11:46 EDT
- **MODEL:** claude/opus
- **AGENT:** research.y.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_005336.md`

## Prompt

%id(cld, clan=research.y)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.y.cdx`, `research.y.grk`, `research.y.mus`, `research.y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to explore the idea of integrating Jev (the new decision/judgement AI model)
into sase.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? End your analysis with a
recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Researching Jev's API and limits online; next I'll map sase's provider/decision points to find integration seams.

Mapping sase's judgment-shaped decision points; now measuring how many such decisions sase actually makes per day.

Checking task-bead history as a possible labeled corpus for evaluating Jev offline.

Tallying ToolRun failure triage classes (to see how much is stuck as UNKNOWN), then I'll write the report.

Writing the report now, after a quick check of the provider interface claims I plan to cite.

Now registering the report as an artifact.

I don't think Jev should go into sase core now. The one place it might help is ranking the backlog of task beads waiting for you to triage, and that can be tested offline for under $0.10 of Jev usage before building anything. The report is written and registered as an artifact (`file:explicit:327c52785e68e68d3545a933`, labeled `research:202610/jev_decision_model_integration__cld.md`); the host will commit it to the research repo after this turn.

**What Jev is.** TypeSafe AI released it on 2026-09-15 as a waitlisted early-access API. You send text plus typed questions, and each answer is one of three shapes: a pick from a list you supply, a score on a 2–10 level scale, or a yes/no probability. It never generates text. It is fast (70–500 ms) and cheap ($0.042 per million input tokens). Independent testing is less flattering than the marketing:
- Asked one broad question, it scored 62.6% against Haiku's 81.3%.
- It only matched or beat Haiku when the task was split into narrow questions and the answers were weighted using about 1,000 of your own labeled examples.
- Its "calibrated" probabilities needed per-question tuning before they could be trusted.
- Text inside the input can shift its answers, so it is open to prompt injection.

**Why it's mostly a poor fit for sase:**
- **It can't be a provider.** Every LLM call in sase is a full agent turn that ends with a `/sase_final` declaration. Jev can't produce one, so it can't be a `sase_llm` provider. It also wouldn't replace anything: sase has no cheap classification calls today.
- **Its cost and speed advantages don't apply.** Apart from agent tool calls, sase makes at most a few hundred judgment calls a day. At that volume even Haiku costs pennies.
- **The one high-volume stream is the worst fit.** That's agent tool calls, about 8,100 a day across four harnesses (Muse, Claude, Grok, Codex). Checking each call before it runs would:
  - be open to prompt injection;
  - send tool inputs and outputs (including vault and Gmail content) to a third party with no fixed data-retention limit on standard accounts;
  - need a separate hook for each harness.
- **sase's own decision records rule out most uses:**
  - Triage KNOWN verdicts require an independent witness, and a model guess isn't one. UNKNOWN is only about 4% of failed runs anyway.
  - "No mechanism before its corpus" argues against building a general decision subsystem up front.
  - Gate kinds whose auto-resolution is marked `forbidden` are off-limits by design.
- **Vendor risk is high.** The product is 16 days old, served from one region, with rate limits that change without notice and no SLA. There's also no TypeSafe credential in this environment yet, so you'd need to get access first.

**Where it could help.** You're the bottleneck on task triage:
- 189 triage gates are pending.
- 313 sase task beads are ready, with a median age of 9 days.
- None of the 884 triage gates from the last 30 days was answered through the gate itself.

There's also a ready-made test set: 672 closed task beads already labeled done (389), canceled (235) or superseded (45).

**Recommended path:**
1. **Offline test, outside sase.** On the closed beads, compare Jev against a model that always predicts the most common outcome, a simple regression on free fields (type, size, age, +1 count), and a small LLM. Set the go/no-go bar before running.
2. **Only if Jev clearly wins:** build a separate `sase-jev` plugin. It would run one scheduled routine that scores the triage queue and attaches its scores as advisory notes. It would never resolve gates or close beads, it would use a pinned model version, and if Jev is down sase behaves exactly as it does today.
3. **Only when a second use case has its own labeled data:** build a general `sase decide` command, with the policy in the Rust core and Jev as one of several backends.

Sources:
- [Wikipedia: Jev (AI model)](https://en.wikipedia.org/wiki/Jev_(AI_model))
- [TypeSafe docs: Models](https://docs.typesafe.ai/models)
- [Victor Dibia: How Jev works](https://victordibia.com/explainers/jev/)
- [DataCamp: System One models / Jev](https://www.datacamp.com/blog/system-one-models-jev)
- [Flavio Copes: deep dive into Jev](https://flaviocopes.com/jev/)
- [Abrar Qasim: Jev API gotchas](https://abrarqasim.com/blog/typesafe-ai-jev-api-tutorial-choice-score-noul-and-the-gotchas/)
- [beri.net: independent evaluation](https://www.beri.net/article/typesafe-jev-typed-decision-model-calibration-decomposition-shadow-eval)
- [arXiv 2609.30216: Jev in the Wild](https://arxiv.org/html/2609.30216v1)
- [MindStudio: Jev use cases tested](https://www.mindstudio.ai/blog/jev-use-cases-automation)
- [Pydantic AI: TypeSafe (Jev)](https://pydantic.dev/docs/ai/models/typesafe/)
- [Hermes Agent: jev-model-router plugin](https://hermes-agent.nousresearch.com/docs/plugins/jev-model-router)
- [MarkTechPost: Jev coding guide](https://www.marktechpost.com/2026/09/23/a-coding-guide-to-typesafe-ai-jev/)
- [MarkTechPost: Jev release coverage](https://www.marktechpost.com/2026/09/19/typesafe-ai-releases-jev/)
- [jev-guardrails comparison (search result summary only)](https://github.com/deepansh-saxena/jev-guardrails)
- [arXiv 2606.14517: DoS attacks on LLM-based agent guardrails](https://arxiv.org/pdf/2606.14517)
