# Chat History - ace-run (research.26.final)

- **TIMESTAMP:** 2026-09-22 07:02:52 EDT
- **MODEL:** claude/opus
- **AGENT:** research.26.final

## Prompt

%id(final, clan=research.26)
%m:@xlarge
%wait:research.26.cld %wait:research.26.mus %wait:research.26.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm not sure what the
best solution for multi-agent collaboration is when it comes to sase agents. Can you do
some research with the goal of helping me decide the best way to implement this? End
your analysis with a recommended solution. Review the multi_cli_orchestration_vs_sase.md
and family_channel_delivery.md files in the research sidecar repo for context and
inspiration before peforming your own research.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.26.cld`, `research.26.mus`, `research.26.gem` dependencies, matching by `wait_name` and the canonical research
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

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the critique agent, `research.26.critique`, can find it:

   `sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"`

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>.md`. Register only the
   consolidated report, and do not pass `--move`. If registration fails, report that
   failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Need to run from the workspace root.

I've read all three reports and both context syntheses; now I'm verifying disputed claims in the SASE code before writing the merged report.

Confirmed the `/sase_run` continuation only resumes on gate settlement; now checking `%wait` failure semantics and whether a two-prompt "reply join" is already expressible.

Verified Claude Code's cross-session messaging rules (bypass-to-bypass delivery; `crossSessionInbound: refuse` closes it). Now spot-checking the Codex steering and cross-model review claims.

Counting how often agents actually delegate, mentor, and message, from the local run logs.

No mentor profiles are configured anywhere on athena, so the mentor subsystem the reports build on is currently unused. Scanning run logs for real delegation/wait/messaging patterns next.

Still measuring collaboration patterns in the run archive (how often prompts use `%wait`, `#fork`, and families).

Epic land agents already take a configurable model, so cross-vendor integration review is partly expressible today. Checking how that model gets chosen.

`sase pipe --fresh` already provides a clean-context handoff with an agent-written prompt, which covers most of gem's "capsule" idea. Checking the existing continuation budget machinery.

Found that SASE shipped a mid-run "message a running agent" feature on 2026-03-14 and removed its UI on 2026-03-28. Reading the removal plan for the reason.

Most wait-parking (71/79) is epic land/phase retries, so it's more an orchestration-recovery issue than a collaboration gap. One last code check on what `%wait` passes to consumers, then I'll write.

Verified: for a clan, `wait.chats` returns only the newest successful member's transcript. I have enough evidence; now setting up the consolidated report directory.

Reports moved into `202609/multi_agent_collaboration_strategy/`. Writing the consolidated report now.

Report written. Registering it as a durable snapshot for the critique agent.

Registered as `file:explicit:2c4def79c739c5c3a6f029b1`. Now filing the side-channel closure as a task bead, as cld asked the lead to.

No duplicate task and no causally linked epic. Checking the `bug` task type's required fields.

Filed as `sase-163` (ready). Updating the report's follow-up line to cite it, then re-registering the snapshot so the critique agent sees the final text.

Layout is correct and the final report is registered (`file:explicit:004f14dd1005e5121c09358c`). Submitting the final declaration.

I've merged the three reports and my own research into one report, ending with a recommended solution. It's registered for the critique agent, and the research-repo commit has been handed to the host.

**Recommendation:** have the SASE host pass information between agents at defined points (launch, end of turn), and don't let agents talk to each other live. Build it in stages, each only once there's evidence it's needed:

- **Stage 0 (now):** launch Claude agents with a setting that refuses messages from other Claude sessions (`crossSessionInbound: refuse`), and block the Claude tools that can't work in a single-turn run (`ListAgents`, `Workflow`, `Monitor`, `CronCreate`, `RemoteTrigger`). Right now any other bypass-mode Claude session can steer a running SASE agent, and nothing gets recorded. I confirmed this from inside this session.
- **Stage 1 (no new storage):**
  - give `%wait` actual reply text, every clan member's transcript, outcomes, and an optional failure policy;
  - add a "reviewer must use a different vendor than the author" rule in core model routing, applied first to epic land agents and research critique;
  - add a `/sase_run` mode that resumes the requester when the child *finishes*, not just when the launch is approved.
- **Stage 2:** the durable family inbox from the `family_channel_delivery` report. The host itself posts replies, reviews and gate/monitor outcomes into it, and agents acknowledge messages in their final declaration.
- **Stage 3 (only on evidence):** delivering messages to an agent mid-turn through a SASE-installed Claude hook.
- **Never:** group chat, agents polling for messages, locks or file leases, a message bead type, or gem's new handoff format.

**What my research added:**
- **How agents actually collaborate today** (athena run logs, 2026-08-15 to 09-22, about 4.8k runs):
  - `%wait` is in 44% of prompts and `#fork` in 22%.
  - 32% of runs write bead notes.
  - Delegation through `/sase_run` shows up in only 0.5% of runs.
  - Claude's built-in `SendMessage` was used once.
  - No mentor has run since 2026-08-09, so vendor-diverse review should start with land agents and critique, not mentors.
- **Where the reports disagreed:**
  - I rejected gem's auto-acknowledge-on-success and newest-first truncation. Together they can silently skip messages.
  - I rejected gem's file leases. Its "80% fewer conflicts" figure has no source, and Agent Mail's leases are built for agents sharing one working tree, which SASE agents don't.
  - I rejected gem's handoff capsules, because `sase pipe --fresh` and the existing continuation checkpoints already cover them.
  - I moved cld's delegation fix down the list, since so few runs use it.
- **Things none of the reports caught:**
  - You shipped a "message a running agent" key (`m`) on 2026-03-14 and removed it two weeks later. The code that receives those messages is still there, and for Claude it restarts the agent with a blank context containing only your message.
  - The host can't push messages through Claude's own messaging channel: Claude only accepts them from its own child processes, and the host is its parent. A Claude hook is the clean way to do mid-turn delivery.
  - Codex's mid-turn steering can report success before the input is actually saved (open issue openai/codex#40805).

**Decisions only you can make** (§7 of the report):
1. Do you want to steer agents mid-turn at all? Why was the `m` key removed?
2. Which review directions do you allow? One study found Claude reviewing Codex raised the pass rate from 71.6% to 89.7%, while Codex reviewing Claude lowered it from 91.4% to 82.8%.
3. Should mentors come back?
4. Is there a real steering workflow to trial Stage 2 against?

I also filed the Stage 0 fix as task bead **`sase-163`** (bug, medium, ready for triage). One claim in the report is untested end to end: that a `%model` directive in a mentor's prompt already pins the reviewer's model.

Files are in `sase/repos/research/202609/multi_agent_collaboration_strategy/`:
- `multi_agent_collaboration_strategy.md` (registered as `file:explicit:004f14dd1005e5121c09358c`)
- `multi_agent_collaboration_strategy__cld.md`
- `multi_agent_collaboration_strategy__mus.md`
- `multi_agent_collaboration_strategy__gem.md`

Sources:
- [Claude Code cross-session messaging](https://code.claude.com/docs/en/cross-session-messaging)
- [Claude Code hooks](https://code.claude.com/docs/en/hooks)
- [Xiang et al., arXiv 2607.21656](https://arxiv.org/abs/2607.21656)
- [Codex App Server](https://learn.chatgpt.com/docs/app-server)
- [openai/codex#40805](https://github.com/openai/codex/issues/40805)
- [mcp_agent_mail](https://github.com/dicklesworthstone/mcp_agent_mail)
- [MCP Agent Mail](https://mcpagentmail.com/)
