# Chat History - ace-run (research.28.final)

- **TIMESTAMP:** 2026-09-22 11:53:11 EDT
- **MODEL:** claude/opus
- **AGENT:** research.28.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_105129.md`

## Prompt

%clan(research.28, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] We recently implemented the
`sase tool` command, which is just the first part of a larger plan (see the
sase_tool_epic_roadmap.md file in the research sidecar repo and the sase-135 epic bead
for context). I'm thinking about taking the next steps on this. Here's what I'm thinking
that those next steps should be:

- Add support for smoe way of enforcing that sase agents always use the `sase tool`
  command for certain commands. I want you to lead the design on this one, but one
  possible solution would be to implement a new `sase tool ensure-not-agent` command
  that commands (like the `just check` command, for example) could call at the start of
  their logic. This command could then fail if it detects a sase agent. Whatever
  solution we go with, make sure that sase agents are able to override this somehow (in
  case, for example, the `sase tool` command is broken).
- We should start making sase monitors wrap the command they run with the `sase tool`
  command. This should be possible since the `sase tool` command should be able to run
  any arbitrary command (you might need to implement this).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.28.final %m:@xlarge
%wait:research.28.cld %wait:research.28.mus %wait:research.28.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

We recently implemented the
`sase tool` command, which is just the first part of a larger plan (see the
sase_tool_epic_roadmap.md file in the research sidecar repo and the sase-135 epic bead
for context). I'm thinking about taking the next steps on this. Here's what I'm thinking
that those next steps should be:

- Add support for smoe way of enforcing that sase agents always use the `sase tool`
  command for certain commands. I want you to lead the design on this one, but one
  possible solution would be to implement a new `sase tool ensure-not-agent` command
  that commands (like the `just check` command, for example) could call at the start of
  their logic. This command could then fail if it detects a sase agent. Whatever
  solution we go with, make sure that sase agents are able to override this somehow (in
  case, for example, the `sase tool` command is broken).
- We should start making sase monitors wrap the command they run with the `sase tool`
  command. This should be possible since the `sase tool` command should be able to run
  any arbitrary command (you might need to implement this).

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
   in cld, mus, gem, belonging to this
   dispatch's `research.28.cld`, `research.28.mus`, `research.28.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Read the cld report. Now reading the mus and gem reports.

Confirmed the executor/ownership claims in code. Now checking beads, live adoption numbers, the Justfile, and the monitor host-completion binding.

Verified the host-completion binding reads `monitor_execution_argv`/`monitor_command`, so cld is right that the wrap must live only in the proc argv. Checking the monitor start path next.

Reproducing the kill-race bug independently in an isolated SASE_HOME.

Kill race reproduced 2/2 (wrapper SIGKILLed at 5.01 s, `sh`+`sleep` orphaned; cleaned up). Now classifying the adoption report's "ambiguous" bucket myself.

Since E1 landed, in-repo inline adoption is ~90%; most remaining raw heavy calls are in linked repos (sase-core etc.). Now checking what monitors actually run.

Now checking the ToolRun ledger's settlement states and ownership.

Ledger matches cld (13 `lost` check runs; 4 misowned by the epic-launch monitor). There's one risk no report raised: stdout/stderr interleaving under an owner. Testing it.

Research is done; moving the three reports into the new directory.

Reports moved. Before writing, I'll read the flags memory so I can settle the beta-flag question with evidence, not just by deferring to the reports.

Flag rules settled: no beta flag is needed. Filing the stream-interleaving defect I found as a task bead, via the required skill.

Filed `sase-16d`. Linking it to the related beads and marking it ready.

`sase-16d` is ready and linked. Writing the consolidated report now.

Report written. Checking the research repo's state and any formatting conventions.

Layout matches the spec. Finishing with the SASE final declaration.

I've written the consolidated report. My recommendation is to build both of your steps, but in a different shape than you proposed, and only after three bugs in `sase tool run` are fixed.

