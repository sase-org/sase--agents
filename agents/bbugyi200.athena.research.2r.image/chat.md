# Chat History - ace-run (research.2r.image)

- **TIMESTAMP:** 2026-09-27 12:22:47 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2r.image
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_111456.md`

## Prompt

%id(image, clan=research.2r) %model:@image
%wait:research.2r.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:6549340ba990647ef16c014191a4c25f`

- **Node:** `agent-delta:20260927111501:094f3d91028dec0f`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260927111501:094f3d91028dec0f.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

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
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

### Assistant

Read the cdx report; now reading the other four reports and the prior goal_outcomes research.

Verifying the disputed storage claims (agents vs beads sidecar) against the docs and code now.

Checking code facts the reports disagree on (finalizer config, `SASE_PLAN` scrubbing, parent lineage, jump handler, TUI tabs).

Checking how the new Final deck and the directive system could host the Goal decision, then I'll write the merged report.

Inputs verified. Now moving the five reports into the new stem directory in my research checkout.

All five reports are moved into `sase_goals_design/`. Writing the consolidated report now.

Facts check out. Verifying the final layout, then declaring the turn.

I merged all five reports and my own checks into one report: `202609/sase_goals_design/sase_goals_design.md` in the research sidecar. The five source reports sit beside it as `sase_goals_design__{cdx,cld,grk,mus,gem}.md`, and the commit was declared to the host.

**Verdict: build Goals, but change five things in how you proposed it.** All five researchers and the prior report agree the idea is right, and the local run history backs it up. Athena logged 2,048 sase agent runs in the last 7 days, which the cld report groups into roughly 310 distinct outcomes, or about 6.6 runs per outcome. Moving your attention from "an agent stopped" to "a goal is claimed complete" would cut pings about sixfold.

**The five changes to your requirements:**
1. **The host guarantees the goal, and the agent names it.**
   - Checking `SASE_PLAN` won't work. It is removed on every spawn, and epic phase agents deliberately don't use it, so about 840 epic runs a week would each create a new goal.
   - Instead, when an agent launches, the host binds it to a goal from what it already knows: an explicit `%goal`, the session, the plan, the clan, the parent agent, or the routine.
   - If none of those apply, the host creates a draft goal. The agent's first step is to name it or adopt an existing active goal. You never have to write a goal, and agents do set their own.
2. **Agents claim a goal; you close it.** A new required goal finalizer makes every turn choose "keep open" or "claim."
   - A claim must carry evidence links you can click through to, mostly gathered by the host (the commit, the reply, the plan, test receipts).
   - It also needs 1–3 "check it" steps for you and any gaps the agent admits.
   - Tests are required only if a project opts in.
3. **Planners are no longer exempt.** Proposing a plan names the goal from the plan's title and goal text. Plan approval is the decision point for plan-only requests.
4. **Your follow-ups count as goal events.** Replying to an agent whose goal is awaiting review retracts the claim, with your reply as the feedback. A follow-up after the goal is done starts a new goal linked to the old one.
5. **"O(n) active goals" becomes O(n unsettled goals).** Claimed goals waiting for you stay in the fast set, and reads show how recently they synced rather than promising every machine is instantly current.

**Where the researchers disagreed, and what I picked:**
- **Storage:** a new append-only goals ledger that can't produce git conflicts. It starts inside the beads sidecar repo and can split into its own repo later.
  - I rejected the agents sidecar because it syncs only when each owner edits separate files, and it rebuilds all its browsing pages after every pull.
  - The privacy argument between repos doesn't apply here: all four sase sidecars, including the agents sidecar with its prompts, are public on GitHub.
- **Where Goals appear:** a top-level `Goals` tab next to Agents, rather than a pane inside Artifacts. It has Review, Running and Idle lanes, and cards that read *You asked → Claim → Check it → Evidence*, with numbered jumps to every agent and artifact. On the Agents tab there's a goal chip, a Goal card in the FINAL deck, and a "by goal" grouping.
- **How you verify:** each claim opens one approval gate like the ones plans and questions already use, so you can verify, reject or drop it from the TUI, CLI, phone or Telegram. Reading or dismissing the notification never counts as verifying.
- **Answer-only goals:** these are acknowledged automatically when you open the answer. They are recorded as "acknowledged," not "verified."

