# Chat History - ace-run (research.3h.final)

- **TIMESTAMP:** 2026-10-03 14:22:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3h.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_133508.md`

## Prompt

%clan(research.3h, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] My
apollo machine keeps killing all of its sase agents due to OOM errors I believe. Can you
dig into this / do some research with the goal of helping me figure out what is causing
this and fix it? End your analysis with a recommended solution.]]) %id:research.3h.final %m:@xlarge
%wait:research.3h.cdx %wait:research.3h.cld %wait:research.3h.grk %wait:research.3h.mus %wait:research.3h.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

My
apollo machine keeps killing all of its sase agents due to OOM errors I believe. Can you
dig into this / do some research with the goal of helping me figure out what is causing
this and fix it? End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3h.cdx`, `research.3h.cld`, `research.3h.grk`, `research.3h.mus`, `research.3h.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3h.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3h.linker`, can find it:

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
└── <name>__final.md
```

## Response

I've read two of the five reports (cdx, cld). Reading the other three next, then I'll check the open disagreements myself on apollo and in the source.

The detach-scope fix has now landed on master (`9fe4405683`, committed 18:05 UTC from an apollo agent), but it still uses the 243 version gate that cld flagged. Reading the full module now.

I'm checking the tool-call logs of the two agents killed at 17:32 to see which command was running when the OOM hit.

I'm checking whether apollo's installed SASE already includes today's fix, and whether the service unit has been re-rendered.

The `bob_query` skill has no FLATTEN or memory guidance. Last check: the TUI's own memory heartbeat over its 43-hour lifetime, to settle grk's heap-growth theory.

The cross-check is complete, and the Sep 3 OOMs belong to an earlier boot with no OOMs between then and Oct 1. Before writing, I'll check which `sase service` command re-renders the unit file.

`sase service init --check` is read-only, so I'll run it on apollo to confirm the unit drift.

Drift confirmed: `sase service init -y`, run from Bryan's normal apollo login shell, would rewrite the unit. I have everything I need, so I'll set up the report directory now.

The five reports are moved into `202610/apollo_agent_oom_wipeouts_root_cause/`. Writing the consolidated final report now.

Fixing two details before registering: the page-cache purge range (Oct 1 was 8 GB, not 14–15), and the wording about the `app.slice` lines. Checking athena's systemd version first.

Report corrected. Registering it as a durable artifact for the linker agent.

The report is registered (`file:explicit:059ae8c95f43160e5be5e707`). Submitting the final declaration now.

Apollo is killing your agents with real kernel OOM kills, and every wipe-out needs two problems at once.

**What uses up the memory: one runaway `bob query`.** Agents in bob-cli ran whole-vault queries like `FLATTEN file.tasks … GROUP BY` with no `FROM`. bob's Dataview engine copies the whole page once for every task it flattens, so memory grows with the square of a page's task count. Your vault has pages with 2,413 and 2,012 tasks. One query grows by about 25 GiB in under a minute on a 31 GiB machine with no swap.
- All 5 unscoped FLATTEN queries ever run on apollo died within about 0.1 s of one of the 3 OOMs, and every OOM had one running. The scoped queries all succeeded.
- `sar` shows only 4–7 GiB in use a few minutes before each OOM, so this is a sudden spike, not a slow leak. The TUI itself never went above 2.6 GiB.

**Why it kills *every* agent: they all share the TUI's tmux pane.** Agents launched from the TUI stayed in the pane's systemd scope, and systemd's default rule on apollo is to stop the whole scope when one process in it is OOM-killed. So one killed `bob` takes down the TUI and every agent with it.

**Today's fix isn't working yet.** Commit `9fe4405683` gives each agent its own scope, and apollo has it installed. But:
- the TUI you're running started before it, and no agent has been given its own scope yet;
- `sase.service` still has the old setting because its unit file was never rewritten;
- the fix checks for systemd 243, but scopes only support this setting from 253. Apollo (255) and athena (257) are fine; older hosts would fail every agent launch.

**Recommended solution:**
1. **Today, no code.** Change the user systemd default from `stop` to `continue`, run `sase service init -y`, and restart the TUI.
2. **Today.** Tell agents (in the `bob_query` skill) never to FLATTEN without `FROM`, and to use `TASK` queries instead. A `TASK` query answers the same question in 1.6 GiB.
3. **bob-cli.** Make FLATTEN and GROUP BY stop copying whole pages, and add a row or memory limit so a bad query fails fast.
4. **sase.** Fix the version check to 253 and put agents under a shared memory cap so a runaway can't exhaust the whole machine.
5. **Optional.** Add a swapfile. Neither swap, fewer agents, nor more RAM would have prevented these wipe-outs.

One thing is still unexplained: the pane that died at 17:32 logged only 4.3G of peak memory. A single sudo read of the kernel log would settle it. I changed nothing on apollo.

The consolidated report is registered as `file:explicit:059ae8c95f43160e5be5e707`, and the commit is declared. Everything is in `202610/apollo_agent_oom_wipeouts_root_cause/` in the research repo:
- apollo_agent_oom_wipeouts_root_cause__final.md
- apollo_agent_oom_wipeouts_root_cause__cdx.md
- apollo_agent_oom_wipeouts_root_cause__cld.md
- apollo_agent_oom_wipeouts_root_cause__grk.md
- apollo_agent_oom_wipeouts_root_cause__mus.md
- apollo_agent_oom_wipeouts_root_cause__gem.md
