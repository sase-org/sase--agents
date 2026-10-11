# Chat History - ace-run (1g)

- **TIMESTAMP:** 2026-09-27 17:17:28 EDT
- **MODEL:** claude/opus
- **AGENT:** 1g

## Prompt

#gh:gh_sase-org__sase What is the plan for setting the goals of xprompt swarms? For example, what will
the goal be for the researcher agents that run in the `#research_swarm` xprompt swarm?
Keep your report concise but beautiful. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge

## Response

I'm reading the SASE Goals design and roadmap research to find how swarm goals get set. Next I'll check the roadmap, the `#research_swarm` xprompt, and the goals epic beads.

I've mapped the design and the swarm's structure. Now I'm checking whether any Goals code or plan has landed, and how the individual reports differ on swarm goals.

Registration succeeded. Now the final declaration.

The plan is that an xprompt swarm gets **one** shared goal, not one per agent. So the `#research_swarm` researchers don't get goals of their own: they contribute to the swarm's goal, and the lead is the one that claims it. All of this is still design only. Today's `sase_goals_design` and `sase_goals_epic_roadmap` reports describe it, but there's no code, epic bead or plan yet, and swarm goals are scheduled for the fourth of six epics (G4).

**How a `#research_swarm` goal gets set:**
- **One draft goal for the whole swarm.** At launch the host binds every member of the swarm's clan to a single draft goal. The first member to run `sase goal name` writes the title and outcome; the others get `already named` back.
- **The goal's content.** The outcome is something like "a consolidated report answers `<question>` and gives a recommendation." It's written by whichever researcher names it first.
- **What researchers do.** Each researcher writes its own report (`__cdx.md`, `__cld.md`, …) as a contributor and finishes with `keep_open` plus a progress note. They can't claim, because the lead waits on them.
- **What the lead does.** The lead (`.final`) claims the goal with the consolidated report as evidence, plus "check it" steps and any gaps it admits. That opens one verification gate where you choose Verify, Reject or Drop. You get one signal instead of 3–5 "done" pings.

I checked the design against the actual swarm xprompt and found three gaps:
1. **The lead doesn't always claim.** With `critique=true` or `image=true`, those agents wait on the lead, so the lead counts as a contributor. The claim then goes to whichever of the critique or image agent finishes last, which could mean the infographic agent claims the research goal.
2. **The goal gets named from boilerplate.** Every researcher's prompt starts with "You are researcher cdx in a …-researcher swarm", so that's what the draft title shows and what the naming researcher sees. The actual question is only in the lead's clan summary.
3. **Unclear before G4.** Until then swarms have no goal. It hasn't been checked whether an explicit `%goal` on the swarm prompt would reach every agent.

The report is registered as `file:explicit:c5adfab258b62964ded12099` under the label `research:202609/xprompt_swarm_goals.md`, and it's declared for commit in the research repo.

Report: `sase/repos/research/202609/xprompt_swarm_goals.md`