**Gaps none of the reports covered:**
- Test receipts exist only on the machine that ran the tests, so a claim has to copy the receipt's summary into itself for other machines to show it.
- Child agents don't currently record which agent launched them, so goals can't be passed down yet. This needs fixing first.
- The handler that jumps from a notification to an agent can't reach an agent hidden in a collapsed group. This also needs fixing first.

The report ends with a five-phase rollout behind a `goals` feature flag, acceptance tests, and six open questions for you — for example, whether answers should settle when you open them or need an explicit verify.

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<source-stem>_infographic.png` in the same directory.


## Response

An infographic illustrating the core design, architecture, and verification model from [`sase_goals_design.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/sase_goals_design/sase_goals_design.md) has been generated and saved to the research sidecar repository.

### Saved Infographic File
- **Target File:** [`sase_goals_design_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/sase_goals_design/sase_goals_design_infographic.png)
- **Directory:** `sase/repos/research/202609/sase_goals_design/`
- **Format & Dimensions:** 848 × 1264 (2:3 vertical poster layout), 8-bit RGB PNG

---

### Key Architectural Concepts Visualized

The infographic visually summarizes the five core mechanisms and structural components defined in the research report:

1. **Host-Enforced Pre-Launch Binding Ladder:**
   - Pre-launch resolution order: `%goal:<id>` directive / session follow-up → Plan `goal_id` → Clan / Parent / Bead / Routine → Fallback to a host-created machine-local **Draft Goal** (`⌖`).
   - Draft turns trigger `/sase_goal` (`sase goal name` or `sase goal adopt`) at turn start without imposing prompt crafting burdens on the user.

2. **Goal Lifecycle & State Machine:**
   - Lifecycle flow: `Draft` ──*(name/adopt)*──► `Active (Running / Idle)` ──*(claim + evidence)*──► `Review` ──*(verify / ack)*──► `Done`.
   - Rejection loop: `Review` ──*(reject + feedback / user follow-up)*──► `Active`.
   - Cancellation path: `[Review / Active]` ──*(drop / merge)*──► `Dropped`.

3. **TUI "Goals" Tab & 30-Second Review Card:**
   - **Top-level Goals tab** (`Agents | Goals ⌖2 | Artifacts | Services`) with persistent `inbox: ⌖2` badge.
   - **Lane Layout:** `REVIEW` (needs human decision), `RUNNING` (active live contributors), and `IDLE` (no live contributors).
   - **Review Card Layout:** *YOU ASKED* (original prompt preview) → *OUTCOME* (target definition of done) → *CLAIM* (agent claim sentence + evidence strength badge) → *CHECK IT* (1–3 actionable verification steps) → *EVIDENCE* (numbered jump chips: `@commit`, test receipts, `@reply`) → *GAPS* (admitted boundaries/limitations).
   - **Quick Actions:** <kbd>v</kbd> Verify, <kbd>r</kbd> Reject, <kbd>x</kbd> Drop, <kbd>p</kbd> Prompt.

4. **The `builtin@goal` Finalizer & Evidence Contract:**
   - Executes after `builtin@commit` on normal turns.
   - Decision options: `keep_open` (with a progress note) vs. `claim`.
   - Strict evidence rules: resolvable typed refs, host-gathered candidates, embedded test receipt snapshots, and unforgeable provenance.

5. **Conflict-Free Storage & $O(n_{\text{unsettled}})$ Performance:**
   - Append-only event store (`goals/items/<id>/events/<ulid>.json`) + lightweight `goals/live/<id>` markers.
   - Zero in-place edits prevent git rebase conflicts.
   - Fast $O(n_{\text{unsettled}})$ local projection with visible sync watermark (`synced 12s ago`), completely ignoring historical settled goals.
