# Chat History - ace-run (research.4e.final)

- **TIMESTAMP:** 2026-10-13 12:14:08 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4e.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_112927.md`

## Prompt

%clan(research.4e, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
think I would like to rename the sub-tabs on the "Artifacts" tab.

- We should name "Stitch" to "Commits", "Patch" to "PRs", "Bead" to "Bugs", "Plan" to
  "Plans", and "File" to "Files".
- The goal of this change would be to use a more common terminology to describe the
  different artifact tabs and pluralize the tab names (which seems more appropriate).
- I'm not sure if getting rid of the stitch/patch/bead tab names is the right call.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.4e.final %m:@xlarge
%wait:research.4e.cdx %wait:research.4e.cld %wait:research.4e.grk %wait:research.4e.mus %wait:research.4e.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
think I would like to rename the sub-tabs on the "Artifacts" tab.

- We should name "Stitch" to "Commits", "Patch" to "PRs", "Bead" to "Bugs", "Plan" to
  "Plans", and "File" to "Files".
- The goal of this change would be to use a more common terminology to describe the
  different artifact tabs and pluralize the tab names (which seems more appropriate).
- I'm not sure if getting rid of the stitch/patch/bead tab names is the right call.

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
   dispatch's `research.4e.cdx`, `research.4e.cld`, `research.4e.grk`, `research.4e.mus`, `research.4e.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.4e.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.4e.linker`, can find it:

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

All five reports are in my research checkout. Next I'll read each one through `sase artifact read`.

I've read all five reports. They disagree on the main points, so next I'll check the disputed facts against the source code and history.

Some counts are confirmed: only 3.5% of beads are bug-typed, and 21% of open ones. Next I'm checking the Patch-to-PR ratio and the stitch-origin split.

The commit-origin numbers check out: 92% of rows are stitches in the default view, but only 19% when sidecars are shown. Next I'm checking whether any tab label is stored in the Rust core.

I've verified the main disputed claims. Next I'll check the research repo's conventions for a consolidated report, then move the five reports into place.

The five reports are moved and history dates are confirmed. Next I'll write the consolidated report.

Report written. Now registering it as a durable artifact.

The layout is complete and registration succeeded. Now submitting the final declaration.

I'd ship **Commits · Patches · Beads · Plans · Files**. Your hesitation about dropping the SASE names is right for Patch and Bead, and wrong for Stitch, where the common word is actually the more accurate one.

All five reports were found, one per suffix, and the consolidated report is written and registered (`file:explicit:0a0570142600da618d66f448`). The host will commit the research repo after this turn.

**What to keep from your proposal**
- **Plural labels:** four of five researchers agree. The August switch to singular gave no reason beyond "They should be singular" (I checked the plan and the commit). The parent tabs and the surrounding text are already plural.
- **Stitch → Commits:** the pane is a commit log, and only some rows are stitches: 92% in the default view, 19% with sidecars shown (I re-measured over the last 30 days). Its own empty state and the `sase stitch list` help text already call the rows commits.

**What to drop**
- **Patch → PRs:** all 315 of your Patches do have PRs today, so it isn't false for you right now. It's still the wrong label: every row opens as a Patch (`sase patch`, `@patch:`), "PR" is GitHub's word in a core that isn't tied to GitHub, and typing `prs` in the command palette already finds the tab.
- **Bead → Bugs:** only 3.5% of all beads are bugs (21% of open ones). "Bugs" is also already a command-palette category for the external-issue actions inside the Beads pane.
- One researcher suggested Changes and Issues instead. "Changes" partly undoes the August 9 ChangeSpec → Patch rename. "Issues" clashes with the Beads pane's existing "External issue" wording.

**What your request missed**
- **The tab label is also used as a singular noun** in about 17 places, such as "Refresh {label}s" and "Open selected {label}". Just renaming would print "planss" and "Open selected plans". It's already broken for the Research tab, which shows "Refresh researchs", a "# Researchs" loading heading and a "researchs" palette context. The fix is to store a singular item noun next to each label; this fixes the Research text even if you never rename anything.
- **This is the fourth relabel of this strip since August 9.** I'd write a decision record with conditions for reopening it so it stops flipping.

**How to implement it**
- Change only the visible labels. Ids, keymaps, config keys, `@stitch:`/`@patch:`/`@bead:` refs, CLI commands, saved state and number keys stay the same. That means no feature flag, no data migration and no change in sase-core (I confirmed no tab labels live there).
- Set the Plans label explicitly in the built-in plan provider rather than bringing back automatic pluralizing.
- Leave the retired Agent pane and the Research tab as they are.
- Keep the old words searchable in the command palette: `stitch`, `bead`, `bugs`, `issues` and `prs` should all still find the right tab.

**The one decision you need to make:** if you still plan to show stitches that have no commit in this pane (a planned proposal type), use **Stitches** instead of Commits. Everything else stays the same.

Files are in `202610/artifacts_subtab_naming/` in the research repo:
- artifacts_subtab_naming__final.md (the consolidated report)
- artifacts_subtab_naming__cdx.md
- artifacts_subtab_naming__cld.md
- artifacts_subtab_naming__grk.md
- artifacts_subtab_naming__mus.md
- artifacts_subtab_naming__gem.md
