# Chat History - ace-run (research.4e.cld)

- **TIMESTAMP:** 2026-10-13 11:52:39 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4e.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_112927.md`

## Prompt

%id(cld, clan=research.4e)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4e.cdx`, `research.4e.grk`, `research.4e.mus`, `research.4e.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Reading glossary definitions for the artifact terms, then digging into the rename history I just found.

Checking why the labels were made singular in August (agent `zl`'s prompt), then surveying every label surface.

Now surveying the current TUI: top-level tab names, other sub-tab strips, and where the Artifacts labels surface.

Checking the live Artifacts strip next (screenshot) so I can measure label widths against the full/compact/micro tiers.

Measuring how wider plural labels would interact with the strip's fit ladder.

Now computing full/compact/micro strip widths for the candidate label sets with the real strip renderer.

Measuring the strip's available width across terminal sizes (the earlier SVG lookup missed; switching to the headless harness).

Big finding: the "Stitch" pane classifies each row's origin as `stitch`, `auto`, or `manual` ("no SASE provenance"), so many rows aren't stitches at all. Quantifying that mix on real data.

Default view: ~92% of rows are true stitches; with the pane's `sidecar:` toggle on, only ~19% are (80% are `auto` bead/plan-sync commits). Now checking how many Patches actually have a PR.

Every Patch here (315/315) has a PR URL, 77% adopted external PRs — so "PRs" matches this machine's data even though the model allows PR-less Patches. Now the bead mix, to test "Bugs".

Beads: 7,478 total — 71% phases, 13% plans, 16% tasks; only 263 (3.5%) are `bug`-typed. Checking vocabulary collisions for "Bugs"/"Issues"/"PRs"/"Commits".

Label-surface inventory done. Now gathering external precedent (tab-label conventions, how comparable tools name these collections).

Back to the codebase: checking whether pane metadata is already configurable, which bears on a config-driven option.

Pinning exact file:line locations for the hardcoded label duplicates.

Running the width calculation for the 5-tab layout (no Research provider) too, since that's the default install.

I have enough evidence. Writing the report now.

Quick last check for toast/notification strings that embed the tab name (e.g. "Artifacts ▸ Stitch"), so the inventory is complete.

Report written. Registering it as a durable artifact.

Registration succeeded. Submitting the final declaration.

I'd pluralize everything, rename Stitch → Commits, but keep Patches and Beads rather than switching to PRs and Bugs. The report is written and registered as `research:202610/artifacts_subtab_labels_commits_prs_bugs__cld.md` (`file:explicit:28d643a50ee845cb3e6be391`); the host commits it to the research repo when this turn ends.

Recommended strip: **`Commits │ Patches │ Beads │ Plans │ Research │ Files`**

**This would undo three recent decisions.** In August the strip went Commits → Stitches (Aug 10), PRs → Patches (Aug 11) and plural → singular (Aug 13). The singular change had no recorded reason; the prompt only asked to stop pluralizing. Also, "Bugs" was never a name for beads: it was a separate pane of remote tracker issues, retired in that same August 11 change. Each of the two big renames regenerated 200+ screenshot goldens. None of these choices was written down as a decision record, which is how the strip keeps flipping.

**Tab by tab:**
- **Pluralize: yes.** The top-level tabs (Agents, Artifacts, Services), the docs and the empty-state text are already plural. For Plans, set an explicit label in the plan provider's spec instead of bringing back the auto-pluralizer, which was removed because words like "Research" don't pluralize.
- **Stitch → Commits: yes, and it's the more accurate name.** Every row is a VCS commit tagged as `stitch`, `auto` or `manual`. Over the last 30 days, 92% of rows are stitches in the default view, but only 19% are once sidecars are shown. The pane's own empty state and detail text already say "commit". Keep "stitch" wherever it names the real concept (`@stitch:`, `sase stitch`, the Patch `STITCHES:` section).
- **Patch → PRs: no, keep Patches.** Today all 315 Patch records on athena do have a PR (77% of them adopted external PRs), so this is the most defensible of the three. But a Patch is defined as existing with or without a PR, and the core is meant to be VCS-neutral (git and hg). "PR" is GitHub's word, while "patch" is already ordinary vocabulary. The command palette already finds the tab when you type "prs".
- **Bead → Bugs: no, keep Beads.** Only 263 of 7,478 beads (3.5%) are bug-typed; 71% are epic phases. "Bug" already means a task type, the old `@bug:` ref, a command-palette category, and the retired pane. "Issues" is the better plain word, but the Beads pane already uses "issue" for linked GitHub issues, and "Tasks" clashes with task beads.

**How I'd implement it:**
1. Gather the labels into one table first. About 8 places hard-code their own copy today (onboarding, copy mode, pane headers, Help titles, plan defaults).
2. Flip them all in one change. Tab ids stay plural (`stitches`, `beads`), so saved state, keymaps and config are unaffected: no migration and no feature flag.
3. Write a decision record with the rule "a tab's label names what its rows are", so the strip doesn't flip a fifth time.
4. Optionally, add a per-user config override (`ace.artifacts.panes.<id>.label`) so you can try "Issues" or "PRs" locally.

**Width cost:** the recommended labels are 6 cells wider. Normal 120 and 130 column terminals are unaffected; at 140, 150 and 180 columns with six tabs they drop one layout tier (at 140, inactive labels hide). Your proposal is almost the same width as today only because "PRs" and "Bugs" are short. The 140-column case is mostly caused by a spacer that widens at that size; the report covers fixes.

Open questions for you:
- Do you ever want GitHub wording in the core TUI? If yes, the noun should come from the VCS provider rather than hard-coding "PRs".
- Would you rename the Beads pane's "external issue" wording to free up "Issues" as a tab name?
