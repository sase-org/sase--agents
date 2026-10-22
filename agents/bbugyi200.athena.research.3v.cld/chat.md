# Chat History - ace-run (research.3v.cld)

- **TIMESTAMP:** 2026-10-06 17:04:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3v.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_163905.md`

## Prompt

%id(cld, clan=research.3v)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3v.cdx`, `research.3v.grk`, `research.3v.mus`, `research.3v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add a `for_epic=<true|false>` keyword input to the `%wait` directive.

- This input would default to `true` when a sase agent name is provided as an argument
  alongside it (we should throw an error and/or show diagnostic warnings if a user
  attempts to use this input without an agent name) and will trigger a new behavior.
- Namely, when `for_epic=true`, the sase agent that is launched from that prompt should
  wait for the agent specified by the `%wait` directive AND should also wait for any
  epic bead that this agent may or may not create.
- In order to make this work reliably, we will probably need to make sure that
  artifact/bead links are established consistently from the sase agent that creates an
  epic bead to that epic bead. I think we already have the infrastructure set up for
  this.
- We will also want to make it very clear to the user in the TUI somehow when an agent
  has stopped waiting for the agent it specified via the `%wait` directive and is now
  waiting for the epic bead that agent created instead.
- The goal of this feature is to allow users to launch sase agents earlier than they can
  now in some cases. Sometimes, for example, I need to wait for an agent to create an
  epic before I can launch a prompt (so I can pass that epic bead ID to the `%wait`
  directive's `bead` input). This feature makes it so I do not need to do that anymore.
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

I'm mapping how `%wait`, epic creation and the TUI wait display work in the codebase. Next I'll confirm the planner's `done.json` and `epic_bead_id` timing and check the Rust directive contract.

I'm opening the linked `sase-core` repo to check where the Rust directive contract defines the `%wait` keywords.

I'm reading the feature-flag and macros notes, plus the glossary terms I'll rely on, so the recommendation matches project conventions.

I have the line references I need, so I'm writing the report now.

Citations check out. Now registering the report as a durable artifact.

Registration succeeded. Now submitting the final declaration.

I've written the report and registered it as `research:202610/wait_for_epic_follow_through__cld.md` (artifact `explicit:1684e3b81388c756c5256d38`). The host commits it to the research repo after this turn. All conclusions come from reading the code in `sase` and the linked `sase-core`; I didn't run anything.

**Verdict:** it's a good idea, and defaulting to `true` is the right call. Today `%wait:planner` releases once the plan is approved or, at best, once the epic's phase agents are launched. That is almost never what you mean by "start after that agent's work". With the default on, a mistake means a waiter starts late instead of starting early on unfinished work. Waiting is also cheap: a parked waiter doesn't hold a workspace.

**Main risk: the link from agent to epic is not as solid as you expected.**
- The planner's `agent_meta.json` gets the epic ID under `epic_bead_id`, and that write is best-effort.
- Phase and land agents use the same key for the epic they *work on*, not one they created.
- A version keyed on that field would deadlock every epic: the land agent's `%wait:<epic>.1` would follow into `<epic>`, which only the land agent can close.
- The artifact-link graph can't be the source either. Planners usually have no commits, so they are never published and their links never appear.

**Requirement changes (all marked in the report):**
- **What the default covers:** agent-style targets in the same `%wait(...)` (names, `agent=`, a bare `%wait`, `@tribe`, sessions, clans). It does not cover `hood=`, `bead=`, `time=`, or a `<name>--plan` planner-row target.
- **Validation:** an error at launch plus an editor diagnostic, both with the same wording. Also an error when one target gets conflicting `for_epic` values in two directives.
- **No surprises for parked waiters:** the default is applied and stored when a waiter launches. Waiters launched before this feature never follow.
- **Which epics:** epics created by any run behind the target (gate, launch monitor, tale coder), not just the first run.
- **Pinning:** once a wait has moved to an epic, re-running the agent can't change it.
- **Deadlock guard:** a waiter never follows into an epic that contains its own bead.

**Recommended solution:**
1. **Record the epic when it is created.** `sase bead work` writes a new `created_epics.json` into the creating run's artifacts, at the point the epic can no longer be rolled back. An epic an agent creates directly with `sase bead create` gets recorded the same way. The plan's `bead_id:` field is an independent backup source.
2. **Turn the agent wait into a bead wait.** When an agent target finishes and it created an epic, the epic ID is added to the existing `wait_for_beads` list and pinned. Everything bead waits already do then applies, including syncing, run-now and editing with `w`.
3. **Show the change in the TUI:**
   - the agent row reads `WAITING ↪ ◐ sase-7k 2/5`, with a teal `↪`;
   - the detail panel reads `[agents] planner ✓ ↪ sase-7k ◐ 2/5 phases`;
   - a toast appears when the switch happens;
   - `{{ agents["planner"].epic_bead_id }}` lets the follow-up prompt name the epic.
4. **Ship in three phases, with no feature flag:**
   - recording the epic, which is invisible to users;
   - `for_epic=true` as an explicit opt-in;
   - then turning the default on.

   Each phase needs a regression test showing that an epic's land agent still gets released.

**Questions for you:**
- **Canceled epics:** should the waiter be released (matches `bead=` today) or stay parked? I recommend releasing with a clear toast.
- **`sase agent wait`:** should the command get matching `--for-epic/--no-for-epic` options?
- **Approval dialog:** the "Wait for" field would inherit the default; does it need a way to opt out?
- **Notice:** should the switch to the epic also create a silent notification-inbox entry?

I also found an existing bug you should know about. When a phase agent hands its phase to a child epic, the launch code (`_update_epic_launch_metadata`) appears to overwrite that agent's parent-epic ID with the child epic's ID. Step 1 above fixes it as a side effect.
