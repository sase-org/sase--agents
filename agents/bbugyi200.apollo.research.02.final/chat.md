# Chat History - ace-run (research.02.final)

- **TIMESTAMP:** 2026-10-02 11:34:20 EDT
- **MODEL:** claude/opus
- **AGENT:** research.02.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_110156.md`

## Prompt

%clan(research.02, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.02.final %m:@xlarge
%wait:research.02.cdx %wait:research.02.cld %wait:research.02.grk %wait:research.02.mus %wait:research.02.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.02.cdx`, `research.02.cld`, `research.02.grk`, `research.02.mus`, `research.02.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.02.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.02.linker`, can find it:

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

I'll read the saved output files with the Read tool in chunks.

Now I have all five reports. Let me verify the key claims and disagreements myself, starting with the codebase facts.

I've read all five reports and I'm checking the claims they disagree on. Next is the memory-read audit log, since cld and grk report very different decision and glossary usage numbers.

I'm simulating the decisions roster in its different render modes to check the claimed line savings against the real renderer and formatter.

zsh was treating `$c:A` as a path modifier, so I'm rerunning the AGENTS.md growth-history check with proper quoting.

I'm checking whether `sase memory init --check` actually runs on the lint path, as cld claimed.

I've confirmed the codebase facts. Now I'll spot-check the load-bearing external sources: the Claude Code memory guidance, the Vercel eval, and the AGENTS.md papers.

Those three sources check out. The search also found newer July–August 2026 papers that none of the five researchers cited, so I'll check what they found.

Everything I need is verified. Now I'll set up the consolidated directory in the research checkout and move the five reports into it.

Reports moved. Now I'll write the consolidated report.

Registration succeeded. Now the final declaration.

I've written and registered the consolidated report. Short answer: yes, get the generated `AGENTS.md` under 100 lines. But the line count matters less than adding an automatic budget check and stopping the renderer from inlining catalogs that grow over time. No rule or read trigger has to be removed to get there.

**What the evidence shows:**
- **Most of the bloat is generated, not authored.** Of the 283 lines, 145 are memory-web rosters, and the decisions roster alone is 90. The shared `sase.md` template adds another 76.
- **The file grows back after a trim.** It was trimmed to 227 lines on 2026-08-29 and is back to 283. Nearly all of that regrowth is the decisions roster: the webs section went from 56 to 145 lines while the reference section was cut from 76 to 33.
- **The decisions roster earns little.** In September only about 20 non-research runs (about 1.5% of runs) opened a decision. The rules ordinary coding agents need from it already reach them through `lint_and_test.md`, which 437 runs read, or are enforced by the harness.
- **Short triggers are the valuable part.** A 2–4 line "read X before Y" entry brings in hundreds of runs, so every reference trigger should stay.
- **Correction to one report.** grk counted each glossary or decision strand as a separate hit (727 and 214). Counted per run, cld's much lower numbers are right.
- **It's a real but not dominant cost.** I measured 284 recent Claude sessions: the first call's prompt is at least about 25k tokens, and the instruction files are about 20% of that. The median session makes 41 calls, mostly cached. So the stronger reasons are rule adherence and stopping the regrowth, not money.
- **Outside research agrees.** Newer studies found that loading context on demand didn't hurt correctness, and that short guidance tuned on real tasks beat a larger static file. Vercel's eval is the counterweight: agents often fail to fetch optional content, so the short pointers have to stay always loaded.

**Changes I'd make to your requirement:**
1. Budget lines and tokens together: at most 100 lines at the normal 88-column wrap and at most 1,600 tokens. Lines alone can be gamed with wider wrapping or `@imports`.
2. Aim for about 85–90 lines so the next note doesn't immediately break the limit.
3. Enforce it in `sase memory init --check` as a ratchet: start the limit at today's size and lower it as each phase lands.
4. Every always-loaded line must be either a rule that applies on most turns or a trigger pointing to on-demand content. Rules the harness already enforces get one line at most.
5. Never move the eight hard rules (`/sase_final`, `/sase_repo`, memory read/write routing, and so on) out of the file.
6. Judge success by agent behavior in the memory-read audit log, not just by line count.

**Recommended solution (all Python, no Rust-core work):**
- **Roster sizes:** add two compact roster styles, `names` (titles only) and `none` (a one-line count plus a browse command). Leave superseded records out of the file. Use `none` for decisions and `names` for the glossary and task types.
- **Shared template:** rewrite `memory-sase.template.md` from 76 lines to about 18–20. This also shrinks every other SASE project's file and your home `~/CLAUDE.md`, which is a deliberate product change.
- **Reference index:** make each of the 10 triggers one line.
- **Budget check:** add the line/token check with a cost-per-section table so whoever adds content sees what to demote.
- **Decision record:** write a new record that partly supersedes `webs-render-in-their-own-section`. That record already allows a scoped opt-out once inlining becomes a token-budget problem.

That should land at about 85–93 lines and 1,200–1,400 tokens; cld's mock, run through the project's own formatter, came out at 93 lines and about 1,205 tokens. Changing the decisions roster from `list` to `inline` is a one-line, no-code first step worth 53 lines.

I'd keep out: dynamic or keyword retrieval, `@imports`, moving rules into skills, and the existing minimal template (it drops the reference triggers). Two disagreements are settled in the report: no Rust-core work is needed, since nothing in memory rendering calls `sase_core_rs`; and gem's claim that Antigravity loads both `AGENTS.md` and `GEMINI.md` is unverified (only Grok's double load is documented).

**Files:**
- `202610/agent_instructions_budgeted_router/agent_instructions_budgeted_router__final.md` in the research repo, registered as `ref=file:explicit:22bdf90269affcdc26091c29`.
- The five researcher reports are moved into the same folder with their suffixes kept, and the research-repo commit is declared.
- Every step that edits memory still needs approval through `/sase_memory_write`.

Sources:
- [Claude Code memory docs](https://code.claude.com/docs/en/memory)
- [Gloaguen et al., Evaluating AGENTS.md](https://arxiv.org/abs/2602.11988)
- [Khatri, Two-Agent Ablation Study](https://arxiv.org/abs/2607.27250)
- [Probe-and-Refine Tuning](https://arxiv.org/abs/2606.20512)
- [Vercel, AGENTS.md outperforms skills](https://vercel.com/blog/agents-md-outperforms-skills-in-our-agent-evals)
