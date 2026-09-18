# Chat History - ace-run (research.6.cld)

- **TIMESTAMP:** 2026-09-18 18:12:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.6.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260918_174610.md`

## Prompt

%id(cld, clan=research.6) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.6.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I've been running out of tokens from all of my LLM providers
(claude, codex, and grok) pretty fast lately and have several solutions in mind to
address the issue. One of them is to optimize the sase size model aliases so I'm only
using the largest model that I need to get the task done and I am load balancing between
providers efficiently/fairly.

Can you do some research with the goal of helping me decide what model alias pools and
fallbacks I should use for the default values of sase's builtin (size) model aliases?
Also, critique this plan in general. Is this a good idea? Would you take a different
approach? Make any adjustments to the requirements that you think are justified but
clearly call these out. End your analysis with a recommended solution / set of model
alias definitions. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

Reading how SASE resolves the size aliases (pool picking, fallback chains, usage-limit disables) before I look at models and usage data.

Now checking how sizes are assigned to phases/tales and what the user's live config and usage data look like.

Pulling historical launch metadata to measure which aliases/models actually consume the budget.

Aggregating per-agent `usage.json` token counts by alias/provider/model across the retained agent history.

Checking how plan/gate/monitor successors pick their model (they seem to inherit the parent's concrete model).

Web research is back. Now verifying the model catalogs SASE knows about (Fable 5 vs 5.1, Terra/Luna, grok variants).

Confirmed the user's Codex account offers Terra and Luna. Pulling their descriptions, then checking the Claude and Grok side.

Codex rollouts carry both token totals and the live weekly `used_percent`, so I can measure actual allowance burn per model. Parsing all September sessions.

gpt-5.5@xhigh (the `@medium` Codex member) looks like ~78% of Codex spend. Calibrating credits against the observed weekly `used_percent`.

Now the same analysis for Claude transcripts (API-equivalent cost per model/session).

Anthropic's cost-per-solved-task figures would change the Claude recommendation a lot, so I'm checking them against the source.

Verified: Fable 5→5.1 is ~43% cheaper per solved task, and Opus 5 at low/medium effort is far cheaper than at default. Checking today's per-provider launch mix against the Grok burn.

Notable: a usage-limit hit on any Claude model (including the Fable-only sub-cap) disables the whole `claude` provider. Checking whether other fleet machines share these accounts before I calibrate.

Sol sessions cost ~14× less than gpt-5.5 sessions; checking whether that's the model, the task mix, or an accounting artifact.

Checking whether SASE already has a temporary global effort override that could serve as an "economy mode" lever.

Found that alias-borne efforts outrank the temporary effort override, so there's no one-switch "economy mode" today. Writing the report now.

Fixing two small numeric overstatements I spotted on re-check.

Now registering the report as a durable artifact.

Registered. Last step is the SASE final declaration.

I wrote the researcher B report, registered it as an artifact, and the host accepted the commit. My main conclusion: tuning the alias pools is the right place to act, but model size is a secondary setting. Most of your token burn comes from the implementation tiers (`@medium` and `@small`) running at `xhigh` effort, and from one expensive model that Codex is retiring.

- **Report:** `sase/repos/research/202609/size_alias_token_budget_routing__b.md`
- **Artifact:** `research:202609/size_alias_token_budget_routing__b.md` → `file:explicit:4c814a2fb50a0d77b80e7ad4`

**What apollo's own logs show:**
- **gpt-5.5 dominates Codex spend.** `codex/gpt-5.5@xhigh`, the Codex member of `@medium`, used 78% of all Codex credits since Sep 1 and 91% in the current weekly window. It costs 25–50% more per token than GPT-5.6 Sol, and it leaves Codex on **Oct 14**. A typical `@medium` run makes about 178 tool calls and rereads about 124k tokens of context each time. Planning sessions (`@large`) cost roughly a tenth as much per launch.
- **All three providers are nearly exhausted at once.** Claude is at 97% of its weekly limit (the Fable-only cap at 96%). Codex went from 0% to 87% in about 29 hours after you soft-disabled Claude and its load moved over. Grok is at 35%, though that reading is unreliable.
- **Demand exceeds supply.** At the current cost per launch, you're launching roughly 1.5–2× what the three subscriptions can supply. Balancing load between them can't fix that; when one runs out, the others take its share and run out faster.
- **SASE requests the older Fable.** It pins `claude-fable-5`, and every Fable request this week ran on Fable 5. Anthropic says Fable 5.1 costs 43% less per solved task at the same score.
- **One Claude limit takes all of Claude offline.** Usage-limit disables apply to the whole provider, so hitting the Fable-only cap also blocks Opus and Sonnet.

**Critique and requirement changes (called out in the report):**
- **Effort should count as part of "size".** Every vendor's data shows `xhigh` is past diminishing returns for coding. Anthropic measured Opus 5 at `low` solving more tasks than Sonnet 5 at default for about 30% of the cost per solved task.
- **"Fair" should mean pace, not equal launch counts:** each provider's allowance should last until its reset. That needs usage-driven soft-disables, not fixed weights. This knowingly departs from the earlier capacity-UX research, which declined to route on usage projections; I use the reading only to steer, never to block.
- **Default weights must not assume a plan.** Shipped defaults should use equal weights; your own weights belong in your config, calibrated from measured cost per launch.
- **No alias should use gpt-5.5 after Oct 14.**

**Recommended defaults:**
```
xsmall: claude/sonnet@low | codex/gpt-5.6-luna@medium | grok/grok-4.6@low | agy/gemini-3.8-flash-medium
small:  claude/opus@low | codex/gpt-5.6-terra@medium | grok/grok-4.6@medium
medium: claude/opus@medium | codex/gpt-5.6-terra@high | grok/grok-4.6@high
large:  (claude/opus@high | codex/gpt-5.6-sol@high) || grok/grok-4.6@high
xlarge: (claude/fable@high | codex/gpt-6-astra@high) || grok/grok-4.6@xhigh
```
- **Your config:** remove `default_effort: xhigh`, which quietly raises anything without an explicit effort. Also replace your three gpt-5.5 overrides before Oct 14.
- **Code changes needed:** add Terra, Luna and Fable 5.1 to SASE's model lists, and regenerate the alias table in the docs.

**Expected impact:** about half the token cost per unit of work. That rests on vendor benchmarks carrying over to SASE's tasks and on quality holding, so the report includes a one-to-two-week A/B check, run through the pools themselves, before trusting it.

**Caveats:**
- The numbers cover apollo only. Other machines or surfaces sharing these accounts could shift the absolute figures, but not the relative shares.
- Codex agents don't record per-agent token usage, so I rebuilt Codex costs from `~/.codex/sessions`.
- I didn't verify that `claude --model fable` resolves to Fable 5.1 on your installed CLI, because that would spend tokens.

**Follow-ups (not filed as beads, left for the lead to decide):**
- automatic soft-disables when a provider runs ahead of pace
- per-model usage-limit disables
- per-agent Codex cost records and a cost-per-landed-phase view
- a temporary effort cap as an "economy mode"
- relaunching at the next size up when a phase fails its checks
- trimming the context that implementation agents reread every turn
