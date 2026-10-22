# Chat History - ace-run (research.4v.final)

- **TIMESTAMP:** 2026-10-19 08:07:20 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4v.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071316.md`

## Prompt

%clan(research.4v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add pi (see the https://github.com/earendil-works/pi GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to pi that you should review if you
can find it. End your analysis with a recommended solution.]]) %id:research.4v.final %m:@xlarge
%wait:research.4v.cdx %wait:research.4v.cld %wait:research.4v.grk %wait:research.4v.mus %wait:research.4v.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to add pi (see the https://github.com/earendil-works/pi GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to pi that you should review if you
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
   dispatch's `research.4v.cdx`, `research.4v.cld`, `research.4v.grk`, `research.4v.mus`, `research.4v.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4v.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4v.linker`, can find it:

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

Now let me read the five reports via `sase artifact read`.

Verifying the disputed pi claims in source now (sessions, prompt input, extension failure, exit codes), then I'll check the SASE side.

Now verifying the SASE side: hook surface, instruction delivery and suppression precedent, flags, models manifest, and provider-disable keying.

Evidence gathering is essentially done. One last check on install-metadata manager types, then I'll move the reports and write the consolidated report.

Now creating the consolidated directory and moving the five reports.

All five reports are moved into `202610/pi_sase_provider_design/`. Writing the consolidated report now.

Report written. Quick verification of two claims I carried over from researchers (missing-path-as-literal-text and `--name`).

Both confirmed. Registering the consolidated report as a durable artifact.

Registration succeeded. Now submitting the final declaration.

I've written the consolidated report on adding pi as a SASE provider and registered it as `research:202610/pi_sase_provider_design/pi_sase_provider_design__final.md` (`file:explicit:4767edfd1745d6b9662d5c5f`). I matched each of the five reports to its suffix and moved them into `202610/pi_sase_provider_design/` with their suffixes unchanged. The research repo commit was declared and runs when this turn ends.

## Recommended solution
Build pi as a provider inside the SASE repo, with no Rust (sase-core) change, in three phases:
- **Phase 0 (about half a day):** install pi and record real output samples to test against. Nothing has been run live yet. pi isn't installed on athena, and athena's Node (v22.14) is below pi's minimum (22.19). Installing it is a global install, so you'd run it yourself or approve it.
- **Phase 1:** a basic provider that runs `pi --mode json` once per SASE turn.
- **Phase 2:** a small pi extension bundled with SASE that enforces SASE's rules mechanically.

The key design points:

- **Never trust pi's exit code.** In this mode pi exits 0 even when the model errors, aborts or runs out of output. Success has to be read from its event stream (it signals true completion with an `agent_settled` event).
- **Deliver SASE's instructions explicitly.** Left alone, pi loads both the workspace `AGENTS.md` and `~/AGENTS.md`, and on athena both contain the final-declaration rules, so they'd load twice. The fix:
  - pass SASE's instruction file with `--append-system-prompt`;
  - turn off pi's own discovery with `-nc`, only in SASE-managed projects (the same rule Codex follows);
  - re-add the user's own pi instruction files that this drops.
  The earlier pi research said pi's own loading was enough; that's out of date.
- **Send the prompt on stdin.** Passing it as an argument hits Linux's size limit, and pi's `@file` syntax wraps the prompt in `<file>` tags.
- **Never resume with `--session`.** pi runs a reopened session's tools in the directory it was created in, so resuming from a different numbered workspace would edit the old clone. Continuing within one SASE turn reuses the same session id, which is safe; continuing across workspaces uses `--fork`.
- **Keep the user's pi intact:** their default model (via a `pi-default` tier), extensions, MCP, tools and project trust settings.
- **Hold back for now:** no autodetect, no size-alias pools, and no automatic disable when a usage limit is hit.

Two things I found that the five reports missed:
- **Shared subscriptions.** pi can sign in to the same Anthropic, OpenAI Codex, xAI and Meta (Muse) subscriptions SASE's own providers use. SASE tracks quotas and disables per provider name, so it can't see pi and, say, `claude` drawing on one subscription.
- **pi only works within a turn.** Codex is a better model than Claude for suppressing instruction files.

## How the disagreements came out
I settled each one by reading the code it depends on (§10 of the report has the full table):
- **Instruction loading:** mus said pi's own loading was enough; that's wrong.
- **Prompt input:** grk proposed `@file` and gem the argument list; stdin it is.
- **Session continuation:** the earlier research and gem said `--session`; it's never used.
- **Rust:** cdx wanted the event parser in sase-core; v1 stays in Python, since every existing provider's parser is Python and nothing outside the host reads pi's raw output.
- **Sunset flag:** grk proposed one; it isn't needed, because pi has no old behavior to keep reachable.
- **Extension load failures:** cdx thought they were only warnings; they stop the run, so a broken extension fails closed.
- **gem's specifics:** its model list is stale, its usage counting double-counts, and its autodetect priority and quota patterns go against how Grok and Muse are set up.

## Decisions for you
1. **Default tier:** let pi pick the user's default model (recommended), or have SASE choose specific models.
2. **User extensions in SASE runs:** load them (recommended), or load none.
3. **First backend:** if you plan to send pi through a subscription you already use with `claude` or `codex`, the shared-quota problem matters from day one.
4. **OpenCode:** pi now covers the same multi-vendor role, so it may be worth considering retiring OpenCode once pi has real usage.
