%clan(research.2r, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add a new
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
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.2r.final %m:@xlarge
%wait:research.2r.cdx %wait:research.2r.cld %wait:research.2r.grk %wait:research.2r.mus %wait:research.2r.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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
- #beau

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
   dispatch's `research.2r.cdx`, `research.2r.cld`, `research.2r.grk`, `research.2r.mus`, `research.2r.gem` dependencies, matching by `wait_name` and the canonical research
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