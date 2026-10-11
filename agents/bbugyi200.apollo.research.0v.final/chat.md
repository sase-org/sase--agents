# Chat History - ace-run (research.0v.final)

- **TIMESTAMP:** 2026-10-11 10:38:27 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0v.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261011_095836.md`

## Prompt

%clan(research.0v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research on the pi repo (see https://github.com/earendil-works/pi)? How
does this product compare to sase? In what ways can sase learn from pi? End your
analysis with a ranked list of improvements to sase that you think I should consider
implementing to make sase more appealing to someone who already uses pi.]]) %id:research.0v.final %m:@xlarge
%wait:research.0v.cdx %wait:research.0v.cld %wait:research.0v.grk %wait:research.0v.mus %wait:research.0v.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research on the pi repo (see https://github.com/earendil-works/pi)? How
does this product compare to sase? In what ways can sase learn from pi? End your
analysis with a ranked list of improvements to sase that you think I should consider
implementing to make sase more appealing to someone who already uses pi.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.0v.cdx`, `research.0v.cld`, `research.0v.grk`, `research.0v.mus`, `research.0v.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.0v.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0v.linker`, can find it:

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

Reading the five researcher reports now (cdx done); next I'll read cld, grk, mus, gem, then do my own verification against the pi checkout.

Verified pi's hook API (`agent_before_settle` continue, `tool_call` block, `terminate`). Next I'm checking the CLI flags, RPC lifecycle, and session format.

Pi-side claims check out (Codemode is opt-in, Durable is explicitly experimental and single-process). Now verifying the SASE-side claims: providers, fork semantics, cost, steering, and trust.

Found that SASE already has a hidden interrupt-and-redirect path (`interrupt_request.json`), which contradicts the reports' claim that it has no steering. Checking how the TUI exposes it.

Verified that SASE has no dollar-cost display (only usage windows). Checking the remaining claims: instruction-bundle delivery, tmux-agent, trust, and existing pi beads.

Pi loads `AGENTS.md`/`CLAUDE.md` natively from parent directories, so a pi provider would get SASE's instructions without extra wiring. Last check: pi's release dates, then I'll write the report.

All verification is done. Writing the consolidated report.

Registration succeeded. Now submitting the final declaration.

I wrote the consolidated report and registered it for the linker agent. The host will commit the research repo after this turn.

**Conclusion:** pi and SASE work at different layers. Pi is a minimal, hackable single-agent harness: it runs the model, tools, session file and terminal UI itself. SASE coordinates harnesses like it. So pi is mainly a backend SASE could run, not a rival. Today SASE can't run pi at all: none of its eight providers is pi, and no task beads mention it. A pi user won't give up their models, logins and extensions to try SASE.

The gap in reach is large: pi has 114,256 GitHub stars and 4.19M npm downloads in the last week; SASE has 5 stars. And SASE's real competition for a pi user isn't pi itself. It's the multi-agent orchestrator packages already in pi's package gallery (worktrees, swarms, schedules, handoffs), plus Pi Durable, Earendil's experimental crash-resumable runtime.

**What SASE can learn from pi:**
- Enforce rules with pi's hooks instead of instruction text.
- Teach the smallest customization mechanism first.
- Show context, cost and the actual model while an agent runs.
- Offer strict, documented machine interfaces.
- Measure whether instructions earn their tokens with with/without evals.

**Ranked improvements:**
1. A first-class pi provider that runs the user's own pi config. Start with pi's one-shot JSON mode, which fits SASE's single-turn model; add its live-control (RPC) mode later. It must treat pi's `agent_settled` event as the end of a turn: JSON mode exits 0 even when the model fails.
2. A `sase-pi` pi extension that enforces SASE's rules mechanically:
   - the final declaration becomes a typed tool;
   - a guard before the agent stops reminds it to declare;
   - `git commit` and `gh pr create` are blocked;
   - helper processes can't declare.
3. An on-ramp for pi users: target the repo they're in, a "lite" profile, and a one-page guide.
4. Steer, follow-up and abort for running agents. This needs a short decision record.
5. Live cost, context and model display, plus a budget for SASE's own instructions. Pi will show SASE's roughly 5–6k tokens of always-loaded instructions in its own context meter.
6. A pi→SASE bridge published in pi's gallery (`/sase run`, `/sase promote`).
7. Native forks using pi's session tree, and a tree view of SASE's agent lineage.
8. Cheap customization: `/` templates, Agent Skills interop, and installable data-only packages.
9. A stable SASE event stream.
10. With/without evals for instructions and memory.
11. Crash-safe provider sessions.
12. Reach and polish: terminal status signal, one-line installer, HTML export, themes.

**Where I overrode the researchers:**
- **SASE did once have steering.** Two reports said it has none. Commit `739196a9c9` (2026-03-14) added a "message a running agent" key on the Agents tab, and `1a46198f14` removed it two weeks later; its plan gives no reason. The provider-side code is still there but unused. It kills the agent and restarts it with the message, whereas pi queues the message for the next safe point. Worth finding out why it was removed before reviving it.
- **gem's top pick, a SASE-native version of pi's script-the-tools feature (Codemode), targets the wrong layer.** SASE doesn't execute the model's tool calls; the provider CLIs do. gem's "50–70% token reduction" has no source, and some file paths it cites don't exist. SASE users get Codemode through the pi provider, as long as SASE doesn't override pi's tool settings.
- **I rejected grk's long-lived pi process kept alive across SASE turns.** It conflicts with SASE's single-turn design. Each turn should reopen pi's session file by absolute path, because the next turn can land in a different numbered workspace.

**Files:**
- **Folder:** `202610/sase_for_pi_users/`, containing the five moved reports and `sase_for_pi_users__final.md`. The old empty `pi_vs_sase/` directory is gone.
- **Registered ref:** `file:explicit:9767805b38ab6627ba6982de`

Sources:
- [@onlinechefgroep/pi-agent-orchestrator](https://pi.dev/packages/@onlinechefgroep/pi-agent-orchestrator?page=29)
- [@xzzpig/pi-subagents](https://pi.dev/packages/@xzzpig/pi-subagents?name=sub)
- [@0xkobold/pi-orchestration](https://pi.dev/packages/@0xkobold/pi-orchestration?page=7)
- [@pi-orca/agents](https://pi.dev/packages/@pi-orca/agents?name=tmux)
- [pi-subagentura](https://pi.dev/packages/pi-subagentura?name=tmux)
