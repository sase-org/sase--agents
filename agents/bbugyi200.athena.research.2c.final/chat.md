# Chat History - ace-run (research.2c.final)

- **TIMESTAMP:** 2026-09-23 13:46:56 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2c.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260923_131242.md`

## Prompt

%clan(research.2c, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I keep hearing about this Hermes agent
that is apparently a lot like OpenClaw and, maybe, a lot like this project. Can you do
some research with the goal of comparing and contrasting the Hermes project with this
project? End your analysis by giving sase a rating on how well it competes functionally
(don't consider popularity/adoption) with Hermes.]]) %id:research.2c.final %m:@xlarge
%wait:research.2c.cld %wait:research.2c.mus %wait:research.2c.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I keep hearing about this Hermes agent
that is apparently a lot like OpenClaw and, maybe, a lot like this project. Can you do
some research with the goal of comparing and contrasting the Hermes project with this
project? End your analysis by giving sase a rating on how well it competes functionally
(don't consider popularity/adoption) with Hermes.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.2c.cld`, `research.2c.mus`, `research.2c.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

I've read the cld report and am now reading the mus and gem reports before doing my own verification research.

Verification is done. Now I'm laying out the files in the research checkout and writing the consolidated report.

The consolidated report is written. Checking the final layout, then submitting the final declaration.

I've written the consolidated report, and I rate sase **5 / 10** as a functional competitor to Hermes. That is my own weighted score of about 5.2 across 14 dimensions of what Hermes offers. The overall number hides a sharp split:

| Domain | sase score |
| --- | --- |
| Supervised software engineering with many agents from different vendors (Claude Code, Codex, Grok Build and others) | about 8.5 / 10 |
| General always-on personal agent, which is Hermes's and OpenClaw's home ground | about 2 / 10 |

**Hermes vs OpenClaw.** Hermes is like OpenClaw: both are personal agents you talk to through chat apps, and Hermes ships a `hermes claw migrate` importer for OpenClaw setups. It is a rival that took over OpenClaw's users, not a fork. Its repo's first commit (July 2025) predates Clawdbot (November 2025), the project that was later renamed OpenClaw.

**Hermes vs sase.** The two only overlap in one area: running many agents on real repo work, tracking it, scheduling it and supervising it. Within that area:
- **sase is stronger.** It drives other vendors' coding CLIs natively, agents never commit themselves, and it has the plan → epic → phase → land-agent work model. Hermes's own docs say running Claude Code or Codex as Kanban workers is "not yet a paved path".
- **Hermes leads in a few places:** a built-in per-task review lane, pull-request checks gates, `/goal` loops, rollback, and real sandboxes.
- **Outside the overlap, sase doesn't compete.** It has no agent loop of its own, no self-learning, one chat platform, no sandbox, and no MCP or API server.

**Why the three researchers disagreed (5, 6 and 9):**
- **gem's 9 answers a different question.** It rates how good sase is at sase's own job, not how it stacks up against what Hermes does.
- **gem's picture of Hermes is out of date.** Checking the Hermes code, it does have a persistent task board with dependencies, a review lane, multi-agent support and links between machines.
- **The self-improvement claim was misattributed.** Gem credited Hermes with DSPy/GEPA self-improvement, but that lives in a separate repo of 8 commits that has been idle since June. It rewrites skill files offline and opens pull requests for human review; the real learning loop is a different, built-in mechanism.
- **gem was right about approvals.** Hermes approvals block the running process and are denied after 5 minutes, while sase's gates are durable records that can wait for days. So I scored sase's approval gates higher than cld did (8 vs 7).
- **mus scored sase's scheduling too high (8).** I used 5, close to cld's 4.5.

The changes that would move the rating most are:
1. Adding Hermes as an 8th provider through its headless `--oneshot --format stream-json` mode.
2. Letting agents search past chat transcripts.
3. Letting agents propose memory updates that a human then approves.

Together with a per-bead review lane and a pull-request checks gate, these could lift the score to about 6–6.5.

The files are laid out as requested, and the three original reports were moved in with their suffixes unchanged. I submitted the research-repo commit declaration, and the host will create the commit.

```text
202609/sase_vs_hermes_agent/
├── sase_vs_hermes_agent__cld.md
├── sase_vs_hermes_agent__mus.md
├── sase_vs_hermes_agent__gem.md
└── sase_vs_hermes_agent.md
```

Sources:
- [OpenClaw – Wikipedia](https://en.wikipedia.org/wiki/OpenClaw)
- [OpenClaw vs Hermes Agent – innfactory](https://innfactory.ai/en/blog/openclaw-vs-hermes-agent-comparison/)
- [OpenClaw vs Hermes Agent (2026) – Toolradar](https://toolradar.com/blog/openclaw-vs-hermes-agent)
- [OpenClaw vs Hermes Agent – Petronella](https://petronellatech.com/blog/openclaw-vs-hermes-agent-2026)
