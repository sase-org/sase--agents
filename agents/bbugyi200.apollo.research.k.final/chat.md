# Chat History - ace-run (research.k.final)

- **TIMESTAMP:** 2026-09-28 13:15:57 EDT
- **MODEL:** claude/opus
- **AGENT:** research.k.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_122749.md`

## Prompt

%clan(research.k, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm not sure about
our plans to implement "goals" for sase.

- See the sase_goals_epic_roadmap.md file in the research sidecar repo and the sase-1bu
  epic bead for context.
- In particular, if the only value-add is better notifications (so users are only
  notified when work they asked for is complete), couldn't we just customize xprompt
  swarms and/or agent clans to only send a completion notification for certain agents?

Can you do some research with the goal of critiquing this idea and helping me decide
whether I should press forward with this or not? End your analysis with a
recommendation.]]) %id:research.k.final %m:@xlarge
%wait:research.k.cdx %wait:research.k.cld %wait:research.k.grk %wait:research.k.mus %wait:research.k.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm not sure about
our plans to implement "goals" for sase.

- See the sase_goals_epic_roadmap.md file in the research sidecar repo and the sase-1bu
  epic bead for context.
- In particular, if the only value-add is better notifications (so users are only
  notified when work they asked for is complete), couldn't we just customize xprompt
  swarms and/or agent clans to only send a completion notification for certain agents?

Can you do some research with the goal of critiquing this idea and helping me decide
whether I should press forward with this or not? End your analysis with a
recommendation.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.k.cdx`, `research.k.cld`, `research.k.grk`, `research.k.mus`, `research.k.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Now checking the code facts the reports disagree on, such as whether epic agents belong to clans and whether the old deferral mechanism exists.

G1's landing-fix epic is one phase from done. I'm now moving the five reports into a new subdirectory and writing the consolidated report.

The consolidated report is written and all six files are in place. Last step is submitting the turn's final declaration.

My recommendation is to not press forward with G2–G6 now. Finish G1's landing fixes, then build your notification idea as one rule inside SASE itself rather than by editing each xprompt. Re-decide on Goals in about two weeks.

**Is better notifications the only value-add?** On paper, no. Goals also promises a verify/reject step backed by evidence, a list of the outcomes you're currently trying to get done, and continuity across follow-ups and relaunches. But notifications are the only one with evidence of real pain today. The others are unproven, and each can be tested cheaply. For example, the G1 manual `sase goal new/list` already exists and costs nothing to try.

**Could clans and swarms handle it?** Yes, and better than Goals would, but not by customizing each xprompt. Those per-template tweaks would miss epics (the largest source of pings) and break when the optional critique/image agents run after `.final`. Instead, add one rule where success notifications are sent:
- Stay quiet when another agent is still waiting on this one, or when other members of its clan are still running.
- The last clan member to finish sends one ping for the whole group.
- Failures, questions and approvals always stay loud.

**Evidence:**
- **Traffic on this host (apollo), last week:** 77% of the 260 success pings came from clan members. One ping per clan cuts them to about 108, a 58% drop. cld's numbers for athena show a 72% cut, which is fewer pings than the design's own Goals end state (about 310 a week).
- **Epics are already covered.** Every epic phase and land agent is in the epic's clan, and the land agent waits on every phase. That means gem's "epics don't use clans" and grk's "waiting can't quiet epic phases" are both wrong.
- **The roadmap delivers quieter notifications last, and louder first.** G3 adds about 15% more notifications. G6, the only epic that silences success pings, can't start until G4 (every-turn drafts, the riskiest part) has landed, there are zero unbound turns, and a soak of at least 7 days has run.
- **The three reports that say keep going all skip G4 themselves.** That contradicts the accepted `goals-host-binds` decision (every turn gets a goal) and means G6's start condition could never be met. Their quieter inbox would also come from the same clan and plan structure the simple rule uses.
- **Task-triage gates are as big a stream as completions:** 277 versus 260 on apollo last week. Goals does nothing about them.

**Recommended steps:**
1. Finish `sase-1bu.8`; it has one phase left.
2. Don't write the G2 plan yet.
3. Build the rule as one task or a 3–4-phase epic, with a `%notify` override and a config switch back to today's behavior.
4. Point the next notification-noise effort at task triage.
5. Around 2026-10-12, restart Goals, limited to G2 and G3 on epics and explicit `%goal`, if any of these happen:
   - loud pings often point at work that isn't actually done;
   - the rule silenced something you needed, or you lost track of work spanning several launches;
   - you actually use the manual goal list;
   - a second person needs a shared list of open asks.
6. If none of those happen, archive the roadmap on purpose rather than letting it drift, and record that as a new decision.

The consolidated report and the five moved researcher reports are in `research:202609/goals_vs_structural_completion_notifications/`. The commit is declared to the host.
