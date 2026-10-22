# Chat History - ace-run (research.3v.grk)

- **TIMESTAMP:** 2026-10-06 16:54:36 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3v.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_163905.md`

## Prompt

%id(grk, clan=research.3v)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3v.cdx`, `research.3v.cld`, `research.3v.mus`, `research.3v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the `%wait` directive, epic-bead linking, and TUI wait states independently, then write a `__grk` report with a recommended design. First I'll load the research/macros/beads skills and locate the current wait implementation.

I'll load the wait/macros/beads/TUI reference memory and open the research sidecar next, then map the current `%wait` implementation.

The wait contract, epic linking, and TUI wait states are the next code paths I’ll map in the primary tree and sase-core.

The wait parser and TUI already support beads; next I’ll read those contracts and how epic creation links back to the creating agent.

I have enough of the wait, epic-backfill, and TUI contracts to write the design report: the gap is real, and the risky part is discovery plus the default.

**Yes, build this — as opt-in late-bound bead-close, not as default-on `%wait:agent`.** The report is `research:202610/wait_for_epic_keyword_design__grk.md` (snapshot `file:explicit:983c0a276a7f674b0d804fe9`).

The idea is sound. `docs/axe.md` already says a wait on an epic-approved planner waits for the planner, not the host-owned epic. Today you copy the new epic ID into `%wait(bead=…)` after it exists. That glue belongs in `%wait`.

Three changes to the request are load-bearing:

1. **Opt-in.** `%wait:builder` must keep today’s meaning. `for_epic` is true only when authored, and only next to an agent name. Default-on would trap every swarm and `%repeat` chain on accidental epics.
2. **Created vs assigned.** Do not key off `epic_bead_id` alone. Planners get it after back-fill; phase/land agents get it because they *work* the parent. Naive use waits for the wrong bead. Add `created_epic_bead_ids` and a `created` / `created-by` projection.
3. **Creation-settled, then close.** Agent-done is too early. Plan submit, `epic_approved`, and `EPIC APPROVED` all happen before the ID exists. Stay parked until creation produces an ID or settles as “no epic,” then use ordinary bead-close. Failed epic launch fail-closes (never-self-resolve), same as a failed agent dep.

Recommended spelling:

```text
%wait(builder, for_epic=true)
```

Runtime: one parked runner, two phases. Rebind `waiting.json` after creation settles (`wait_for_beads` + `wait_epic_bindings`), then the existing close gate. Compact TUI handoff: `WAITING ▶1 ★` → `WAITING ✓1 ★…` → `WAITING ★ ◐ sase-64`, with the Wait: lanes dropping the agent and naming the epic `via builder`.

I would not add a new directive, a synthetic `--epic` session member, or a hood wait on the epic ID (hoods snapshot at waiter launch, when those workers do not exist yet).
