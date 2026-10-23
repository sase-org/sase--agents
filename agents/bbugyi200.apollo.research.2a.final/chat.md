# Chat History - ace-run (research.2a.final)

- **TIMESTAMP:** 2026-10-23 13:00:24 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2a.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261023_115726.md`

## Prompt

%clan(research.2a, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm thinking about moving forward with the E3 epic described by the
pypi_release_reliability_design_and_work_split.md file in the research sidecar repo. Can
you do some research with the goal of making sure we are ready for this epic, describing
the work that has been done so far (e.g. E1 and E2) and what developer-facing behavior
has been changed by that work, and starting the design for the E3 epic?]]) %id:research.2a.final %m:@xlarge
%wait:research.2a.cdx %wait:research.2a.cld %wait:research.2a.grk %wait:research.2a.mus %wait:research.2a.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about moving forward with the E3 epic described by the
pypi_release_reliability_design_and_work_split.md file in the research sidecar repo. Can
you do some research with the goal of making sure we are ready for this epic, describing
the work that has been done so far (e.g. E1 and E2) and what developer-facing behavior
has been changed by that work, and starting the design for the E3 epic?

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
   dispatch's `research.2a.cdx`, `research.2a.cld`, `research.2a.grk`, `research.2a.mus`, `research.2a.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.2a.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.2a.linker`, can find it:

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

I've read the first of five reports (cdx); now reading the other four, then I'll verify the disputed points myself.

The independent Master Gate measurement matches the cld report closely: about 82% red wall-clock time, with flake-only runs at roughly 3.5%. Next I'm checking the code-level claims.

Confirmed several code-level claims, and found another post-snapshot change: sase-core v0.42.2 has now been cut. Checking PyPI and the pin next.

Confirmed that the Full CI and modal-sizing fixes (`sase-1nn.3` and `.4`) are now closed. Still checking the remaining code claims and the design text.

Verification is done; sase-core v0.42.2 also contains the steward binding. Moving the five reports into the consolidated directory now.

Now drafting the two figures and rendering them with the PDF-mirroring config.

Figure 1 passes the fit check. Figure 2 is too tall, so I'm switching it to a column layout.

Figure 2 still fails the fit check after two revisions, so per the diagram rules I'm dropping it and using a table instead. Checking a few final design details before writing.

I have everything I need. Writing the consolidated report now.

The report is written. Full CI tests are still running, as the report says. Registering the consolidated report as an artifact now.

You're ready to start E3 now. The new-file and read-only phases can begin immediately; anything that edits Master Gate or `ci.yml` should wait for the conditions below. The main surprise is that flakes are a small part of why master is red, so E3's value is in labeling each failure and naming its culprit more than in rerunning flaky tests.

**Work so far**
- **E1 (installable family) is closed.** For developers:
  - `uv tool install sase` gets 0.18.0, and the old 0.1.0 is yanked.
  - A daily Linux/macOS install check opens a tracking issue when it goes red. It reports; it doesn't block anything.
  - Plugin release PRs fail if they depend on a sase version not yet on PyPI.
  - Deleting a core file a supported release still needs is refused.

  You declined the 7-day soak and the TestPyPI drill, so neither was done.
- **E2 (release train) has closed 6 of 10 phases but hasn't shipped anything.** What developers see today:
  - an exact `sase-core-rs==0.42.0` pin;
  - `just ratchet-core-pin` replacing the old window recipe;
  - a rewritten `tools/release_watch` with new flags;
  - `ci.yml` usable as a release qualifier;
  - an observe-only release steward.

  Still open: qualification proof, digest-checked publish, the cutover and the first steward release. Releases still go out the old `ci_watch` → `publish.yml` way.

**What the CI data says.** I re-measured the last 200 Master Gate runs independently and got the same numbers as one of the researchers:
- Master was red 82% of the time.
- Runs that failed only on flaky tests account for about 3.5% of that time.
- Only 10 of 62 lasting breakages started right after a green run.

So a perfect rerun barely helps, and the design's "first red commit with a green parent" rule would catch about one break in six. Attribution has to be tracked per failing test instead.

**Conditions before E3 touches the shared workflows**
- **Full CI producing results:** half cleared. Since the reports were written, the setup fix landed and the first new run got past it, but its tests were still running when I finished.
- **Master Gate green at current master:** not yet. One modal-sizing test still fails, even though its fix landed and the owning bead closed this morning.
- **No one else editing those workflows:** not yet. The 0.18.1 release epic and E2's open phases are both still working there.
- **E2 defects to fix as E2 work first:**
  - the "is this commit release-green" check can be fooled by duplicate job names;
  - the steward's rerun step reruns lint jobs too;
  - nothing checks that the published core tag contains the pinned core source.

**Design contradictions the plan must resolve**
- **Rerunning a failed test.** The design says a test that fails only because of run order must stay red, but tests run in a random order (xdist `worksteal`), so a fresh rerun would pass it. I recommend rerunning it once, immediately, in the same worker process. Polluted state survives, so an order-dependent failure fails again. That's my own proposal, not something a researcher tested; if it doesn't hold up, fall back to only accepting reruns for flakes you've reviewed.
- **Qualification evidence.** E2's plan says qualification picks up E3's reruns "with no change". It can't: the validator treats any failed test as red and rejects new fields, so E3 needs a version 2 of the evidence format in files E2 owns.
- **E4's entry point.** I suggest letting E4 start once attribution is live, not waiting for reruns too. That changes the design, so it's your call.

The report also lists 11 design decisions with a recommended option for each. One of the five reports was wrong on several status claims (E2's progress and how much flakes matter); the report corrects them.

Name the epic so it can't be confused with the two other closed "E3" epics, `sase-1ko` and `sase-18j`. I suggest "E3: Trustworthy CI signal (PyPI release reliability)".

**Housekeeping:** the five reports are moved into the new folder, the report is registered as an artifact (ref `file:explicit:a392c07c38c3957b8b93f464`), and the research-repo commit is declared. The report has one diagram; I replaced a second with a table because it rendered too small. Nothing in sase or sase-core was changed or dispatched.

Report: `202610/pypi_release_e3_trustworthy_signal_readiness/pypi_release_e3_trustworthy_signal_readiness__final.md`
