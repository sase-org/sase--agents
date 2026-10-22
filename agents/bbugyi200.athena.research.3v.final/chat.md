# Chat History - ace-run (research.3v.final)

- **TIMESTAMP:** 2026-10-06 17:27:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3v.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_163905.md`

## Prompt

%clan(research.3v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add a `for_epic=<true|false>` keyword input to the `%wait` directive.

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
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.3v.final %m:@xlarge
%wait:research.3v.cdx %wait:research.3v.cld %wait:research.3v.grk %wait:research.3v.mus %wait:research.3v.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3v.cdx`, `research.3v.cld`, `research.3v.grk`, `research.3v.mus`, `research.3v.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3v.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3v.linker`, can find it:

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
├── <name>__final.md
└── <name>_narration.md
```

## Response

Read grk, mus and gem; now reading the full cdx and cld reports before verifying claims in code.

Now verifying the key factual disagreements in code (planner lifecycle/session membership, `epic_bead_id` overload, generated waits, TUI colors).

Still verifying; now tracing what happens to the planner between plan proposal and approval.

Still verifying how a planner's session resolves across the plan gate and epic-launch monitor.

Still auditing which waits are machine-generated (epic phases, land agent, `%repeat`) since that decides whether a default-on flip is safe.

Still verifying — checking TUI glyph/color claims (teal vs gold star) and the existing wait-lane rendering.

Confirmed `produced-by` is stitch→agent only (no agent→bead creation relation). Checking whether wait resolution already has a Rust home, and how agents create epics directly.

Nearly done verifying; checking the existing epic-launch handoff records as a possible "launch pending/settled" signal.

Verification mostly done. Before finalizing the rollout and TUI recommendations, I'll read the relevant SASE reference memories (macros, flags, TUI).

Verification complete; checking two last details (runner fallback interval, tale coder session member) before writing.

Writing the consolidated report now. First, setting up the directory and moving the five reports.

Writing the consolidated final report.

Report written. Spot-checking a few cited paths before registering.

Now registering the consolidated report as a durable artifact.

Registered. Now submitting the final declaration.

I've merged the five reports and my own code checks into one final report, and registered it as an artifact for the linker. My recommendation is to build `%wait(…, for_epic=true|false)` and keep your default (on for agent targets), with a few guardrails. The host commits the research repo after this turn ends.

**Should you build it?** Yes; all five researchers agree. The strongest argument is one the code makes for you. Today `%wait:planner` already waits for the implementation when the planner picks a tale, because the tale's coder runs inside the planner's session. When the planner picks an epic, the wait stops at the launch. You can't know which one you'll get when you type the wait. Inside epics, SASE already pairs every phase-agent wait with a wait for that phase's bead to close, for the same reason.

**The default was the main disagreement.** cld and cdx backed default-on; grk, mus and gem rejected it. The objections mostly don't hold against the code:
- A plan reviewer already has to wait on `planner--plan`, which won't follow epics.
- Backlog epics an agent merely files are excluded; only epics actually launched from a plan count.
- The setting is fixed when each waiter launches, so waiters already parked keep today's meaning.

**Your assumption about links is only partly right.** The `epic_bead_id` field in `agent_meta.json` means "the epic I launched" for a planner, but "the epic I belong to" for phase and land agents. Reading it naively would deadlock every epic. No artifact-link relation records "agent created bead" yet (`produced-by` only covers stitch → agent).

**Recommended solution:**
1. **Record:** when an epic becomes durable, write `created_epics` into the creating run's metadata. Stop overwriting `epic_bead_id` on phase/land agents, and derive the agent → epic link from this record.
2. **Parse strictly:** the keyword applies per `%wait(...)`. Using it without an agent target is a hard error, with the same message at launch and in the editor. `--plan` rows never follow, and the waits `sase bead work` generates inside an epic emit `for_epic=false`.
3. **Resolve once, everywhere:** a small state machine goes `AGENT → LAUNCHING → FOLLOWING | NONE | BLOCKED`. "No epic" only counts once it's proven, and a failed launch keeps the waiter parked with a notification. On `FOLLOWING`, the wait becomes an ordinary bead wait on the epic, pinned so a re-run of the planner can't redirect it.
4. **TUI:** one new teal `↪`, the colour `EPIC CREATED` already uses. Rows read `WAITING ▶1 → WAITING ↪ epic… → WAITING ↪ ◐ sase-7k`, and the detail panel shows `planner ✓ ↪ sase-7k ◐ 2/5 phases`. Add one toast, a timeline milestone, and `{{ agents["planner"].created_epic }}` for the follow-up prompt.
5. **Ship as one epic in five phases:** record, keyword, follow logic, TUI, then flip the default. The flip should wait until a test proves an epic's own phases and land agent still release.

**Requirements I'm changing:**
- Using the keyword without an agent is an error, not a warning.
- The default is stored when each waiter launches, not applied to waits already parked.
- Only epics launched from a plan are followed.
- Everything the agent's session launches counts, and you wait for all of them.
- A followed wait is pinned to its epic.

All ten adjustments are in §4 of the report.

**Risks and open questions:**
- **Longer parking:** waiters on epic-launching agents will now stay parked for the epic's whole duration, and parked runners are resident processes. Check that the earlier host-resource work on parked runners has landed before flipping the default.
- **Starting at launch:** if you want a follow-up to start as soon as the epic is launched, you'll have to write `for_epic=false`.
- **Your calls:** whether a canceled epic should release its waiters, and whether `sase agent wait` should get a matching flag (§8).

**Files and steps:**
- The five reports moved to `202610/wait_follows_agent_into_epic/wait_follows_agent_into_epic__{cdx,cld,grk,mus,gem}.md`.
- Registration succeeded: `research:202610/wait_follows_agent_into_epic/wait_follows_agent_into_epic__final.md`, ref `file:explicit:01c960f6e178f69b5e447047`.
- I didn't create `<name>.md` or `<name>_narration.md`; the steps didn't call for them, so I assumed the linker produces them.
- I opened sase-core read-only and changed nothing there.

Files are in `202610/wait_follows_agent_into_epic/`:
- wait_follows_agent_into_epic__final.md
