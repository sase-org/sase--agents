- **AGENTS:**
  - [bbugyi200.apollo.research.4.cdx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.4.cdx/README.md)

%clan(research.4, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've recently
decided that our visual screenshot test suite is far too much work to enforce (i.e.
expect every sase agent to keep the screenshots they change up-to-date). I want to keep
the screenshot tests around, but as a new `just fix-tui-screenshots` lint command
instead of the `just test-visual` test command.

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
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.4.cdx %m:@sol_or_grok %q(w=0.25) #gh:gh_sase-org**sase You are researcher A
in a two-researcher swarm. The other researcher, `research.4.cld`, is independently
investigating the same request and will write its own self-named report ending in
`**b.md`. Your report will end in `__a.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I've recently decided that our visual screenshot test suite is far too much work to
enforce (i.e. expect every sase agent to keep the screenshots they change up-to-date). I
want to keep the screenshot tests around, but as a new `just fix-tui-screenshots` lint
command instead of the `just test-visual` test command.

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
#research(suffix=a)