**Enforcement: drop `sase tool ensure-not-agent` and use a small shell guard inside the recipe.**
- **Rule:** an agent may run `check`/`check-full` only inside `sase tool run <that tool>` or with a bypass. "Not an agent" is the wrong rule, because `sase tool run check` still runs `just check` as the agent.
- **Why not a `sase` command:** the override exists for when `sase` is broken, and a `sase` subcommand fails in exactly that case. It would also add about 0.3 s to every human and CI run.
- **Design:** a ~20-line POSIX script, `tools/require_tool_run`, runs first in `check` and `check-full`. It reads three environment variables and never starts `sase`, taking about 1 ms:
  - `SASE_AGENT`, which agents already have;
  - a new `SASE_TOOL_NAME`, which `sase tool run` would always set;
  - a new `SASE_TOOL_BYPASS='<why>'` as the override.
- **One trap:** two researchers keyed the check on `SASE_TOOL_RUN_ID`. The code removes that variable when recording fails, so the guard would refuse a correctly wrapped run.
- **Refuse, don't silently redirect:** a `just` step can't replace the recipe it belongs to, and a redirect hides the behavior change.

**Monitor wrapping: yes, but narrower than "every monitor."** Running arbitrary commands already works (`sase tool run -- ARGV` shipped with the first epic, E1), so nothing new is needed there.
- **Wrap only the argv that actually runs.** The recorded monitor command must stay untouched, because prepared host completion checks that exact field.
- **Never wrap** epic launches or commands that already start with `sase tool run`.
- **Named upgrade:** a monitor running exactly `just check` becomes `sase tool run check`, not an ad-hoc run.
- **Scope:** v1 covers verify-profile monitors plus exact catalog commands. A new config field (`monitor.tool_wrap: off | verify | all`) can widen it later.

**Three bugs to fix first.** Both steps push more work through the wrapper, and it currently handles three cases worse than a raw command:
- **`sase-16c`:** epic phase agents inherit the epic launch's monitor id, so their runs get no compact output and no saved logs. A guard would force every phase agent onto this path.
- **`sase-16b`:** when a monitor times out, the wrapper is killed but the `just check` process tree keeps running. I reproduced this 2 out of 2 times.
- **`sase-16d` (new, which I filed):** when stdout and stderr go to the same place, such as a monitor log or `2>&1 | tail`, the wrapper prints all stdout first and then all stderr. I reproduced this 3 out of 3 times.

**How much the guard buys right now.** Since the adoption guidance landed on 2026-09-20, about 90% of heavy agent `just check` runs in the sase repo already go through `sase tool run`. One researcher's "1.96% adoption crisis" figure mostly counts runs from before that. About 80% of the remaining raw runs are in linked repos, mainly sase-core, which have no tool catalog, so a guard in sase's `Justfile` can't reach them. The guard is still worth building because it's cheap, and later planned work (receipt reuse, fail-closed capacity admission) needs every heavy run recorded by design. It does reverse the "bypass is measured, not enforced" clause of the `record-before-admit` decision, so it needs a new decision record.

**Delivery.** One small epic before E2, with four phases:
1. Fix ownership (`sase-16c`) and add `SASE_TOOL_NAME`.
2. Fix the orphaned processes and output order (`sase-16b`, `sase-16d`); this can run in parallel with phase 1.
3. The recipe guard.
4. Monitor wrapping.

No beta flag is needed.

**Decisions for you:**
- Should the monitor wrap default be `verify` (my pick) or `all`?
- Should the guard require an exact tool-name match (my pick) or accept any `sase tool run`?
- Should linked repos get tool catalogs so the guard can reach them?

The three researcher reports are now in that folder as `…__cld.md`, `…__mus.md` and `…__gem.md`. The research repo commit has been submitted. `sase-16b` and `sase-16c` still cite the cld report's old path; the report records the new one.

Report: `202609/sase_tool_guarded_recipes_and_monitor_wrapping/sase_tool_guarded_recipes_and_monitor_wrapping.md` (in the research repo)
