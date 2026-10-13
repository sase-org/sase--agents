# Chat History - ace-run (research.13.final)

- **TIMESTAMP:** 2026-10-13 17:13:33 EDT
- **MODEL:** claude/opus
- **AGENT:** research.13.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_162421.md`

## Prompt

%clan(research.13, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
am considering launching agents to implement the E3 epic described in the
memory_built_instruction_migration_epics.md file in the research sidecar repo. Can you
do some research with the goal of helping me understand if we are ready for this work?
Also, explain how I would be able to figure out what a given sase agents instruction
bundle's contents looked like (for a completed agent on the "Agents" tab, for example).]]) %id:research.13.final %m:@xlarge
%wait:research.13.cdx %wait:research.13.cld %wait:research.13.grk %wait:research.13.mus %wait:research.13.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
am considering launching agents to implement the E3 epic described in the
memory_built_instruction_migration_epics.md file in the research sidecar repo. Can you
do some research with the goal of helping me understand if we are ready for this work?
Also, explain how I would be able to figure out what a given sase agents instruction
bundle's contents looked like (for a completed agent on the "Agents" tab, for example).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.13.cdx`, `research.13.cld`, `research.13.grk`, `research.13.mus`, `research.13.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.13.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.13.linker`, can find it:

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

Reading the five researcher reports now (1 of 5 done), then I'll verify the disputed points myself.

Read all five reports. Now reading the source epics report's E3 section and checking the points where the reports disagree.

I'm checking whether the five Grok runs that one report flagged as missing final declarations were actually monitor handoffs (which would make them legitimate).

Pre-E1 runs lack `done.json` (dismissed), so I'm adjusting the scan to fall back to `agent_meta.json` to get a comparable baseline.

Handoff-aware classification changes the E1 readout a lot (Codex's "38% outlier" is a monitor-handoff artifact). Now verifying the Agents-tab keybindings the reports disagree on.

Confirmed no E3 plan or bead exists. Checking one contested provider claim: whether Claude Code 2.1.296 loads `AGENTS.md` natively.

Significant find: Claude Code 2.1.296 has an `instructionFiles` setting whose default falls back to `AGENTS.md` when a project has no `CLAUDE.md`. Checking the exact key.

Claude Code 2.1.296 does load `AGENTS.md` (default `instructionFiles: "claude-md-or-agents-md"`), which affects E3.3 and E4. Quickly verifying the shadow-render error count and manifest volume.

All 804 manifests since Oct 6 are `shadow` status, all on apollo, zero render errors; no remote machines configured. Checking the sase-core wire schema for what E3 must extend.

Rollback via `sase flag disable` works today. Let me check the residual "missing declaration" runs in the post-E1 window before writing.

I have what I need. Creating the consolidated directory and moving the five reports into it.

Directory created and reports moved. Verifying a couple of command details I'll cite in the how-to section.

Writing the consolidated report now.

Report written. Registering it as a durable artifact for the linker.

Registered (`file:explicit:cc54c7c25f6ec42d1abc3fda`). Now submitting the final declaration.

You're ready to plan E3 but not to launch implementation agents yet: no E3 plan or epic bead exists. The entry gates are met. Your next step is a planning agent, and it needs a few changes to the original E3 design (listed below). None of them needs more waiting time.

**Readiness**
- **E1 and E2 landed on Oct 6.** Since then, 804 shadow bundles were built with zero render errors, and the parity check is clean.
- **E1 readout:** the five researchers disagreed on whether it was acceptable. I settled it as acceptable. Counting "has a final-submission file", as two reports did, makes compliance look much worse than it is.
  - The five Grok runs one report flagged were legitimate: each published a prepared declaration (`sase final prepare`), handed off to a verify monitor, and its chain ended with an accepted submission.
  - Counting plan and monitor handoffs as valid, Grok runs that ended with neither a declaration nor a handoff fell from **14% to 5%**.
  - Codex's reported "38% outlier" is just its frequent monitor handoffs. Its real misses are 2% at most.
  - The E3 watch metric needs this handoff-aware definition.

**Changes the E3 plan needs**
1. **Fix the scoreboard first.** `sase instructions verify` silently skips dismissed agents (it returns zero runs with exit 0). It zeroes the whole per-section comparison for any transcript over 512 KB. It counts presence in the old native files, so a working explicit delivery would read as zero. It also can't prove "exactly once". E3.3–E3.5 can't prove their exit criteria until this is fixed, so it should come before them.
2. **Replace the "re-render reproduces the hash" exit criterion.** `render -a` compiles from today's sources, not the agent's original ones.
3. **Provider changes since the original design:**
   - **Claude Code 2.1.296 now reads `AGENTS.md`.** A new `instructionFiles` setting defaults to loading `AGENTS.md` when a project has no `CLAUDE.md`. Both E3.3 and E4 (which deletes the `CLAUDE.md` copies) have to handle this.
   - **Codex multi-agent v2 is on.** Its full-history forks would inherit the root bundle, so the plan should declare Codex helpers as inheriting the root.
4. **Fold in open bug `sase-11s`.** It changes the same Codex home-directory code as E3.4, and its suggested fix would hide Codex session logs from the scoreboard.
5. **Rollback and decisions.** Create new per-provider kill-switch flags rather than reviving the retired E1/E2 ones. A failed render must restore the old delivery and the native files together. Any new manifest field means a sase-core change plus moving its pinned revision. Put home-layer privacy, Claude auto-memory and Grok memory, and flag lifetime in the plan's `decisions:` block.

**Seeing a completed agent's bundle**
1. On the Agents tab, press `%` then `d` to copy the agent's artifacts directory, or run `sase agent show NAME`. `sase agent show` also works for dismissed agents.
2. Open `<artifacts>/instructions/00-<provider>.md` for the exact bytes, and the matching `.json` for the manifest.
3. Check every numbered pair, not just `00`; later numbers are recovery or repair invocations.

Two caveats:
- **That bundle is shadow-only until E3 ships.** No agent has ever received it.
- **The TUI can't open the bundle today.** What the agent actually loaded shows as the "AGENTS.md as launched" row in the MEMORY lane (press `v` on it). `sase instructions verify -a NAME` shows what the provider's own logs say it loaded.

I made no paid provider calls or remote-host probes. The Muse no-trust-flag and Claude auto-memory checks are still open for E3's spikes phase.

The consolidated report and the five moved researcher reports are committed to the research repo under `202610/e3_delivery_cutover_readiness_and_bundle_inspection/`. The final report is registered as `research:202610/e3_delivery_cutover_readiness_and_bundle_inspection/e3_delivery_cutover_readiness_and_bundle_inspection__final.md`.
