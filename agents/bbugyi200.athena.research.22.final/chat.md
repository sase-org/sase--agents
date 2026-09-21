# Chat History - ace-run (research.22.final)

- **TIMESTAMP:** 2026-09-21 15:26:54 EDT
- **MODEL:** claude/opus
- **AGENT:** research.22.final

## Prompt

%id(final, clan=research.22)
%m:@xlarge
%wait:research.22.cld %wait:research.22.mus %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 2 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The multi_cli_orchestration_vs_sase.md file in the
research sidecar repo recommended that sase "Add a generic ACP provider plugin.". Can
you do some research with the goal of helping me decide the best way to implement this?
Also, critique this plan in general. Is this a good idea? Would you take a different
approach? Make any adjustments to the requirements that you think are justified but
clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, belonging to this
   dispatch's `research.22.cld`, `research.22.mus` dependencies, matching by `wait_name` and the canonical research
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
└── <name>.md
```

## Response

Both reports exist in my checkout. Reading them via `sase artifact read`.

Both reports read. Now let me check the source report's recommendation context and verify disagreements. First, the source section and the SASE code claims.

Now verifying SASE-side claims where the reports disagree or rely on specifics.

I've confirmed both reports and checked the SASE code they cite. Next I'm checking the ACP spec checkouts, since the reports disagree on a few points.

Checking whether SASE's mid-run interrupt feature still has a producer, since both reports lean on it as ACP's main win.

Important finding: the only writer of `interrupt_request.json` was removed in March. Checking linked plugins for any remaining producer.

Version discrepancy resolved (two tag series: crate v1.9.1, schema v1.23.0, same day). Now checking the registry protocol matrix and launch commands the reports disagree on.

OpenCode passes: its session survived a process kill and was resumed with full memory, and it reported per-turn token usage. Running the same spike on Grok and Qwen.

Grok returns `-32603 Internal error` on prompt. cld noted Grok needs `authenticate` with `cached_token` first; retrying with that step.

Grok's quota is exhausted right now (402 on stderr), which itself is useful: over ACP the usage limit arrives as a generic `-32603 Internal error`, and the real cause is only on stderr. Now Qwen.

Qwen also fails with `-32603` (actual reason `403 Access to model denied`, in `error.data.details`). Quick check whether that's ACP-specific or the account.

No existing ACP-provider or native-resume beads. Two more checks: the Rust-boundary precedent cld cited, and the feature-flag conventions (since the recommendation involves a scaffolding flag).

Research is done. Setting up the output directory now; first checking the research repo's conventions and the relative links inside the two reports (they'll move one level down).

Reports moved (and cld's relative link to the source report fixed for its new depth). One quick verification of cld's hard-coded provider tables claim before writing.

All claims checked. Writing the consolidated report now.

Quick verification of two details I cited: agy's pool membership, and which spike run produced the `usage_update` numbers.

Confirmed agy is `@xsmall`-only. Fixing the `usage_update` numbers, which came from the first spike prompt, not the conformance run.

The layout is in place. Submitting the final declaration.

The consolidated report is written. It's in `sase/repos/research/202609/acp_provider_design/`, next to the two researcher reports (renamed to `acp_provider_design__cld.md` and `acp_provider_design__mus.md`). The commit has been submitted to the host.

## Short answer

Yes, add ACP support, but build it as a transport, not as "one generic ACP provider". It's worth doing, but not urgent. The source report overstated what ACP delivers.

## What the two researchers agreed on (and I agree)

- **The client:** write a small synchronous Python ACP client in SASE core. Don't depend on the official SDK (it needs asyncio and pydantic), don't use acpx, and don't write it in Rust.
- **One profile per agent:** each agent needs its own settings for how to launch it, turn off approvals, choose model and effort, get usage and log in.
- **Keep native drivers** for Claude, Codex, Muse and agy. agy has no ACP mode, and Google's terms of service threaten suspension for third-party access.
- **Usage:** ACP's standard `usage_update` reports how full the context window is, not token counts.

## Where they disagreed, and how I resolved it

- **Naming:** each agent should be its own provider named after it (`opencode`, `copilot`), not `acp-opencode`. Usage-limit disabling is keyed by provider name but the quota belongs to the account. With two names, the router keeps sending work to an account that is already out of quota.
- **First agents to try:** OpenCode first, then Grok. mus proposed Goose, but it isn't installed here and adds little.

## What my own research added

- **The interrupt feature has no trigger.** The only thing that sent a mid-run interrupt was the Agents-tab `m` key, removed on 2026-03-28 (commit `1a46198f1`). So every provider's interrupt handling is dead code, and "lossless interrupts", a headline benefit in both reports, delivers nothing today. Claude's dead branch is also buggy: it drops the original task.
- **The real benefit is session resume for follow-up agents.** Follow-up agents (after a monitor, question or gate, or via pipe) each start a new process and replay history as text. ACP `session/resume` can pick up the earlier session instead.
- **I tested this live against OpenCode.** It resumed a session after its process was killed and still remembered a codeword. It also:
  - loaded AGENTS.md;
  - saw every `sase_*` skill, including `sase_final`;
  - ran a shell command without asking for permission;
  - streamed tool calls, reasoning and token usage.
- **Grok and Qwen couldn't be fully tested.** Grok's quota is exhausted and Qwen gets 403. Both errors came back as a generic `-32603` code, with the real cause only in stderr or the error's `data` field. Usage-limit detection has to read those.
- **None of the ACP-only agents is installed on athena** (Copilot, Cursor, Goose, Kimi, Droid).

## Changes to the requirements

The report's §7 lists all 12. The main ones:

- **Dropped:** lossless interrupts.
- **Changed:** replace the native OpenCode driver inside the epic rather than running an open-ended A/B test. A temporary `beta` flag covers the switch and is removed when the epic lands.
- **Changed:** resume should sit behind one session-reuse design shared with native Claude `--resume --fork-session` and Codex `exec resume`.
- **Added:** every agent profile must pass a quick conformance check before use (about 20 seconds).
- **Added:** error mapping that reads stderr and the error's `data` field.
- **Changed:** add new agents only when you actually hold an account for them.

## Recommendation

1. Re-run the Grok test once its quota resets.
2. Build the ACP transport with OpenCode, behind a `beta` flag.
3. When it matches or beats the native driver, delete the native OpenCode driver and the flag.
4. Build the shared session-reuse design, with Claude, Codex and ACP support. I'd do this first if you care more about your daily providers than about adding agents.
5. Move Grok to ACP only if it matches native.
6. Add new agents only on demand.

## Decisions for you

- Bring mid-run messaging back, or delete the dead interrupt code?
- Do you plan to get any new agent accounts, such as Copilot?
- Which first: session reuse or ACP?
- Should Qwen stay a provider while its account is denied model access?

I didn't file a bead for the dead interrupt code, because whether to delete it or revive the feature is your call.
