# Chat History - ace-run (research.2m.cdx)

- **TIMESTAMP:** 2026-09-26 12:55:48 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.2m.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_123905.md`

## Prompt

#gh:gh_sase-org__sase %id(cdx, clan=research.2m)
%m:codex/gpt-5.6-sol@xhigh %q(1.5x, w=0.25)

You are researcher cdx in a 4-researcher swarm.
The other researchers, `research.2m.grk`, `research.2m.mus`, `research.2m.gem`, are independently investigating the same request and will write their own self-named reports ending in `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

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
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
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

I’m using the SASE repository and audited-memory skills first because the report belongs to a linked research repo and the design touches artifact references, the TUI, and generated agent skills. I’ll inspect the current implementation and relevant precedents independently, then write and register the `__cdx.md` snapshot without consulting peer reports.

The relevant SASE memory confirms two important constraints: agent skills are generated from in-repo templates, and explicit research snapshots are immutable artifacts whose source file remains in the sidecar. I’m now tracing the actual launch, plan, finalizer, artifact-link, and TUI data paths so the recommendation fits the present architecture rather than assuming a greenfield design.

A key design tension is emerging: enforcing a goal inside the model’s first message cannot guarantee that every run has one, and it adds a network/read penalty to every conversation. SASE already knows the original prompt, project, agent identity, plan association, and finalizer set before the provider starts, so I’m evaluating a launch-boundary assignment with model-visible context and a finalizer decision as the stronger invariant.

The architecture now supports a concrete path: goals should be assigned before provider launch, inherited across retries/follow-ups, and stored as first-class project intent—not created by a mandatory first-turn model ritual. I’m tightening the lifecycle around planner handoffs, crashes, multi-agent work, and the distinction between “agent claims done” and “human verified,” because those are where a superficially simple goal field would become unreliable.

The recommended shape is now stable: one durable goal per user intent, many agents may contribute; launch-time binding is mandatory; plan `goal:` refines the same record; normal exits must submit `keep_open` or `close`; and closing is a host-validated completion claim backed by immutable artifacts and verification receipts. I’m writing the report with the exact data model, failure semantics, storage/index design, TUI layout, and staged implementation.

The report is written and passes a whitespace/diff check. Its main recommendation explicitly rejects the fragile first-message skill approach, preserves planner goals across handoff, and makes a close claim atomically carry its evidence links. I’m registering the exact file now as the requested immutable research snapshot.

Research completed and registered as a durable snapshot.

- Report: [goal_lifecycle_provenance_and_fast_active_index__cdx.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202609/goal_lifecycle_provenance_and_fast_active_index__cdx.md)
- Artifact: `file:explicit:6ea0e1bfe646fa38aa3ce73c`

Core recommendation: assign goals at the host launch boundary, carry one goal across collaborating agents and plans, require a host-validated goal finalizer, and distinguish an agent’s completion claim from human verification. Active goals should be served from an active-only materialized index, giving `O(n_active)` access independent of completed history.
