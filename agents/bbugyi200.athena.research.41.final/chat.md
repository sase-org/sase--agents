# Chat History - ace-run (research.41.final)

- **TIMESTAMP:** 2026-10-07 15:29:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.41.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_143606.md`

## Prompt

%clan(research.41, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The `%auto` directive is the main way that we are able to tune permissions (the ones
that are used in practice at least since real sase agents don't have hard permissions
yet) for a sase agent, but this directive is not very configurable or intuitive to use.
I would like to fix this and make this directive much more powerful.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.41.final %m:@xlarge
%wait:research.41.cdx %wait:research.41.cld %wait:research.41.grk %wait:research.41.mus %wait:research.41.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The `%auto` directive is the main way that we are able to tune permissions (the ones
that are used in practice at least since real sase agents don't have hard permissions
yet) for a sase agent, but this directive is not very configurable or intuitive to use.
I would like to fix this and make this directive much more powerful.

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
   dispatch's `research.41.cdx`, `research.41.cld`, `research.41.grk`, `research.41.mus`, `research.41.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.41.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.41.linker`, can find it:

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

Reading the five researcher reports now; next I'll verify their key claims against the source and write the consolidated report.

I'm checking the reports' conflicting claims against the source; right now that's whether bare `%auto` commits tale plans.

Still verifying: I'm now checking real gate records to see what auto-resolved tale plans actually selected.

Confirmed that gate follow-ups only carry `#fork`/`%model` prefixes. Next I'm checking whether they inherit `%auto` some other way.

Still verifying the source: now reading the docs' Auto Directive section, then running a parser probe and checking prompt-history usage numbers.

I'm reading the prior nested-landing-loop research that one report cited, since 137 of the 234 auto-approved epics came from epic land workers.

Source checks are done and they settle the main disagreements between the reports. Next I'm spot-checking the external prior-art claims (Claude Code and Codex permission models).

Reports moved into `auto_directive_autonomy_policy/`. Writing the consolidated report now.

Report written. Registering it as a durable artifact for the linker.

Artifact registered. Before finishing, I'll file the clear, decision-independent defects as task beads, per project convention.

No duplicates so far. I'm scanning the rest of the in-progress epics for any causal overlap before filing.

Found another live example of the nesting problem: `sase-19i.7.3.3.3.3.3`, an epic six levels deep. I'll add it to the report, then create the bug bead.

Bug bead `sase-1hg` is filed and ready. Next, a memory task for the stale `%auto` row in the core `macros.md` note.

Both beads filed and linked. I'll add the new nesting evidence and the bead IDs to the report, then re-register the snapshot so the linker sees the final version.

The layout is complete and the final snapshot is registered (`file:explicit:cb38b2cce71d7a97b544ea59`). Submitting the turn's final declaration.

I've written the consolidated report on the `%auto` redesign and registered it for the linker. It merges all five reports with my own checks against the code and real usage data. The research repo commit is declared; the host commits it after this turn.

**Recommendation:** don't make `%auto` a more powerful prompt language. Make it pick a named policy defined in config, the way `%final` picks configured finalizers:
- **Per gate kind:** each kind (plan, epic, question, and later launch) gets an explicit decision: ask a human, approve, or deny.
- **Syntax:** `%auto:<profile>` selects a profile. Inline overrides like `%auto(epic=ask)` are allowed, but only for plan, epic and question.
- **Lifecycle:** the policy is fixed when the agent launches and is inherited the same way by every follow-up agent. It is shown to you, and the agent is told about it too.
- **Rust core:** parsing, merging and evaluation live in `sase-core`.

**Main reason against a richer prompt syntax:** prompts are also written by agents and generated code. If prompt text could grant something like launch approval, an agent could give a child agent more authority than it has itself.

**What I found when checking the code and data:**
- **Usage:** 69.5% of prompts use `%auto` (80% in September). The `:epic` form was never used, and the parenthesized form never has been either.
- **Most epic auto-approvals were nested.** Of 234 epics that `%auto` approved with no human, 170 (73%) came from epic land or phase workers, which have `%auto` hard-coded. An epic six levels deep, `sase-19i.7.3.3.3.3.3`, is still in progress.
- **The parenthesized form fails open.** `%auto(plan=ask, questions=ask)` and `%a(epic=ask)` both parse as bare `%auto`, which means full automation. I reproduced this with the parser.
- **Bare `%auto` archives every tale plan to the plans sidecar.** All 557 auto-approved tales did. This started with the July 18 change that made Enter submit approve + commit. The docs and the core memory row still describe the old behavior.
- **`:tale` and `:epic` also auto-answer questions**, which contradicts the docs.
- **Turning auto off in the TUI doesn't stick** for an already-running agent, because an environment variable set at launch is never cleared. I traced this in the source but didn't reproduce it live.
- **Gate follow-ups drop `%auto`** (follow-ups after a launch, custom or sudo gate).

**Where I settled disagreements between the reports:**
- Bare `%auto` keeps answering questions automatically, but picks the agent's recommended option rather than blindly taking the first. Agents will also be told when no human is reading.
- `:tale` keeps auto-answering questions and the docs get fixed, since it has 702 real uses.
- Auto-approving child agent launches comes later: set only in config, with limits.
- Real execution permissions (sandboxing, tool limits) become a later section of the same profile, not a new `%caps` or `%perm` directive.

**Adjustments to your requirements** are listed in §5 of the report. The main one: version 1 is gate autonomy, not "permissions", because every provider still runs with its approval-bypass flag. The proposed CLI names and config keys in the report are suggestions; I haven't read the project's CLI rules note yet, and an implementer should before building them.

**Decisions for you** (report §7.11):
1. Should epic land and phase workers stop auto-approving nested epics now? I recommend yes. October so far shows only 4 such approvals, so check whether something already reduced this before treating it as urgent.
2. Should bare `%auto` keep auto-launching top-level epics?
3. Should auto-approved tale plans keep being archived?
4. Should leaving out `%auto` still mean a human decides everything? I recommend yes.

**Task beads filed:**
- `sase-1hg` (bug): the fail-open parenthesized parsing.
- `sase-1hh` (memory): the stale `%auto` row in `macros.md`.

I corrected two small external details the reports got wrong. Claude Code's docs give no version for blocking `auto` and `bypassPermissions` in project settings. Codex profiles are files selected with `--profile`, and `untrusted` is no longer a supported approval policy. Neither changes any conclusion.

The report is registered twice under the same label because I edited it after the first registration. The current snapshot is `file:explicit:cb38b2cce71d7a97b544ea59`.

Files are in `202610/auto_directive_autonomy_policy/` in the research repo:
- `auto_directive_autonomy_policy__final.md`
- `auto_directive_autonomy_policy__cdx.md`
- `auto_directive_autonomy_policy__cld.md`
- `auto_directive_autonomy_policy__grk.md`
- `auto_directive_autonomy_policy__mus.md`
- `auto_directive_autonomy_policy__gem.md`
