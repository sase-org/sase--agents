# Chat History - ace-run (research.22.final)

- **TIMESTAMP:** 2026-10-18 12:19:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.22.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_111719.md`

## Prompt

%clan(research.22, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you help me review all of the files that the previous agent just tagged in the
research sidecar repo, which are related to our efforts to make sase's PyPI releases
much more reliable? Once you've done that, you should think hard about what the best
possible solution is and how the work should be split up. It's fine if your
recommendation steals a lot from those other research files (i.e. no need to be
original). Converging on the best design/architecture is our main priority.]]) %id:research.22.final %m:@xlarge
%wait:research.22.cdx %wait:research.22.cld %wait:research.22.grk %wait:research.22.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you help me review all of the files that the previous agent just tagged in the
research sidecar repo, which are related to our efforts to make sase's PyPI releases
much more reliable? Once you've done that, you should think hard about what the best
possible solution is and how the work should be split up. It's fine if your
recommendation steals a lot from those other research files (i.e. no need to be
original). Converging on the best design/architecture is our main priority.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.22.cdx`, `research.22.cld`, `research.22.grk`, `research.22.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.22.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.22.linker`, can find it:

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

I've read the cdx and cld reports; now reading grk and gem, then I'll check the live state myself.

All four reports are read. Next I'm checking live state (PyPI, PR #299, core release PR, the new release-watch commit, and the Track 0 beads), focusing on where the reports disagree.

I've confirmed `force-tag-creation` exists in release-please and that a `workflow_dispatch` can target a tag ref. Now reading the two-speed CI decision record, then writing the consolidated report.

Last checks before writing: core storage headroom, and whether the revert path and install canary the reports cite actually exist.

I have what I need. Moving the four reports into the new stem directory, then writing the consolidated report.

Now writing the consolidated final report.

Registration succeeded. Now submitting the final declaration.

I've merged the four reports and my own live checks into one final report, and registered it for the linker as `research:202610/pypi_release_reliability_design_and_work_split/pypi_release_reliability_design_and_work_split__final.md`. The four reports moved into that same folder under their existing suffixes. Nothing outward-facing was changed: no workflows, rulesets, releases or beads, and nothing was dispatched.

**Recommended design**
- **Three separate goals, each with its own check and owner:** `pip install sase` installs the newest release and it works; a tested release reaches PyPI at least every three days; `master` stays green. None of them may depend on a weaker one.
- **A release is a tested pair:** the sase files plus the exact `sase-core-rs` version (`==X.Y.Z`) they were tested against. Build once at the tag, test against the core that's actually on PyPI (not one built from source), upload those same files, then confirm them on PyPI. Today the full test suite never runs against the pair users install.
- **One release coordinator replaces the chain of five scheduled jobs and the watch-only epics.** It grows from `tools/release_watch`, which `sase-1mk.2` just taught to trigger the core release. It keeps no state of its own: each run reads GitHub and PyPI, takes at most one next step, and reports one typed reason for any block, with an owner action. Two of the four reports scheduled this piece last, after the merge-queue switch. It should come first.
- **The merge queue is still the long-term way to keep `master` green, but it isn't blocking PyPI today.** The slow release tests stay outside the queue: a failed release only wastes a version number, while putting those tests in the queue would stall every PR behind the release PR for about 90 minutes a day.

**Where the reports disagreed, and how I settled it**
- **Release workflow:** two reports say the publish workflow's provenance is false; another says that's overstated. Both are partly right, and the fix is the same: run the publish job from the tag itself.
- **Delete-protection rule:** keep the old PyPI core versions every supported release needs, across the last 10 or more releases and including every platform wheel. Keeping only the last two can delete the last version that actually worked.
- **Code placement:** landing state belongs in `sase_core`; release logic stays in `tools/`.
- **Stale claims dropped:** gem's "1 in 271 runs" figure, its stale core commit, "Step 0 today", the manual merge of PR #299, and "fully linear history" (release PRs still land as merge commits).

**How to split the work: Track 0 plus six epics**

| | Epic | Size | Start |
| --- | --- | --- | --- |
| T0 | Ship 0.18.0 (existing `sase-1mk`) | — | in flight |
| E1 | Keep sase and its plugins installable (old core versions kept as needed, no unpublished minimum versions, daily install check) | M | now |
| E2 | Exact-candidate release train plus coordinator, released in lockstep with the core | L | now |
| E3 | Trustworthy CI (one limited rerun, quarantine that doesn't block, finding the culprit commit) | M–L | now |
| E4 | Revert-first after a bad commit lands (propose first, automatic later) | M | after E3's rerun and culprit phases |
| E5 | Queue-aware landing as a product feature, proven on a test repo | XL | once E1–E3 are moving |
| E6 | Switch `sase/master` to the queue | M | after E3, E4, E5, plus a go/no-go review |

This is cld's six-epic shape rather than the plan's four. Four would delay the release coordinator until after the queue switch, and bundle a small, urgent install fix with a large redesign.

**Next 24 hours:** the `sase-core-rs` 0.42.0 release was running when I checked (about 16:05Z). If it can land before PR #299 merges, a three-line `publish.yml` fix (check out release-please's `sha` output) makes the 0.18.0 files come from the release commit. Without it, the publish job builds whatever was latest on `master` when it ran. If the fix can't land in time, trigger Publish immediately after the merge and check the PyPI files against `v0.18.0`.

**Not verified:** whether `release-please-action@v5` supports the `force-tag-creation` setting the plan relies on (the option exists in release-please itself), and whether merged commits keep the tested commit's ID under rebase. Both need a quick test on a throwaway repo before the epics depend on them. My final layout matches the requested structure; I left the moved reports' relative links unchanged rather than editing their contents.
