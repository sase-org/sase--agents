# Chat History - ace-run (research.4.cld)

- **TIMESTAMP:** 2026-09-18 07:24:31 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260918_070414.md`

## Prompt

%id(cld, clan=research.4) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.4.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

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
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

Now let me look at the justfile and the visual test infrastructure.

I'm reading how the visual snapshot suite is wired into the Justfile, CI, and the pytest harness before I write the report.

Now checking PNG churn in git history and how agents are currently told to handle snapshots.

Full CI has been red on every scheduled run for about a week. I'm checking whether the visual job is the cause.

`visual-test` failed in all 60 of the last 60 Full CI runs, going back to 2026-09-05. Next I'm checking what those failures actually are: stale goldens, flakes, or environment skew.

Almost done gathering evidence: checking orphan-golden handling, the existing failure-report tool, and whether SVG/text goldens would be deterministic.

Measuring what share of the repo's git history the PNG blobs take up, for the cost section.

Last data point: comparing CI job durations to size the check-full cost.

I have enough evidence. Before writing into the research sidecar repo, I'll check the repo-access rules.

The printed path matches the requested directory, and my filename is free. One quick tally of per-job failure counts across the 60 Full CI runs for context:

Writing the report now.

Verifying one claim in the report (the Rich SVG class-prefix hashing) before registering it.

Confirmed. Now registering the report as an artifact.

Registration succeeded. Now the final declaration.

I've written the report and registered it. My bottom line: your plan is the right shape, but on its own it won't keep master's screenshots fresh. The missing piece is a scheduled bot that regenerates the goldens on master.

**What the data shows**
- **The gate has already stopped working.** `visual-test` failed in all 60 of the last 60 Full CI runs (2026-09-05 to 2026-09-18). The latest run had 105 failures and 855 passes, and nearly all the failures were the same ~2,750-pixel change repeated across ~100 screens. They're stale goldens, not flaky tests.
- **One chrome change rewrites almost everything.** 587 of the 674 goldens are full 120×40 screens, so any header or footer change touches hundreds of them. Six commits in the last 30 days each rewrote 340–623 PNGs, and at least 21 commits were pure "rebaseline/repair" work.
- **Agents invalidate each other's updates.** About 56 commits land per day. The `sase-126` epic repaired a golden that a concurrent change broke again within hours. Making the update cheaper doesn't fix that; something has to run after landing.
- **Git history cost.** Golden PNGs take ~1.6 GB of the repo's ~2.2 GB on-disk history, with ~550 MB added in the last 30 days. Auto-updating will speed this up, and re-encoding the PNGs doesn't shrink them.
- **Runtime cost.** The visual job takes 13.5 min against 35.8 min for the whole fast suite on the same CI runner. Running it on every `check-full` would make that command ~35–40% more expensive.

**What I'd change (each marked [ADJ] in the report)**
- **Split the command in two:**
  - `just fix-tui-screenshots` writes goldens.
  - `just lint-tui-screenshots` only checks, and CI calls it.
  - The fixer also refuses to write when it detects it's running under GitHub Actions.
- **Don't file it under "lint".** Otherwise it's likely to end up in `just lint`, which would put a 13-minute visual run into `just check` and every master push.
- **In `check-full`, run it only when the diff touches TUI rendering files.** Print its report after the stage, because `run_silent` hides output from stages that pass.
- **`just check` prints a one-line reminder** when TUI rendering files change, instead of relying on agents to remember.
- **Stricter fixer behavior:**
  - Test errors and captures that differ between two runs still fail.
  - Byte-different but pixel-identical captures aren't rewritten.
  - Goldens whose test was removed or renamed get deleted.
  - The report groups identical changes, so 600 matching header diffs show up as one line. It also includes a single contact-sheet image agents can open.
- **Add a backstop:** a scheduled GitHub Actions job that regenerates the goldens and pushes a commit containing only PNGs, with the change report as the message. It fixes staleness within a few hours and uses no capacity on your host. **Decision for you:** are you comfortable with a bot committing directly to master? The fallback is a PR with auto-merge.

**Recommended rollout:** one epic with four phases — the fixer itself, agent integration, the bot backstop, and a rule for resolving golden-only rebase conflicts. A follow-up epic would crop most snapshots to the component under test and add a small text dump per snapshot, so git diffs say what text actually changed.

Two limits:
- I didn't run the visual suite locally, because the host was heavily loaded; the runtimes above come from CI.
- The descriptions of how Jest, insta and pytest-textual-snapshot handle updates are from memory, not re-checked this session.

Full CI also fails for many non-visual reasons, so fixing the screenshots alone won't turn it green.

Artifact ref: `file:explicit:5c118e5f30db1cd5e37efe4f`, label `research:202609/tui_screenshot_fixer_command__b.md`. The commit into the research repo has been handed to the host.

Report: `sase/repos/research/202609/tui_screenshot_fixer_command__b.md`
