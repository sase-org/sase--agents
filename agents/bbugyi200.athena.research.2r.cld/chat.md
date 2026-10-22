# Chat History - ace-run (research.2r.cld)

- **TIMESTAMP:** 2026-09-27 11:48:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2r.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_111456.md`

## Prompt

%id(cld, clan=research.2r)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2r.cdx`, `research.2r.grk`, `research.2r.mus`, `research.2r.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add a new
"Goals" functionality to sase.

- Goals should be associated with the original prompts that were used to launch the sase
  agent that created the goal.
- All sase agents MUST have a goal defined.
  - We already support a required `goal` field for tale / epic plans, so these should be
    used as an agent's goal whenever a plan file is associated with that agent.
  - Any sase agent that does not have a goal associated with it implicitly through a
    plan should be required to create a new goal or, ideally, link to an existing active
    goal.
  - One idea for implementing this would be to require that every sase agent that is NOT
    tasked with creating a plan using the /sase_plan skill (i.e. planner agents don't
    need to do this) check if the `SASE_PLAN` environment variable is set at the start
    of EVERY conversation. If not, it could invoke a new /sase_new_goal xprompt skill.
    This is just one thought, though. Think hard about the best way to solve this.
  - An example goal for an agent without an associated plan that couldn't find a related
    goal to link to might be to answer a user question.
- We should use a new finalizer that requires sase agents to explicitly decide whether
  or not to close the goal or leave it open. An agent that chooses to close a goal must
  provide evidence to the finalizer (that will then be linked to the goal somehow before
  closing it). Think hard about what we should require this evidence to be.
- The TUI should have a new "Goals" panel somewhere that users can use to see all active
  goals for a project. We should use artifact links to make it very easy for users to
  jump from this panel to any artifact and/or sase agent on the "Agents" tab linked to
  that goal.
- One motivation for this change is to start using newly done goals to notify me that I
  need to verify something. I currently use agent completion notifications for this,
  either directly or via the unread indicators on the agent tab. The problem with that
  approach is that not every agent that completes needs my attention like this (I really
  only need to be alerted when my agents claims that a goal which was set is now
  complete).
- The above requirements imply that sase agents need access to all active goals (really,
  any human/agent working on a sase project from any machine needs this access). This
  access needs to be lightning fast. More specifically, we should aim for `O(n)`
  performance, where `n` is the number of active goals (so done goals have no effect on
  performance).
- Review the goal_outcomes_and_verification.md file in the research sidecar repo before
  performing your own research. My thoughts on this research from what I read:
  - I like that outcomes are embraced as a primary value-add for this functionality but
    am worried that we did not focus enough on user experience. For example, how do I
    figure out, for a particular sase project, which goals are currently active? Once
    I've found that goal, how do I then jump to any artifact (including a running agent)
    that is linked with that goal?
  - I'm worried that we are not letting agents set their own goals. I might be wrong
    about this, but doesn't that mean that users would always need to set the goal
    explicitly? That doesn't sound like a good design, if so, since it adds an extra
    burden on the user crafting the prompt.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

Read the prior Goals synthesis. Next I'm surveying the current sase code (launch, finalizers, artifact links, TUI, notifications, sidecar sync) so the design fits what exists.

Still researching: now checking the tab bar, plan-propose hooks, and sidecar layout before I write the report.

Research is nearly complete. Checking the CLI and feature-flag conventions so the proposed `sase goal` commands and rollout flag match the house rules.

Writing the report now.

Registered. Now the final declaration.

I wrote the Goals report and registered it as an artifact. The research repo is set to commit it at the end of this turn.

- **Report:** `sase/repos/research/202609/goals_feature_design__cld.md`
- **Artifact:** `file:explicit:002ccc106a641627e0d1436c` (label `research:202609/goals_feature_design__cld.md`)

**Is it a good idea?** Yes. I counted last week's agent runs on athena for the sase project: 2,047 agent turns served about 310 outcomes, roughly 6.6 completion signals per outcome. Most of them don't need you. Agents are not the risk; your time is. About 30 new verify requests a day is only a win if each one takes seconds to judge, so most of the design effort goes into the review experience.

**Changes to your requirements (all flagged in §5):**
- **The host binds the goal and the agent names it**, instead of agents checking `SASE_PLAN`.
  - `SASE_PLAN` is removed at every spawn and never set for epic phase or land agents. The check would have wrongly created new goals for 839 of last week's turns and duplicated goals across swarms.
  - Instead, the launcher binds each goal from the plan, session, clan, parent, or routine. That covers about 90% of turns.
  - Otherwise it creates a draft from your prompt, and the agent's first step is to name it or link it to an existing active goal.
  - You never have to write a goal. Planners get theirs named automatically from the plan's `title`/`goal`.
- **Agents claim, you close.** The finalizer choice is `keep_open` or `claim`. A claim puts the goal in Review and notifies you; you verify or reject it (optionally relaunching with your feedback).
- **Evidence** is links you can click to check the work: commits, reports, plans, the agent's reply, test results. It also includes required "check it" steps and any gaps the agent admits. The host collects most links, so the agent can't fake them. Tests are required only if a project opts in.
- **"Active" includes claims awaiting your review**; verified and dropped goals cost nothing to read. Freshness across machines is local and fast, with a visible "synced N s ago", rather than instant everywhere.

**How this differs from the earlier `goal_outcomes_and_verification.md` research:**
- **Your agents-set-their-own-goals worry was right.** Its fallback just copied your prompt into the goal, and it linked to existing goals only when you picked one yourself.
- **I'd store goals elsewhere.** That report used the private agents sidecar. That repo only syncs cleanly because each machine writes its own separate files, and goals are shared state that several machines change.

**Recommended solution:**
- **Storage:** a goal ledger in the project's beads repo, made only of new event files plus one small marker per open goal. Nothing is edited in place, so git syncs can't conflict. Listing open goals reads only those markers. Prompt text stays private; the goal stores only a reference to it.
- **Goals tab** with three lanes: Review, Running, and Idle (goals nobody is working on). Each goal opens as a card: *You asked → Claim → Check it → Evidence → Gaps*. Every agent and artifact on it is a numbered jump.
- **Agents tab:** a goal chip on each agent, a GOAL section in its details, and a "by goal" grouping. An Artifacts ▸ Goal pane holds history.
- **Notifications:** successful completions go quiet. Claims notify loudly and stalled goals notify softly; errors and approvals are unchanged.
- **Rollout:** five phases behind a `goals` beta flag. Two existing bugs are fixed first:
  - Agents launched by other agents never record their parent, so they can't inherit its goal.
  - Jumping to an agent from a notification misses agents inside collapsed groups.

Section 10 of the report has six questions for you. The biggest are whether a question-type goal should settle once you read the answer, and whether you're fine with goal titles living in the beads repo, which is public for managed GitHub projects.
