# Chat History - ace-run (research.4q.final)

- **TIMESTAMP:** 2026-10-17 16:51:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4q.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_154710.md`

## Prompt

%clan(research.4q, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you reassess the solution proposed by the
merge_queue_fenced_master_and_exact_sha_releases.md file in the research sidecar repo,
make any changes to its requirements (in the new report your create) that you think are
warranted (but clearly call these out), and then recommend whether or not this work
should be a single epic or multiple epics with justification and indepent epic
verification steps if you think that multiple are warranted?]]) %id:research.4q.final %m:@xlarge
%wait:research.4q.cdx %wait:research.4q.cld %wait:research.4q.grk %wait:research.4q.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you reassess the solution proposed by the
merge_queue_fenced_master_and_exact_sha_releases.md file in the research sidecar repo,
make any changes to its requirements (in the new report your create) that you think are
warranted (but clearly call these out), and then recommend whether or not this work
should be a single epic or multiple epics with justification and indepent epic
verification steps if you think that multiple are warranted?

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.4q.cdx`, `research.4q.cld`, `research.4q.grk`, `research.4q.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4q.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4q.linker`, can find it:

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
├── <name>__gem.md
└── <name>__final.md
```

## Response

Reading the four researcher reports now (cdx done); next cld, grk, gem, then the original proposal.

Now the original proposal under review.

cld's install-breakage finding holds: sase 0.17.1 needs `sase-core-rs<0.33`, and PyPI has nothing below 0.34.23. Next I'll confirm what a clean install actually resolves to.

Confirmed: unpinned `sase` resolves to 0.1.0. Now the live GitHub state: repo settings, gate health, and the release PR.

Master Gate is 8 green of 98 completed with a 22-run red streak; Full CI is 0 of 29. Next: which Full CI jobs fail now, to settle whether `visual-test` is still red.

sase has 103 merge commits, mostly June PR merges. That's a natural experiment: if cld is right, the June changelog sections should show the same change listed more than once.

The four reports are moved (git shows them as renames). Before writing the final report I'll check one thing from the changelog test: two June fixes that are missing from the changelog entirely.

Report written. Two small numeric fixes are needed: the heavy test jobs ran 64–76 minutes, and `visual-test` ran 29–31 minutes. I'll also confirm the `work_prompt.py` line numbers I cited.

Fixes applied. Now I'll check the final layout and register the consolidated report.

The file is 1,119 lines, about twice what I wrote, and the harness says it changed on disk. I'll check whether a formatter rewrapped it or whether something broke.

Re-registering the same label and source replaces the snapshot, so I'll re-register after a final skim. First I'll read the hook-restructured file end to end to make sure nothing else was distorted.

I've written the consolidated report and registered it as `file:explicit:3fcf49260f9f3630266d9abc`. The four reports and the new `__final.md` are in `202610/merge_queue_fence_reassessment_and_epic_split/`. The host commits them after this turn.

**Verdict.** Keep the original's design: GitHub's native merge queue with zero approvals, PyPI publishing exactly the release commit that passed checks, and fixing flaky tests before the queue is enforced. All four researchers agreed, and nothing I checked contradicts it.

**Requirement changes.** The report marks each original requirement (A–J) as kept, modified or replaced, and adds new ones (N1–N13). The six that change what gets built:
- **Installability comes first (new).** `pip install sase` installs **sase 0.1.0** today; I reproduced this with `uv`. The latest release, 0.17.1, needs a `sase-core-rs` version that PyPI cleanup deleted. Nothing in sase-core's cleanup protects versions that published sase releases still need. Two requirements follow:
  - releases cut the sase-core release they need, and cleanup never deletes those versions;
  - a daily clean-install check.
- **Rebase instead of merge commits. This reverses the original.** sase's own `CHANGELOG.md` shows what happened when PRs landed as merge commits in June: three changes listed twice and one agent commit dropped. History has been linear since Oct 10.
- **Handle a broken base (new).** A queue stops bad changes, but not tests that start failing with no change, such as today's date-dependent fixture. When that happens every queued change fails. The report adds:
  - a check that the base itself is red before any repair agent starts;
  - a circuit breaker that pauses the queue;
  - letting the fix jump the queue;
  - a nightly test run with the clock shifted forward.
- **Queue mode is a per-project setting, not a feature flag.** SASE's flag rules forbid flags for permanent choices. Beads keep closing the way they do today, since agents close them during their turn. What changes is that anything waiting on a bead also waits until its code has actually merged.
- **An explicit list of which checks block a release.** The fast gate checks, packaging checks, and the Python 3.13/3.14 tests block a release. Visual, performance and tutorial tests are advisory, with an owner and a deadline. `visual-test` now passes but takes about 30 minutes, past the gate's 20-minute limit.
- **Shipping 0.18.0 is out of scope.** The existing bead chain (`sase-1lh`, `sase-16p`, `sase-10d`) owns it.

**Epics: four, plus two items that are not epics.**
- **Step 0** (you, today): a ruleset blocking force pushes and deletion on `master`.
- **Track 0** (existing beads): get an installable release out.
- **A:** releases that publish exactly the tested commit, plus the install safeguards.
- **B:** make the fast gate trustworthy.
- **C:** queue-aware landing as a SASE feature, proven on a sandbox repo.
- **D:** switch `sase/master` over to the queue.

A, B and C can run in parallel. D starts once B's retry and quarantine mechanisms are live and C passes on the sandbox, and D enforces only after a measured soak. Two researchers merged C and D into one epic. I kept them separate because C is proven on a sandbox and D only in production, and D waits on your GitHub admin changes and a soak that single-turn agents can't sit through. Plan D at the same time as C so the cutover has an owner from the start. Each epic has its own verification steps (V-A1 to V-D7) that don't depend on a later epic.

**What I didn't do:** I changed no rulesets, workflows, memory or beads, created no sandbox repo, and ran no CI. Several GitHub behaviors (bypass users pushing directly, whether the landed commit equals the tested one, permissions for jumping the queue) are listed as things to settle on the sandbox.
