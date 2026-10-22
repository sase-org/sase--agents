# Chat History - ace-run (research.4w.final)

- **TIMESTAMP:** 2026-10-19 08:20:31 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4w.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071704.md`

## Prompt

%clan(research.4w, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add hermes (see the https://github.com/nousresearch/hermes-agent GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to hermes that you should review if you
can find it. End your analysis with a recommended solution.]]) %id:research.4w.final %m:@xlarge
%wait:research.4w.cdx %wait:research.4w.cld %wait:research.4w.grk %wait:research.4w.mus %wait:research.4w.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to add hermes (see the https://github.com/nousresearch/hermes-agent GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to hermes that you should review if you
can find it. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.4w.cdx`, `research.4w.cld`, `research.4w.grk`, `research.4w.mus`, `research.4w.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4w.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4w.linker`, can find it:

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

Reading the five reports now; the artifact reader needs to run from the primary workspace root.

Confirming which Hermes releases actually contain the gateway-backed chat path; the stable/main split is the key fact for the recommendation.

Main (canary) does route stream-json through the gateway; v0.22.2 stable does not. Now checking signal handling and whether main has a private or isolated runtime mode.

Hermes facts are settled. Now resolving the last disagreements on the SASE side: whether a sunset flag is needed and how skills get deployed.

Hermes facts are done; the last one found is that its terminal tool strips `GH_TOKEN`/`GITHUB_TOKEN` from commands it runs. Now reviewing the earlier Hermes research the user mentioned.

All facts are verified. Next I'm creating the consolidation directory and moving the five reports into it.

Reports are moved. Before writing, I'm spot-checking the SASE file paths the reports list, so the final touch-list only names files that exist.

One more disagreement to settle: whether `--source tool` turns off Hermes's one-shot footprint protections.

Everything I needed is verified. Writing the consolidated report now.

Checking that the internal anchors and relative links in the report all resolve.

All links resolve. Registering the consolidated report as an artifact.

Registered. Now submitting the final declaration.

I wrote the consolidated report at `202610/hermes_agent_sase_provider/hermes_agent_sase_provider__final.md` and registered it as `file:explicit:3326c0dcf26d6963a9d42704` for the linker. The five reports were moved next to it as `hermes_agent_sase_provider__{cdx,cld,grk,mus,gem}.md`. The research repo is declared for commit, which the host does after this turn.

**Recommendation:** add `hermes` as a bundled, opt-in-only provider (short name `hrm`), like Grok and Muse.
- **Command:** it drives Hermes's public `hermes chat --oneshot --query-file - --format stream-json` command.
- **Isolation:** every run happens inside a Hermes profile directory that SASE owns, one per workspace, cloned from a `sase` profile you create once.

**The fact that decides the design:** I checked this in the Hermes source and git history, because the reports disagreed.
- **Current stable (`v0.22.2`):** runs the agent inside the CLI process.
- **`main`:** sends every chat turn to a shared background daemon. Ctrl-C there just detaches and the turn keeps running. The daemon also inherits the environment of whichever agent started it, so other agents' tools would see the wrong SASE identity variables.
- **`v0.22.1`:** was released from `main` by mistake, and `v0.22.2` was re-cut to undo it. The next stable release will very likely bring the daemon back.

Three reports (grk, mus, gem) assume a clean subprocess, which only holds until the next upgrade. With a SASE-owned profile per workspace, the same adapter works on both: on `main` each agent gets its own daemon, which SASE stops when the turn ends.

**Other disagreements I settled:**
- **Packaging:** bundle it rather than ship a separate package. Full support means editing lists that only exist in SASE core (directives, effort levels, doctor, verifier).
- **Instructions:** deliver them through Hermes's system-prompt environment variable, `HERMES_EPHEMERAL_SYSTEM_PROMPT` (about 120 KiB limit), and fall back to prefixing the prompt when they're too big.
- **No sunset flag:** the `sase_flags` memory reserves those for keeping an old behaviour reachable, and there's no old Hermes behaviour.
- **Don't pass `--source tool`:** on `main` it silently turns off Hermes's one-shot safety limits.
- **Skills:** deploy to a SASE-owned directory. The default path would write into your personal Hermes profile.

I also found a gotcha none of the reports raised: Hermes strips `GH_TOKEN` and `GITHUB_TOKEN` from every shell command it runs. If your SASE workflows rely on those for `gh`, the SASE profile needs to pass them through.

**Next step:** do a short trial run before building, against stable and a `main` build. It needs to confirm that SASE's environment reaches Hermes's tools, that stopping the daemon cancels the turn, and that nothing keeps touching the workspace after the turn ends. Nobody, me included, ran a real Hermes conversation, so those lifecycle points are inferred from the code. If the trial fails, keep the rest of the design but swap the transport for cdx's small companion command that runs Hermes's agent loop directly. Asking Hermes upstream for a supervised one-shot mode would make most of the profile machinery unnecessary.

Value is narrower than "any model". Claude through Hermes bills only Max extra-usage credits, and Codex through it probably draws on the same quota SASE's `codex` provider already uses. The real gains are Nous Portal, OpenRouter, and local models.
