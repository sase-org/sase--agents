# Chat History - ace-run (research.5g.final)

- **TIMESTAMP:** 2026-10-29 01:39:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5g.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261029_002947.md`

## Prompt

%clan(research.5g, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The sase-core repo keeps failing CI. I'm wondering if there is a way we can fix this
with a post-commit hook or something like that to prevent these same types of failures
from continuing to recur. Can you do some research to help me understand the nature of
these failures? End your analysis with a recommended solution.]]) %id:research.5g.final %m:@xlarge
%wait:research.5g.cdx %wait:research.5g.cld %wait:research.5g.grk %wait:research.5g.mus %wait:research.5g.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The sase-core repo keeps failing CI. I'm wondering if there is a way we can fix this
with a post-commit hook or something like that to prevent these same types of failures
from continuing to recur. Can you do some research to help me understand the nature of
these failures? End your analysis with a recommended solution.

When you author or carry over Mermaid diagrams, load `/mermaid_diagrams` before
drafting, even when no image or diagrams companion runs. The skill has the shared
figure-selection, styling, and PDF-render review rules. If the provider skill is not
deployed, verify the edited plugin's guide with `sase macro show skill/mermaid_diagrams --format raw` (or
`sase macro show /mermaid_diagrams --format raw`) and use the form this host supports.
This guidance does not enable a companion diagrams agent.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.5g.cdx`, `research.5g.cld`, `research.5g.grk`, `research.5g.mus`, `research.5g.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.5g.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.5g.linker`, can find it:

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

Reading the five researcher reports first (cdx done); then I'll verify the disputed points against sase-core's CI history myself.

Receipt docs confirm receipts are machine-local with a 2-hour TTL, and sase-core currently mints none. Last check: whether anything watches sase-core's master CI the way `ci_watch` watches sase's.

Filed flake bead `sase-1pl` (ready, linked to `sase-1io.7.1` and `sase-1pi.1`). Now moving the five reports into the consolidation folder and writing the final report.

Now writing the consolidated report.

Report written. Registering it as a durable artifact for the linker.

Registration succeeded. Final step: submitting the turn's declaration.

sase-core's master was red for about 29% of October, and 40% of October pushes to master failed CI. A post-commit hook can't fix that: git ignores its result, so it runs too late to stop anything. The hook that *can* stop a bad change already runs on every sase-core landing, and right now it does nothing.

**What's failing.** Five kinds of failure, merged from all five reports plus my own checks:
- **Formatting, Clippy, dependency-feature drift and compile errors**, plus **tests that fail on every run**. Together these are about half of all red time. A full local `sase tool run check` catches all of them. None came from a commit whose exact contents had passed that check; each came from a commit with no check, a failed check, or edits made after the check.
- **macOS-only bugs:** case-insensitive file names, file names macOS refuses, a C type that differs between Mac and Linux, and timing. These caused the longest red stretch, 27 hours. A Linux machine can't catch them, except the compile errors, which a Linux cross-compile check can.
- **Intermittent tests**, which fail once and pass on a rerun.
- **CI configuration mistakes**, which are few.

**Why the same kinds keep coming back:**
- **The pre-commit step that runs on every landing is a no-op for sase-core.** All 40 records since 10-20 show it running `sase_git_fix`, exiting 0 in about 0.04 s, and doing nothing.
- **Nearly every sase-core change is made by agents working from another project.** 35 of those 40 came from the sase project's linked checkout and 5 from bob-cli. Those agents follow sase's instructions, which tell them to skip test guidance for files in linked repos, so they run sase's check instead of sase-core's.
- **Failures in sase-core's local check are all labelled "new, no owner".** That includes known intermittent tests that already have tracking beads, because sase-core's check doesn't declare its stages. Agents decide for themselves whether a failure is theirs, and 17% of commits landed on a check that had failed.
- **Master is unprotected and nobody is assigned when it goes red.** During the recent macOS streak, 11 unrelated commits landed on top of a red master.

**What's red right now.** The macOS timing failure was a real product bug and is fixed (`0fd85e4a`). The current red is a cache test (`concurrent_readers_see_consistent_snapshots`) that finds the cache stale. The likely cause is that one failed rebuild switches readers off the cache for 10 minutes, but I haven't reproduced that. It had been noted on three other beads but never filed, so I filed it as **`sase-1pl`**.

**Where the reports disagreed:**
- gem's "100% test flakes, 0% formatting or lint" holds only for the last three days.
- grk said the pre-commit step runs `just fix` and fails; the records show it runs the no-op `sase_git_fix` instead.
- cld's version of the landing gate can't yet skip known intermittent tests, because sase-core's local check can't recognize them.

**Recommended solution:**
1. **Fix the current red:** keep `0fd85e4a`, and fix the cache bug through `sase-1pl` in the product code rather than by loosening the test.
2. **Add a landing gate.** Set sase-core's own `commit_hooks.before` to a script that:
   - runs `just fmt`;
   - lets the commit through if this exact set of files already passed `check` on this machine;
   - otherwise runs `sase tool run check` and refuses the commit if it fails.

   This covers the failures behind about half of red time and costs roughly 15 minutes of host time a day. It also needs a pass-only receipt setting on sase-core's `check`, and a refused commit must go to the repair flow rather than land red.
3. **Add a macOS cross-compile check on Linux.** cld's experiment caught the real macOS compile errors in about 2 minutes. Pair it with a short Mac portability checklist in sase-core's `AGENTS.md`.
4. **Tell agents working from another project** to run sase-core's check when they change it.
5. **Give failures an owner:** declare stages on sase-core's check, stop one failing test from hiding others (`--no-fail-fast`), pin the Rust version, and assign a repair agent on the first red push.
6. **Require CI to pass before code reaches master** only if red time stays above about 5%. It means switching sase-core from pushing straight to master to PRs.

**Limits.** My data covers athena only; the 59 commits made from apollo couldn't be classified, so I'm assuming the same pattern holds there.

Follow-ups 2–6 are proposals only; I didn't file beads for them because they're design choices for you.

The report and the five source reports are in `202610/sase_core_ci_red_recurrence_and_landing_gate/` in the research repo, and the report is registered as `research:202610/sase_core_ci_red_recurrence_and_landing_gate/sase_core_ci_red_recurrence_and_landing_gate__final.md`. The research-repo changes will be committed automatically after this turn.
