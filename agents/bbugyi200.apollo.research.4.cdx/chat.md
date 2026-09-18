# Chat History - ace-run (research.4.cdx)

- **TIMESTAMP:** 2026-09-18 07:18:49 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.4.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260918_070414.md`

## Prompt

%clan(research.4, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I've recently decided that our
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
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.4.cdx
%m:@sol_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher A in a two-researcher swarm. The other researcher,
`research.4.cld`, is independently investigating the same request and will write its
own self-named report ending in `__b.md`. Your report will end in `__a.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

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
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__a` suffix, i.e. `<stem>__a.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I’m using the SASE repository, reference-memory, artifact, and finalization skills because this work crosses into the research sidecar, evaluates the TUI/verification workflow, and must end as a registered durable artifact. I’ll inspect the current task wiring and screenshot implementation, independently verify relevant snapshot-testing practices, then write and register only my `__a.md` report.

The governing notes confirm two important constraints: visual goldens currently use exact local pixel equality with a small CI-only drift tolerance, and `check-full` is intentionally the exhaustive landing/CI lane. I’m now tracing the exact `just`, pytest, renderer, cache-artifact, and CI paths so the recommendation can identify a low-risk migration rather than merely rename a recipe.

The implementation evidence is unusually strong: the corpus is currently 704 PNGs (~80 MiB) across 159 visual test modules, with about 607 snapshot assertion sites. Since 2026-07-01, 710 commits touched snapshot PNGs (14,914 file touches; median 3, 90th percentile 26, maximum 623). That validates the maintenance concern—but also shows why silently accepting every mismatch inside `check-full` would be risky. I’m shaping the recommendation around transactional generation, an explicit CI check mode, orphan detection, and reviewable aggregate output.

The report is written and Markdown-formatted. Its central recommendation is a deliberate adjustment to the request: the updater remains one command, but `check-full` and CI invoke `--check` so verification cannot silently approve regressions. The mutating path stages the complete corpus transactionally, reports additions/updates/stale removals with pixel statistics, and applies only after every scene renders successfully. I’m registering that exact file as the requested durable snapshot now.

Research complete and registered successfully.

- Report: [tui_screenshot_lint_workflow__a.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202609/tui_screenshot_lint_workflow__a.md)
- Artifact: `file:explicit:4e36108eb34b8921a15f0986`

Main recommendation: implement a transactional `just fix-tui-screenshots` updater, but have `check-full` and CI invoke it with `--check`. This prevents verification from silently approving visual regressions while still providing automatic creation, updating, stale-golden removal, and detailed change reports when agents run the fixer explicitly.
