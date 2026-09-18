# Chat History - ace-run (research.4.final)

- **TIMESTAMP:** 2026-09-18 07:38:45 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.4.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260918_070414.md`

## Prompt

%id(final, clan=research.4) %m:claude-fable-5
%wait:research.4.cdx %wait:research.4.cld %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've recently decided that our
visual screenshot test suite is far too much work to enforce (i.e. expect every sase
agent to keep the screenshots they change up-to-date). I want to keep the screenshot
tests around, but as a new `just fix-tui-screenshots` lint command instead of the
`just test-visual` test command.

- This new command should not run when the `just fix` command runs. Instead, we should
  only run this command when the `just check-full` command is run or when a sase agent
  runs this command explicitly (which it should be told to do when it expects that its
  file changes will trigger TUI screenshot updates and/or that agent added new
  screenshot tests).
- This command should automatically create new and/or update existing PNG files with
  good output that describes what changes were made.
- This command should be run in CI but should fail if any new PNG files / PNG file
  updates need to be made (instead of passing and auto-updating/auto-creating the PNG
  files like it should do when run by sase agents).

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

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.4.cdx` and
   `research.4.cld` dependencies, matching by `wait_name` and the canonical research
   label's existing `__a.md`/`__b.md` suffix. Never reassign `__a`/`__b` from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one A report and one B report, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports inside it as `<name>__a.md` and `<name>__b.md`, preserving each report's
   existing `__a`/`__b` suffix. Each report's `source_path` is provenance for where it
   lives in your own opened research checkout; resolve its canonical repo-relative path
   there before moving it. Never modify the other agents' checkouts or the stored
   snapshot recorded at `ref` — only the copy in your own checkout moves. Preserve both
   files and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by loading the skills I need: opening the research repo and reading SASE reference memory about the TUI screenshot tooling and lint/test conventions.

The research repo is open in my workspace. Now I'll read both registered reports through their canonical research references.

Full CI is indeed persistently red. Let me spot-check that `visual-test` specifically fails, and verify the shard-timings ratchet pattern B modeled on.

My verification is nearly complete. Two quick final checks: how `ci.yml` is triggered (PR vs. scheduled), and the finalizer rebase path B's binary-conflict concern rests on.

A prior bead `sase-sl` looks like the exact same defect. Let me confirm.

`sase-sl` is a READY memory task for exactly this defect (the paragraph since migrated into `lint_and_test.md`). I'll corroborate it with my independent verification instead of creating a duplicate.

Now I'll set up the consolidated report layout in my opened research checkout. First, check the month directory contents.

Both reports are present in my checkout. I'll use the stem `fix_tui_screenshots_command` (no collisions), create the directory, and move the reports in with their suffixes preserved.

Both reports are moved. Now I'll write the consolidated report, merging both researchers' findings with my own verification.

The final layout is in place. Let me verify the research repo's state before finalizing.

Layout is correct: both reports renamed with suffixes preserved, consolidated report alongside. Now I'll submit the final declaration.

The consolidated report is done. It lives at `sase/repos/research/202609/fix_tui_screenshots_command/fix_tui_screenshots_command.md`, with both source reports moved alongside it as `__a`/`__b`, and the commit is declared to the host finalizer.

**Bottom line:** the plan is a good idea, both researchers independently endorsed its core shape (auto-update locally, check-only in CI — the same model Jest, insta, and Playwright use), and my own verification confirmed the urgency: the visual gate has *already* failed. B measured `visual-test` red in 60 of 60 recent scheduled Full CI runs; I spot-checked the live run history and the per-job breakdown and it holds. The consolidated recommendation makes three adjustments to your stated requirements, each called out explicitly in the report:

1. **`just check-full` should run a non-mutating check twin, not the auto-updater.** This was the sharpest disagreement between the reports, and I sided firmly with A on repo-specific grounds: agents are required to run `check-full` through a background monitor, and host finalizers stage with `git add -A` — a mutating stage would commit hundreds of regenerated binaries that no agent ever inspected, destroying the one safeguard that makes auto-update tolerable. I kept B's cost mitigation: the stage is diff-gated on a TUI-impact predicate, since the lane costs ~13.5 minutes on a capacity-constrained host.
2. **Two recipes instead of one CI-sniffing command:** `fix-tui-screenshots` (writes) and `lint-tui-screenshots` (check twin), matching the repo's verified `fix-keep-sorted`/`lint-keep-sorted` convention. Also: don't call it a lint — B's warning that filing it under `just lint` would silently drag 13 minutes into the Master Gate is well taken.
3. **Add B's scheduled "screenshot ratchet"** — a GitHub Actions job that regenerates goldens on master and pushes a golden-only commit with a grouped change report as the body. This is the piece that actually fixes the problem: at ~56 commits/day, agents invalidate each other's goldens within hours, so only a post-landing mechanism keeps master fresh. One nuance I added from verification: the existing shard-timings ratchet pushes a *branch*, not master, so B's direct-push design needs your explicit sign-off (fallback: PR + auto-merge). This is the one decision only you can make.

The report also merges A's transactional collect-then-apply architecture with B's per-snapshot safety rules (never write non-deterministic captures or test errors, skip pixel-identical frames, group cascaded diffs so 600 identical footer changes read as one line), adds stale-golden deletion as a third drift kind, and ends with a phased rollout plus a follow-up epic on the real long-term fix: cropping the 587 full-screen goldens to components so chrome changes stop rewriting the whole 80 MB corpus (~0.5 GB/month of unmergeable history growth today).

Two side outcomes from my verification: I confirmed the current update flag is literally a blind `write_bytes` with no comparison or record (so both reports' case for a real change-reporting fixer is solid), and I found `lint_and_test.md`'s claim that CI uses a ratio tolerance is false — CI has always compared exact. That staleness was already tracked as ready bead `sase-sl`, which I corroborated with a +1 rather than filing a duplicate.
