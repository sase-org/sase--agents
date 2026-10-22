# Chat History - ace-run (research.4f.cld)

- **TIMESTAMP:** 2026-10-13 17:47:10 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4f.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_172545.md`

## Prompt

%id(cld, clan=research.4f)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4f.cdx`, `research.4f.grk`, `research.4f.mus`, `research.4f.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
am thinking about implementing some form of evals for sase.

- See the related research files (I think one of the Databricks research files were the
  ones to first suggest this) in the research sidecar repo and in the private
  bbugyi200/job--research GitHub repo for context.
- I think I am going to implement evals using goals somehow, which do not exist yet
  (review recent related research--note that I've done some thrashing on the
  requirements for this one, so favor more recent research files related to goals).
- Also, see my annotations in the
  ~/bob/ref/papers/2026_goals_as_first_class_abstractions_in_human_ai_collaboration_automationxp26.md
  file (and the corresponding research file) for some ideas (that I mostly agree with)
  on what goals should be.

I'm new to evals and am still thinking through goals. Can you do some research with the
goal of finding some articles or papers that inspire me / help me think through all of
this? End your analysis with a ranked list of articles/papers that you think I should
consider reading. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Reading Bryan's goal-paper annotations and the prior goals/Databricks research before searching the web for eval literature.

Now reviewing the latest goals research and SASE's recorded goal decisions.

Reviewing the September goal-verification research, then moving to web research on evals.

Now checking which eval readings prior SASE research already recommended, to avoid repeats.

Next: verifying candidate readings on the web and checking Bryan's reading library.

Core sources verified. Now searching for goal-specific eval work and a few remaining candidates.

Running the library check on all candidates in one batch.

Library checked; quickly verifying one already-queued paper that looks directly relevant, then writing the report.

I have enough verified material. Writing the report now.

Registering the report as a durable artifact.

I wrote the report to `202610/goal_driven_evals_reading_list__cld.md` in the research repo and registered it as `research:202610/goal_driven_evals_reading_list__cld.md` (artifact `file:explicit:4ae66fa6b5286b8e585f35e1`). The host will commit it after this turn ends.

**Main finding:** the goals design already contains most of an eval system.
- A goal (intent, outcome, criteria, original prompt) is an eval *task*.
- A bound turn is a *trial*, and a claim with evidence is the agent grading itself.
- Your verify or reject verdict is the *gold label* every cheaper grader gets checked against.

The readings suggest three evals that come out of the goal lifecycle almost for free:
1. **Live statistics:** how often each model's claims get verified, and coded reasons for rejections. The goals design's success metrics already list "verify/reject rates per model."
2. **Replay:** a verified code goal, rerun from its start commit with git history sealed off, is a benchmark task. This is the Databricks eval-pilot spec, except goals choose the tasks and supply the prompt, the rubric and the label.
3. **Judge calibration:** your verdicts measure how well an automated claim-checker agrees with you before you trust it to sort the Needs Review lane.

**Warnings from the literature:**
- **Criteria drift:** you find out what "done" means by looking at outputs.
- **Tests overstate:** in METR's study, 38% of agent PRs passed the tests and none were mergeable.
- **Requirements and evals are both approximations:** written requirements only approximate intent, and an eval only approximates the real environment.
- **Agents overrate themselves:** in one study, agents with 22% actual success predicted 77%.
- **Replays leak answers:** the correct solution can sit in git history unless you cut the run off from it.

That overconfidence paper, together with METR's time-horizon work, is the closest thing I found to an answer for your "Predictive capability?" annotation.

**Ranked reading list:**
1. Anthropic, "Demystifying evals for AI agents" — already queued in your library.
2. Krentsel, …, Zaharia, Stoica, "Reality Is the Final Verifier" — already queued. It's the best frame for how goals and evals relate.
3. Databricks, "Benchmarking Coding Agents on Databricks' Multi-Million Line Codebase" (July 2026) — the eval pilot, done for real.
4. Shankar et al., "Who Validates the Validators?" — the criteria-drift paper.
5. Husain & Shankar, "AI Evals: Everything You Need to Know" — the evals FAQ.
6. METR, "Algorithmic vs. Holistic Evaluation."
7. Shunyu Yao, "The Second Half."
8. Agent-as-a-Judge, with PaperBench's rubric trees (hierarchical goals).
9. "Agentic Uncertainty Reveals Agentic Overconfidence," with METR's time horizons.
10. Braintrust, "Evals are the new PRD," with Tian Pan, "The Eval Suite That Became the Spec Nobody Agreed To."
11. "Evaluating Goal Drift in Language Model Agents," with PushBench.
12. The Agentic Benchmark Checklist paper, with Jarmak's coding-agents monograph.
13. Anthropic, "Quantifying infrastructure noise in agentic coding evals," with τ-bench and "AI Agents That Matter."
14. Jason Wei, "Asymmetry of verification and verifier's rule."
15. HealthBench's per-conversation rubrics, with TICK.

The report also has honorable mentions, open questions to read with, and `bob ref create` lines for the top unread picks. I didn't run any of them. I left out readings your two October goals lists already ranked.

Library check: 2 of 33 candidates already in your library (0 finished).
