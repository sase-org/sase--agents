# Chat History - ace-run (research.3n.final)

- **TIMESTAMP:** 2026-10-05 08:00:12 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3n.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_065248.md`

## Prompt

%clan(research.3n, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.3n.final %m:@xlarge
%wait:research.3n.cdx %wait:research.3n.cld %wait:research.3n.grk %wait:research.3n.mus %wait:research.3n.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

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
   dispatch's `research.3n.cdx`, `research.3n.cld`, `research.3n.grk`, `research.3n.mus`, `research.3n.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3n.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3n.linker`, can find it:

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

Reading the five researcher reports now; next I'll verify their disagreements against the code.

Confirmed Grok loads zero instruction files in SASE workspaces since mid-September (untrusted folder). Now checking whether trust is a simple fix and verifying the Codex and Antigravity claims.

Verified Codex does load `~/AGENTS.md` via SASE's shadow home (and duplicates the shared contract). Now checking Antigravity's transcripts for the claimed double-load.

Antigravity's bundled docs confirm it loads both `GEMINI.md` and `AGENTS.md` (deduped by path only). Now checking SASE source for the adapter hooks, snapshot logic, and `%tag` history.

Muse also gates rules on workspace trust. Quick check of a Muse session for home vs. project instructions, then I'll check the finalizer baseline timing claim.

Grok and Muse both gate project rules on trust, which changes the delivery design. A few more checks: template-override usage, Rust-side memory rendering, and Muse/Codex flags.

I've confirmed the core facts. Two open questions need vendor docs: Claude Code's `claudeMdExcludes` and subagent inheritance, and Codex's project-doc suppression knob. Fetching both in parallel.

I have what I need. Now moving the five reports into a new stem directory in my research checkout.

Reports moved. Writing the consolidated report now.

Report written. Registering it as a durable artifact for the linker.

Registered. Now the final declaration.

I've written and registered the consolidated report; the host will commit it to the research repo after this turn. In short: build it, but not as you described it. Your two named bugs are out of date. The real ones are worse.

**What's actually happening now (I checked each of these myself):**
- **Grok loads no instruction files at all** in SASE workspaces, and hasn't since about 2026-09-10. Grok 1.0.46 only loads project rules in "trusted" folders, and SASE never marks workspaces as trusted. `grok inspect` in a workspace shows `Project trusted: no` and `Project Instructions (0)`, and all 465 Grok workspace sessions since then loaded nothing. The double-load you described is what comes back if you grant trust, so don't fix it that way.
- **Codex does read `~/AGENTS.md`** in SASE runs, through the temporary `CODEX_HOME` SASE builds for each run. The real Codex bug is that the shared SASE instructions arrive twice. Claude has the same duplication, and its two copies list different linked repos.
- **Muse and Grok never see the home instructions** (tailnet, Obsidian, chezmoi).

**Where I'd change the plan:**
1. **Don't write the file into the workspace.** Each provider adapter should pass one generated bundle through that provider's own channel (Claude's `--append-system-prompt-file`, Grok's `--rules`, the Codex temporary home, a prompt prefix for Muse). Writing files fails because:
   - the files are committed, so the finalizer would commit the rewrite;
   - Grok skips gitignored files;
   - Codex has no way to turn off a project `AGENTS.md` that's present;
   - reused workspaces keep the previous agent's file;
   - the provider isn't final until the moment of launch.
2. **Make `SASE.md` a short layout spec, not the place the text lives.** It would say which layers go in, in what order, under what conditions, and within what size budget. The text stays in memory notes, which gain a `when:` key. The generated `sase/memory/sase.md` gets folded into SASE's built-in base, which also removes the duplication.
3. **No `%tag`.** The name has been used before (it became `%group`, then tribes), `%t` already means `%tribe`, and old `tag` metadata is still read as a tribe. Nearly every conditional section I found can key off facts SASE already knows about the launch: provider, role, phase worker, tribe, macro, commit method, host. If free-form labels turn out to be needed, macros can declare them later.
4. **Test that each provider receives the instructions exactly once**, by reading its own session records in `sase doctor` and on a schedule. A check like this would have caught the Grok regression on the first day.
5. **Stop committing the 20 generated instruction files.** Codex can't ignore a full committed `AGENTS.md`, so keeping it would preserve the duplicate and block any per-agent trimming for Codex. People running raw CLIs get gitignored local copies, and the public repo can keep a short hand-written stub.

**Use cases you missed** include:
- lean versions for monitor and gate turns;
- a separate version for Claude subagents, which today get told to run `/sase_final`;
- moving the four provider-specific directives hard-coded in the adapters into the reviewable spec;
- a record of exactly what each agent saw;
- home instructions that vary by host (replacing the chezmoi hostname template);
- instruction sections contributed by plugins;
- flag-gated experiments with different instruction versions;
- an end to the churn: 111 commits touched `AGENTS.md` in the last 60 days.

**Recommended order:**
- **Phase 0 (days):** pass Grok its instructions via `--rules` and leave workspaces untrusted, plus a first version of the delivery check.
- **Phase 1:** the bundle renderer and per-provider delivery, each behind its own flag.
- **Phase 2:** stop committing the generated files.
- **Phase 3:** conditional sections based on launch facts, with a size budget for each variant.
- **Phase 4:** labels, only if a real section needs one.

The validation schema goes in `sase-core`; assembling the text stays in Python.

Some numbers come from the researchers and I didn't re-measure them: run shares, the drop in Grok's final-declaration rate, and the size of the duplication. Antigravity double-loading `AGENTS.md` and `GEMINI.md` is documented by the vendor and was reported by the gem researcher, but its transcripts don't record loaded rules, so I couldn't confirm it.

The five researcher reports are now in the same folder under the new name, and the report is registered as `file:explicit:bca9e755c7e49a953c8330c9`. I didn't create `sase_md_instruction_delivery.md` (the linker publishes it) or the `_narration.md` file, which my steps didn't cover.

Report: `202610/sase_md_instruction_delivery/sase_md_instruction_delivery__final.md`
