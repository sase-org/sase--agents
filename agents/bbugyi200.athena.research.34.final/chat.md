# Chat History - ace-run (research.34.final)

- **TIMESTAMP:** 2026-10-01 11:20:35 EDT
- **MODEL:** claude/opus
- **AGENT:** research.34.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_102713.md`

## Prompt

%clan(research.34, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Why is master failing in CI for
this project? What can I do to fix this an prevent this from happening again in the
future? Can you do some research with the goal of answering these questions? Make sure
your report is excellent, concise, and beautiful. End your analysis with a recommended
solution.]]) %id:research.34.final %m:@xlarge
%wait:research.34.cdx %wait:research.34.cld %wait:research.34.grk %wait:research.34.mus %wait:research.34.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Why is master failing in CI for
this project? What can I do to fix this an prevent this from happening again in the
future? Can you do some research with the goal of answering these questions? Make sure
your report is excellent, concise, and beautiful. End your analysis with a recommended
solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.34.cdx`, `research.34.cld`, `research.34.grk`, `research.34.mus`, `research.34.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Read the cdx, cld, and grk reports and half of mus. Now finishing mus and gem.

All five reports are read. Next I'm checking where they disagree: whether test selection is to blame, how receipts are enforced, the Python version skew, and the current state of master.

The receipt and Python-skew claims check out. Next is the main disagreement: does diff-scoped test selection actually miss these tests? I'm replaying the selector at the culprit commits.

Confirmed: only 26 of the last 1,000 local `check` runs passed. Next I'm checking the repair beads and the existing hold and ci_watch machinery.

Bead counts match cld: 68 `ci` and 89 `flake` beads sit untriaged in "ready." Now I'm checking whether anything on the landing path consults master's CI status, and what a `hold` actually blocks.

All conflicts are resolved. Now I'm cleaning up the scratch worktrees and moving the five reports into place.

Reports moved. Now writing the consolidated report.

The final layout matches the expected structure. Submitting the final declaration.

`master` has been red since 2026-09-18, about 1,110 commits ago. The cause is not CI itself: master currently has 13 real, small breaks, and nothing on the landing path refuses a red change. The last 198 Master Gate runs all failed.

**What's broken now** (latest completed gate, `90be0cff56`):
- **Lint:** symvision flags three unused public symbols added by `018061f6f2`.
- **Collection:** a test facade still imports a test that `c6b802a647` renamed. The ImportError also breaks `test_contract_manifest`.
- **Stale tests:** 11 tests still expect the old behavior after recent changes: `history_text` launch mocks, the `memory history --at` completion and help, the memory event shape, an unreviewed audit site, the schema wording, and a Python 3.12 argparse help string.
- **Size:** each break is a 5–30 minute fix, about 1–2 hours in total. Most already have beads (sase-1dn, sase-1dh, sase-1cm, sase-1de), but nobody has fixed them.

**Why it keeps happening:**
- **No refusal on landing.** Master Gate runs only after the push, and `master` has no branch protection. The finalizer records `"unverified"` instead of refusing.
- **Verdicts arrive too late.** 42% of pushes land before the previous commit's gate (12.7 min median) finishes.
- **Local checks can't pass.** Only 26 of the last 1,000 local `check` runs passed, because master's own failures redden every run. So "my part looks fine" became the landing rule, and the culprit agents' own checks were red or killed before they landed.
- **Repairs get overtaken.** On 09-29 a repair cut failures from 61 to 4, and they were back to 10 within 21 minutes. 68 `ci` beads and 89 `flake` beads sit untriaged.
- **Python version mismatch.** Agents run Python 3.14 locally while the gate uses 3.12. I confirmed this hides one failure locally (the argparse help string renders differently on 3.12).
- **Release blocked.** PyPI is still on 0.17.1 (from 08-29), and release PR #299 has been open since 08-30.

**Where I overruled the other reports:**
- **Test selection.** Four of five blamed diff-scoped test selection. I replayed the selector at all 9 culprit commits and every one escalated to the full suite, so the broken tests were in scope. There is one real blind spot: a test file that imports another test file isn't picked up when that file changes. The "always-run contract tests" they proposed already exist.
- **Merge queue.** Three recommended a GitHub merge queue. The project's own CI decision record rejected that, and at about 90 commits a day a one-at-a-time queue would need roughly 19 hours of gate time daily.
- **Culprit commits.** I corrected several commit attributions and test names in the gem and mus reports by checking git history.

**Recommended solution:**
1. **Today: stop the line.** Hold new launches and let running agents finish, because a hold doesn't stop agents that are already running from pushing. Then have one build-cop agent, explicitly authorized to run `just check-full`, land all 8 fixes as one commit. Lift the freeze only when Master Gate and Full CI are green on that commit.
2. **This week: adopt a "green-or-revert" landing rule.**
   - The commit finalizer refuses a `master` push without a passing `check` receipt, and refuses non-repair landings while master is red.
   - A newly red commit triggers an automatic fix attempt, then a revert if master is still red after 60 minutes.
   - Pin local Python to 3.12 with a `.python-version` file.
3. **Next:** stop lint failures from hiding later checks, cover the test-import blind spot, give `ci` beads a 24-hour triage clock, and show "commits ahead of last green" in ACE.

Steps 2's two finalizer changes alter existing design decisions, so they need a new decision record and a feature flag.

The host commits the research repo once this turn ends.

Files are in `sase/repos/research/202610/master_ci_red_why_and_how_to_stay_green/`:
- master_ci_red_why_and_how_to_stay_green.md (the consolidated report)
- master_ci_red_why_and_how_to_stay_green__cdx.md
- master_ci_red_why_and_how_to_stay_green__cld.md
- master_ci_red_why_and_how_to_stay_green__grk.md
- master_ci_red_why_and_how_to_stay_green__mus.md
- master_ci_red_why_and_how_to_stay_green__gem.md
