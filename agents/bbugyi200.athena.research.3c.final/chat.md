# Chat History - ace-run (research.3c.final)

- **TIMESTAMP:** 2026-10-02 13:37:48 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3c.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124120.md`

## Prompt

%clan(research.3c, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add
excellent support for the recently added memory file history functionality to the TUI
(see the sase-1dr epic bead for context). I'm pretty sure sase's pager is the only thing
that supports memory history at the moment. Can you do some research with the goal of
helping me decide the best way to implement this? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! End your analysis with a
recommended solution.]]) %id:research.3c.final %m:@xlarge
%wait:research.3c.cdx %wait:research.3c.cld %wait:research.3c.grk %wait:research.3c.mus %wait:research.3c.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to add
excellent support for the recently added memory file history functionality to the TUI
(see the sase-1dr epic bead for context). I'm pretty sure sase's pager is the only thing
that supports memory history at the moment. Can you do some research with the goal of
helping me decide the best way to implement this? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! End your analysis with a
recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3c.cdx`, `research.3c.cld`, `research.3c.grk`, `research.3c.mus`, `research.3c.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3c.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3c.linker`, can find it:

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

I've read the first of five reports (cdx); now reading the other four, then I'll verify their key claims in the code.

I've read all five reports. Now verifying the key claims and disagreements against the current code (HEAD is newer than the revision the researchers inspected).

Checking the status of the related follow-up beads (sase-1es, 1eu, 1en, 1e5, 1e6, 1e7, 1ee) to resolve sequencing disagreements between the reports.

Measuring the history service on this repo: warm `timeline` ≈58 ms and `feed` ≈40 ms. Now checking whether `subjects()` can cheaply feed a per-row glance in the note rail.

Running a quick headless probe to measure the real Memory card size inside the Admin Center (only one researcher measured it, and it decides how much history chrome fits).

Still measuring the Memory card's real size inside the Admin Center; my first probe gave numbers that disagree with one researcher's, so I'm capturing a screenshot to settle it.

Reports moved. Now writing the consolidated report.

Both confirmed: no memory-history files changed since the researchers' revision, and the feed exposes 21 deleted subjects. Tightening that bullet with the evidence.

Registration succeeded and the layout matches the spec, with no `<name>.md` placeholder. Now submitting the final declaration.

My recommendation is to make the Memory pane itself aware of history, drawing it with the pager's existing renderers, and keep the full-screen pager as the place for deep reading. The consolidated report is written and registered as `file:explicit:cba4cd3d8de4354d1288a0d1`. It's committed along with the five member reports under `202610/memory_history_tui_support/`; there's no `<name>.md`, which is left for the linker.

**The most important finding:** you're right that only the pager supports history, and it's worse than that. The TUI's `H` and `C` keys have never opened anything. They fail on every press, and the error toast fails the same way, so nothing appears. Two researchers reproduced this, and I confirmed it's still present on current `master`. All four broken calls are in one file (`memory_pane_history.py`), and no test presses either key.

**Recommended design:**
1. **Fix the entry points first.** Repair `H`/`C`, add tests that actually press the keys plus a cheap lint check against this bug pattern, and stop the History row from showing a stale summary or a loading `…` forever after a failure.
2. **Put time on the note card.** A two-row strip replaces today's History row, using the pager's look: version label, scrubber, and what changed. `( ) { } =` step through and diff versions right on the card. It gets a violet "past" frame, and past versions are read-only and never logged as agent reads. `H` opens the pager at the exact version you're looking at, not always at now.
3. **Two new views in the left list:**
   - `@` swaps the note list for the selected note's **version list**, with a live preview and a way to mark a version to compare against.
   - `C` swaps it for a **changes review** grouped by day, with bead/agent/commit chips and word diffs, defaulting to the current scope.
   - `Esc` always returns to the note you were on.
4. **Complete the list:** a recency glyph on each row, an Instructions group for `AGENTS.md` and its copies, and an opt-in "include deleted" filter.
5. **Agents tab:** chips showing which version of each memory file an agent read and whether it has changed since (follow-up `sase-1e5`). Then add a review watermark ("N new since you last looked") to the changes view (`sase-1e6`).

**What the evidence settled:**
- **Don't embed the pager widget in the card yet.** Both pager epics (`sase-1es` and `sase-1eu`) are mid-rewrite today, the widget can't be dropped into another screen without new adapter work, and nothing in the TUI embeds it so far.
- **Two reports had the wrong data source for the per-row glyph.** The history service's subject list comes back with no versions. One changes-feed call per scope (about 43 ms) covers every note.
- **One report said the card is about 52×15 cells.** My probe found it much larger, roughly 68–87 columns wide at 120×40, so the card works as a reading surface. The probe's heights are approximate.
- **One report's proposed keys `.` and `Tab` are already taken in the Memory pane.** All the keys this design adds (`( ) { } = @`) are unused there today.

If only two phases ship, ship 1 and 2. The report has the mockups, the full key table, performance budgets, and the open questions for you, such as how loud unreviewed changes should be.
