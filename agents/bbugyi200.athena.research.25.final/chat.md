# Chat History - ace-run (research.25.final)

- **TIMESTAMP:** 2026-09-21 19:13:31 EDT
- **MODEL:** claude/opus
- **AGENT:** research.25.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_182824.md`

## Prompt

%clan(research.25, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? End your analysis with a recommended solution.]]) %id:research.25.final %m:@xlarge
%wait:research.25.cld %wait:research.25.mus %wait:research.25.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.25.cld`, `research.25.mus`, `research.25.gem` dependencies, matching by `wait_name` and the canonical research
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

I've read the three reports. Now I'm checking the provider guard code and recent run telemetry myself to settle where they disagree.

I'm testing whether gem's proposed fix (widening the agy version allowlist) would actually have caught the two agy failures it cites, by decoding their trajectory databases.

The agy run with no final declaration still got a `success` from the commit finalizer. I'm tracing why it isn't rejected.

The first research.24.gem run left a workflow log showing the agy idle-kill but no artifact dir under the sase project. I'm locating it.

Confirmed muse's cancel-and-restart timeline. Now I'm checking whether `sase tool run` / `sase monitor` already have any way to join an in-flight run, since cld's main recommendation depends on that.

Guidance quotes are confirmed. Next I'm breaking monitor handoffs down by day and provider, to see what the user has actually been seeing most recently.

Grok's binary exposes config knobs like `auto_background_on_timeout` and `foreground_block_budget_ms`, so its auto-backgrounding may be configurable. Checking that.

Prior research covers per-hop replay cost, not hop count or restarts, so it doesn't overlap. Now checking for existing beads that already cover any of the fixes.

Evidence gathered: 2 of 7 agy runs on Sep 20–21 ended in a silent false success. I'm creating the consolidation directory and moving the three reports.

Reports moved. Writing the consolidated report now.

Report written. Quick check that the prepared-completion monitor path I recommend (`-f`) really exists as described.

Layout is in place. Now the final declaration.

Your guess is partly right. Only a small share of the long-command "dying" you're seeing comes from agents not understanding headless mode. Most of it is the designed `sase monitor start` handoff, which agents use at the wrong moment and in a way that throws work away.

**What's actually happening (Sep 14–21 runs on athena):**

1. **The headless misunderstanding is real but narrow now.**
   - **Claude:** it hit 10 of 67 Claude runs on Sep 14 and has been at zero since the Sep 15 fix (`bdda3bdf1`).
   - **agy (Antigravity):** it's happening today, in 2 of the 7 agy runs on Sep 20–21. One of them was `research.24.gem`, which stalled that research swarm; that's probably what prompted this request.
   - **How agy fails:** agy pushes any command longer than 10 s into the background and its own tool text tells the model to end its turn. Its print mode then kills the command and exits with status 0. SASE's check for that failure is effectively off: the version allowlist is stuck (bead `sase-15o`), and the text fallback misses these replies. I ran the classifier on both replies and it accepted them.
   - **The host counts it as success:** the commit finalizer only requires a declaration when the repo is dirty, so on a clean tree it recorded `success`. The phase bead `sase-14t.3` is still `IN_PROGRESS` 22 h later.
2. **Most of the "dying" is designed monitor handoffs.** They ended 190 of 1,193 agent runs (16%), including 49% of Grok runs. The mechanism works; the waste is in how agents get there:
   - The guidance says to hand `just check` to a monitor "whenever it is taking a long time". That asks agents to predict a duration they can't know.
   - So they start inline, notice it's slow, cancel the in-flight run and restart it from zero. For example, `sase-14n.14--plan` cancelled a check that had been running for about an hour.
   - After a failure they loop: 23 agent families ran 3 or more monitors, the worst 15 hops over 8 h.
3. **Slow verification sits under both.** `just check` often runs 34–45 min (p90) and `check-full` 45 min typically. Every provider except Claude gives up waiting long before that: agy at 10 s, Grok at about 15 s, Muse at 300 s.

**Where the three reports were wrong:**
- **mus** said Grok and Muse silently losing work was the main cause. I found no such case since Sep 15: every one of those runs ended in a monitor handoff or, for one Codex run, a usage-limit death.
- **gem** said widening the agy allowlist would restore detection. It would only catch these two runs by accident, because the decoder misreads agy 1.2.7's trajectory format.

**Recommended fix.** The tool, not the model, should decide when a wait becomes a handoff; a handoff should never discard work in progress; and a turn that stops halfway should fail loudly. More "you are headless" prompting won't work: agents already know, and agy's own tool text tells the model to end its turn.

1. **Now (small changes):**
   - Require a final declaration whenever a run has an assigned bead, and mark runs that end with neither a declaration nor a handoff as `incomplete`, not `completed`. This works for every provider.
   - Fix agy: rewrite its instructions so the agent keeps checking a backgrounded command instead of ending its turn (gem showed this works), and fix its detection properly.
   - Replace the "hand off when it gets slow" rule with one decided up front: Claude runs checks inline; other providers start them under a monitor straight away, with the declaration prepared so a pass finishes without another agent. Never cancel a running check to restart it.
   - Stop offering Claude the native background tools it still sees (`Monitor`, `Cron*`, `RemoteTrigger`, `PushNotification`, `Workflow`).
2. **Next (the durable fix):** make verification runs survive the agent and let a second identical request join the one already running instead of restarting it. Let a monitor adopt a check that's already running, and add a `sase tool run --handoff-after` threshold per provider. The same wait-detection guard should also go into the Grok, Muse and Codex integrations.
3. **Then:** after 3 failed verification monitors in a row, ask the user instead of trying again, and re-run only the failing tests first. Speed up verification with a shared prebuilt Rust core package so each workspace stops rebuilding it.

Grok's own settings appear to let its commands run in the foreground longer, but I couldn't confirm SASE can set that per run; it's worth a quick test.

The consolidated report is at `202609/agent_long_command_early_exits/agent_long_command_early_exits.md`, alongside the three original reports under their `__cld`, `__mus` and `__gem` names. The final declaration was accepted, so the host will commit the research repo.
