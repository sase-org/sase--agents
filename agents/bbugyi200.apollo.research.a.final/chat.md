# Chat History - ace-run (research.a.final)

- **TIMESTAMP:** 2026-09-25 17:12:40 EDT
- **MODEL:** claude/opus
- **AGENT:** research.a.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_162822.md`

## Prompt

%id(final, clan=research.a)
%m:opus@xhigh
%wait:research.a.cdx %wait:research.a.cld %wait:research.a.mus %wait:research.a.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Sase's
finalizers are a critical part of a sase agent's lifecycle yet they are not represented
on the "Agents" tab in any way. I want to add excellent (and beautiful) support to this
tab for finalizers.

Can you do some research with the goal of helping me decide the best way to implement
this? Review the old agents_tab_finalizer_panel.md file in the research sidecar repo for
context and inspiration before performing your own research. Make sure to think hard
about what role decks, cards, and/or card blocks (card blocks are an upcoming
feature--see the agent_data_card_blocks.md file in the research sidecar repo for
context) should play (if any) in providing the user with an excellent way to visualize
and troubleshoot their own finalizers (I have several plans for new finalizers so make
sure you don't overfit this use-case to the builtin `commit` finalizer) . End your
analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, mus, gem, belonging to this
   dispatch's `research.a.cdx`, `research.a.cld`, `research.a.mus`, `research.a.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

Read the cdx report; now reading the other three reports and the two context files.

Now reading the prior context reports (finalizer panel and card blocks).

Code check so far: there are three decks, one preferred-card slot per panel, and cycling visits every deck. Next I'm checking which card holds the fold sections today.

Measuring finalizer artifacts on disk to settle the timing disagreement between reports (p50 2 s vs. ~2 min).

Found something none of the reports covered: 184 shells have a sealed finalizer plan but no result. They're mostly `--plan` shells. Checking why.

Checking what the 184 plan-but-no-result shells actually are.

Verification is done. Quick glyph-collision check before I write the consolidated report.

Verification is done. Next I'll pick a stem with no collision, move the four reports, and write the consolidated report.

Writing the consolidated report now.

The file changed on disk after I wrote it (866 lines), so a formatter probably ran. Checking the result.

A post-write hook reformatted the report. It reads well, so I'm keeping that version. Next I'll check for an existing bead on the chronic stitch warnings before filing one.

`sase-10x` (open, +2) already covers the quarantined-publication root cause, so I'll corroborate it rather than file a new bead. Checking the other two warnings against their closed beads.

The prompt-archive warning has a different root cause: `referenced-by write-back failed: artifact-link legacy index writes are fenced`. Searching for that.

The fence came from `sase-yy.6`'s cutover, and child epic `sase-yy.8` is still in progress. Checking whether it already covers the referenced-by write-back path.

Correction: my "outbox" count also matched "until the outbox is cleared" inside the quarantined warning. Only two warnings are live right now, not three. Fixing the report.

Next: corroborate `sase-10x`, sweep last week's task beads, and check the `sase-196.6.1` note that mentions the fence.

Bead work is done: `+1` on `sase-10x`, and a DISCOVERED ISSUE note on `sase-yy.8.6`. Doing a final structure check of the report and the layout.

The layout is complete. Now the final declaration.

I've merged the four reports and my own checks into `202609/agents_tab_finalizer_visibility/agents_tab_finalizer_visibility.md`. The four originals now sit beside it as `__cdx/__cld/__mus/__gem.md`, and the host commits the research repo.

## Recommendation

Show finalizers at four zoom levels, all fed by one provider-neutral data layer:

1. **Agent row.** A `FINALIZING` status word while finalizers run; it still counts as Running for sorting, filters and capacity. A `⊛` chip appears only while running or after a failure, deferral, refusal or interruption. Successful runs show nothing.
2. **Reply receipt.** A short `─── ⊛ FINAL ───` section at the end of each shell's reply: one line per finalizer showing its key result (a commit SHA, a URL, an exit code), plus a reason line if it failed. This is where you already look when a turn ends.
3. **A new `⊛ FINAL` deck.**
   - **Cards:** an `Overview` card (the plan, why each finalizer was or wasn't selected, submission attempts and rejections, config drift), then one card per finalizer instance, keyed by its id (`commit`, `check`, …). The tab strip doubles as a status strip, and a chosen card stays selected as you move between agents.
   - **Card blocks:** one per *run*, meaning one shell's execution. That keeps the card-block design's single meaning, so `[`/`]` means older/newer shell in both Reply and FINAL.
   - **Inside a run:** attempts are sections, each holding its operations, progress steps, typed evidence and a live log tail. There are no retry or cancel controls in the first version.
4. **Authoring your own finalizers.** The `Overview` card, plus a read-only `sase final` view of an agent's run, answers "why didn't my finalizer run?" and "what did my validator reject?".

Underneath, everything is additive and nothing is specific to `commit`:
- a progress log written by the finalizer controller;
- one uniform per-operation record across the three executors;
- an opt-in step channel that plugins and `sase stitch create` can write to;
- bounded live logs;
- a compact status summary in `agent_meta.json`;
- one shared Rust-core view model that the TUI and CLI both render.

`commit` just gets extra formatting (such as links to the commit viewer); every future finalizer gets a full card automatically. The cheapest useful first slice is the data layer plus the row signal and the receipt.

## How the disagreements resolve
- **Placement:** cdx and cld wanted a new deck, gem a card in Main, mus a fold section. I went with the deck. A fold section would now render inside the Context card. A Main card has nowhere to put runs or attempts, and it would drag off-thread file loading into Main.
- **What a card block represents:** cdx said a run, cld an attempt, gem an instance. I went with a run. On today's data none of these would show more than one block in more than about 1% of cases (no instance retried; 1 of 110 sessions had two runs). So the deck must work well with no blocks at all.
- **Timing:** the old 2-second median is stale. I measured about 108 seconds from reply to result across 196 runs, which matches cld.

## New findings from my own checks
- **Skipped finalizers look like failures.** 102 `--plan` shells in the last 15 days had a finalizer plan but correctly never ran it: a pending handoff skips finalization and writes no result. Every report's rules would have shown these as not run, unavailable or interrupted. The design adds a calm `skipped · handoff` state, which the controller can record with one extra log line when it skips.
- **Submission rejections are common.** 41% of runs had at least one rejected `sase final submit`, which is why the `Overview` card leads with that timeline.
- **Nearly every commit carries warnings.** 96% of successful commit outputs contain them, and two are live right now:
  - The "56 quarantined publication requests" warning is open bug `sase-10x`; I added a `+1` with my evidence.
  - "Prompt archive publication was deferred" is caused by a write path that still hits the legacy link index after the `sase-yy.6` cutover fenced it. I recorded it as a discovered issue on the in-progress epic `sase-yy.8.6`.

## Decisions for you
- The deck's name, glyph and accent: `⊛ FINAL`, picker key `n`, rose accent.
- Whether the `Overview` card shows configured-but-unselected finalizers, dimmed with the reason. I recommend yes.
- Whether a failing finalizer should override your chosen card as you move between agents. I recommend no, consistent with Main.
- Whether to fix the chronic commit warnings before the deck ships; otherwise "succeeded with warnings" describes almost every run and stops meaning anything.
- Whether shells that skipped for a handoff get a one-line receipt or none. I recommend none.
