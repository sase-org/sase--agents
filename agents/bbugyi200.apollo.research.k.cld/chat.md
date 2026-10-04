# Chat History - ace-run (research.k.cld)

- **TIMESTAMP:** 2026-09-28 12:49:17 EDT
- **MODEL:** claude/opus
- **AGENT:** research.k.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_122749.md`

## Prompt

%id(cld, clan=research.k)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.k.cdx`, `research.k.grk`, `research.k.mus`, `research.k.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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

I've read the roadmap; next I'm checking the sase-1bu epic bead and the design's stated motivation before critiquing.

Progress: apollo's notification store shows completions are only ~29% of notifications (task-triage pings are larger). Now checking athena, where most agents run, for the same breakdown.

Found the original Goals request transcript on athena; extracting just your prompt text from it.

Almost done gathering evidence. Quick check on what the notification `read` flag means before I cite it, then I'll write the report.

I have the evidence I need. Spot-checking the two key code references before writing.

Writing the report now.

Report written. Quick verification of one claim (whether the final-declaration wire rejects unknown fields) before registering.

Claim holds: the finalizer wire structs are `deny_unknown_fields`. Registering the report as an artifact.

Registered as `file:explicit:68c8531599aef66b7773ab8a`. Now submitting the final declaration.

My recommendation is **not to start G2–G6 now.** Let the G1 landing-fixes epic (`sase-1bu.8`) finish, then pause Goals. Build your idea first, as a single rule in the host rather than per-swarm settings, and decide on Goals again in about two weeks.

**Your idea works.** I sorted last week's notifications on athena. There were 883 "agent finished successfully" pings, and most came from agents that the existing clan and epic records already mark as not the final one:

| Where the pings came from | Share of the 883 |
|---|---|
| Epic phase agents | 49% |
| Swarm researchers | 12% |
| Other clan fan-outs (mostly `toobig-*`) | 11% |
| Standalone agents (questions, children, ad hoc) | 13% |
| Epic land agents | 9% |
| Swarm leads and tail members | 5% |
| Routine runs | 1% |

The rule I'd build:
- **Epic phases:** silent.
- **Clans:** one ping per clan, sent by whichever member finishes last.
- **Failures:** always ping.
- **Override:** a `%notify` directive and an `outcomes | all` config switch.

That rule would have cut success pings by about 72%, to roughly 245 a week. The design's own estimate for the finished Goals feature is about 310 pings a week, so the rule matches or beats it. It lands in days, adds nothing to each agent turn, and needs no model judgment.

- **Put it in the host, not in each swarm.** Epic phases are half the pings and aren't swarms at all. Also, the lead-researcher `.final` name is only a naming convention, and when a swarm's optional image or critique agents run, `.final` isn't the last one to finish.
- **Existing settings can't do it.** `ace.notification_rules` only changes the popup and the sound; the notification is still stored as unread and still reaches Telegram. `%hide` hides the agent's row and still leaves an unread dot. All success pings are sent from one function (`run_agent_runner_finalize.py:309`), so the change is small.

**This also undercuts the design's main objection.** It rejected a simpler "agent says it's done, no Goal object" approach because a researcher or phase agent can't know the whole job is finished. The host can, from the clan and epic records it already keeps. If the rule's pings still include too much unfinished work, add an optional done / still-going / needs-you field to the final declaration. That gives most of G3's "tell me what to verify" without the ledger, per-launch-path binding, drafts, or a new tab.

**Goals' other benefits are real but unproven.** You can test the cheapest one, a list of what you've asked for, by running G1's `sase goal new` by hand for two weeks. The cost of continuing is mostly what you'd have to own, not build time:
- About 29 more phases, touching every launch path and adding a required step to every agent turn.
- Two loops that depend on model judgment: claim honesty, and naming or adopting goals.
- About 30 new verify decisions a day for you.
- G1 alone added about 19k lines and needed an 18-defect fix-up epic.

After the rule, task triage becomes the biggest source of notifications: about 88 a day, counting the gates relayed from apollo. Goals does nothing for those.

**When to restart Goals:** if success pings stay above about 50 a day, if the rule silences things you needed, if you keep using the manual goal list, or if another person starts working on these projects. If one of those happens, restart with a smaller scope: binding goals only to plans, epics and explicit `%goal` launches, plus claims and the tab. Leave the "every agent turn gets a goal" drafts and adoption (G4) for a later decision.

I saved the report and registered it as an artifact (`file:explicit:68c8531599aef66b7773ab8a`), and it's committed through the final declaration. The report covers the full traffic breakdown, the rule table with edge cases, the gaps the rule leaves (child agents launched by other agents have no parent link; `%dispatch` completions stay on the remote machine), and a comparison of the options.

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202609/goals_vs_outcome_shaped_notifications__cld.md`
