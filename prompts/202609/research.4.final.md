- **AGENTS:**
  - [bbugyi200.apollo.research.4.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.4.final/README.md)

%id(final, clan=research.4) %m:claude-fable-5 %wait:research.4.cdx %wait:research.4.cld
%q(w=0.25) #gh:gh_sase-org__sase You are the lead researcher: two independent
researchers have reported on the request below, and you will add your own research and
merge all three perspectives into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.4.cdx` and `research.4.cld`
   dependencies, matching by `wait_name` and the canonical research label's existing
   `__a.md`/`__b.md` suffix. Never reassign `__a`/`__b` from list order. Open the
   research repo with `/sase_repo`, then read each report through its canonical research
   reference (or the `ref` field's `file:<id>` reference if the original has moved)
   using `sase artifact read`. Do not read predecessor chat transcripts. If the records
   above do not identify exactly one A report and one B report, stop and report the
   missing or ambiguous input instead of guessing.
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
