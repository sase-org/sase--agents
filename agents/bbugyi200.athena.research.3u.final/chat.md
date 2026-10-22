# Chat History - ace-run (research.3u.final)

- **TIMESTAMP:** 2026-10-06 17:44:17 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3u.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_161855.md`

## Prompt

%clan(research.3u, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Does the number of beads that exist for a sase project matter for bead read/write
performance? If so by how much? What are some ways that we can compress and/or archive
old beads in order to improve performance without losing any information permanently?

Can you do some research with the goal of answering all of these questions? Also,
critique this plan in general. Is this a good idea? Would you take a different approach?
Make any adjustments to the requirements that you think are justified but clearly call
these out. End your analysis with a recommended solution.]]) %id:research.3u.final %m:@xlarge
%wait:research.3u.cdx %wait:research.3u.cld %wait:research.3u.grk %wait:research.3u.mus %wait:research.3u.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Does the number of beads that exist for a sase project matter for bead read/write
performance? If so by how much? What are some ways that we can compress and/or archive
old beads in order to improve performance without losing any information permanently?

Can you do some research with the goal of answering all of these questions? Also,
critique this plan in general. Is this a good idea? Would you take a different approach?
Make any adjustments to the requirements that you think are justified but clearly call
these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3u.cdx`, `research.3u.cld`, `research.3u.grk`, `research.3u.mus`, `research.3u.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.3u.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3u.linker`, can find it:

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

I've read the cdx and cld reports; now reading grk, mus, and gem.

Profiling the live store's replay cost now. First I'm finding the Python environment that has the `sase_core_rs` binding.

The benchmark built. Running it now against a scratch copy of the live store.

Back in the research questions: checking prior research, the goal-ledger decision, and existing beads that track these fixes.

All five reports are committed in the research repo. Moving them into a new `bead_history_cost_and_lossless_archival/` directory now.

No linked plugin (sase-github, sase-telegram, sase-nvim) reads `issues.jsonl`, so its consumers are limited to sase and sase-core. Writing the consolidated report now.

Duplicate search found no existing reports of either defect. `sase-1c4` concerns outbox operation-ID reuse, a different defect. Sweeping last week's tasks and in-progress epics next.

Epic note recorded on `sase-yy.8`. Now creating the TUI Beads pane bug task.

Filed: `sase-1h5` (TUI bug, now ready, linked to `sase-zn`), a DISCOVERED ISSUE note on `sase-yy.8`, and a +1 with new evidence on `sase-17r`. Checking repository states before the final declaration.

Only the research repo has changes: the five moved reports plus the new final report and its data directory. Submitting the final declaration.

The consolidated report is written and registered for the linker as `file:explicit:77c9bd77e3c02bec214dc32d`. The research-repo changes are declared for the host to commit.

**Does bead count matter?** Yes. Every bead read and every write replays the whole event store: 2,108 files and about 48,400 events, ~0.5 s in Rust and ~0.6 s through Python. Looking up one bead costs the same as summarizing all 7,034. The cost grows with total history (events and bytes), not with the number of open beads.

| | Today | 2× (~Jan 2027) | 4× (~mid-2027) |
|---|---|---|---|
| One replay | 0.58 s | 1.28 s | 2.70 s |
| A write (local part that grows with the store) | ~3–4.5 s | ~6–9 s | ~16–21 s |
| TUI Beads pane, per 10 s refresh | 2.8 s | 8.2 s | ~48 s |

- **Growth:** the store adds about 88 beads a day, and that rate is rising.
- **Writes:** each one does 3–5 replays, then rewrites and commits the 20.8 MB `issues.jsonl`.

**Where the time goes:** I built a stage-timing benchmark against the Rust core. It settled the reports' main disagreement:
- **File I/O is small.** Opening and reading every file is 15 ms of the ~480 ms. gem's claim that opens dominate is wrong.
- **About 40% is waste.** Re-checking a migration that already finished costs ~130 ms, and a deep copy plus repeated validation costs ~60 ms.

**Costs that aren't bead count:**
- **Audited reads:** `sase bead read` takes 5–8 s, but only ~0.6 s of that is the bead store. Another 2.9 s goes to rescanning all 11,419 artifact-link outbox entries on every read.
- **Git bloat:** it comes from the committed `issues.jsonl`, not from old beads.
- **Hidden clone:** the host's hidden beads clone holds 1.84 GiB of loose objects that never get packed.

**Archiving and compression:**
- **Archiving buys little.** Moving closed beads out only speeds replay by 1.6–6.8×, depending on the age cutoff, and that gain shrinks as new beads pile up.
- **Archiving is risky.** Live beads depend on closed ones, and 481 closed phases sit inside live epic files. Closed beads also keep getting written: I counted 2,899 events on 968 beads arriving a week or more after they closed. A read-only archive would break that.
- **Compression doesn't help speed.** Replay is CPU-bound, and git already compresses history.

**Critique:** the instinct is right (closed history sits on every operation) and the no-loss constraint is right. But archiving first targets the smaller, shrinking win and adds the most ways to break things. I'd change the goal from "fewer beads" to "bead latency doesn't grow with closed history." The report spells out seven requirement changes.

**Recommendation, in order:**
1. **Remove the waste:**
   - make the outbox check constant-time;
   - fix the Beads pane's grouping loop and forced refresh;
   - drop the migration re-check, the deep copy and the repeated validation;
   - do one replay per command;
   - get the hidden clone packed.
2. **Add a read cache in the Rust core.** It's a disposable, gitignored file that is rebuilt whenever anything doesn't check out. Saving the reduced state and applying only newly appended events gives exactly the same result as a full replay, falling back to a full rebuild otherwise. This acts as an archive without moving any data.
3. **Stop committing `issues.jsonl` on every write.** First, the five places that use its modification time to detect changes need a replacement signal, or those views will silently go stale.
4. **Physically seal old beads only if a size or speed trigger fires.** Files would move unchanged, still accept writes, and be checked against a full replay. No event is ever edited, compressed in place or deleted.

The September research recommended the same first two steps, and only the integrity-guard fix (`sase-17q`) has landed. The next useful move is turning this into an epic, not more research.

**Beads:**
- Filed `sase-1h5` for the Beads pane bug (marked ready, linked to `sase-zn`).
- Added a "discovered issue" note on epic `sase-yy.8`, whose phase introduced the outbox check.
- Added a +1 with the new hidden-clone numbers on `sase-17r`.

All five reports and the cdx data folder are in `202610/bead_history_cost_and_lossless_archival/` in the research repo. The data folder kept its old name so cdx's link still works. My benchmark code and results are in `bead_history_cost_and_lossless_archival__final_data/` next to the report. I didn't create the `_narration.md` file; that's not part of my steps.

Files are in `202610/bead_history_cost_and_lossless_archival/`:
- bead_history_cost_and_lossless_archival__final.md
