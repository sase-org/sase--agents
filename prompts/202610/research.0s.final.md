- **AGENTS:**
  - [bbugyi200.apollo.research.0s.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0s.final/README.md)

%clan(research.0s, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I am going to
apply to one or two NYC DataBricks roles and I would like you to help me design a CV
specifically for this/these role(s).

- See the databricks_omnigent_job_fit.md file in the research sidecar repo for context.
- This CV should be modeled off of my existing CV in my bbugyi200/CV GitHub repo and
  should be committed to that repo.
- I left Google in May, but I haven't updated my LinkedIn or CV yet, so you should do
  that (or, in the case of LinkedIn, give me guidance on what needs to be done). During
  my 6 monthes unemployed I have been working on sase fulltime. I am currently working
  on releasing a blog post to http://sase.sh (it should be done within the next week or
  two) before I start my looking for a new role, but was so excited to hear about
  Omnigent that I figured I would try applying to DataBricks.
- I would also like to create a short pitch for each role that you think I should apply
  for (make sure I'm really qualified for each).

Can you do some research with the goal of helping me with all of this?]])
%id:research.0s.final %m:@xlarge %wait:research.0s.cdx %wait:research.0s.cld
%wait:research.0s.grk %wait:research.0s.mus %wait:research.0s.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are the lead researcher: 5 independent researchers have
reported on the request below, and you will add your own research and merge every
perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I am going to apply to one or two NYC DataBricks roles and I would like you to help me
design a CV specifically for this/these role(s).

- See the databricks_omnigent_job_fit.md file in the research sidecar repo for context.
- This CV should be modeled off of my existing CV in my bbugyi200/CV GitHub repo and
  should be committed to that repo.
- I left Google in May, but I haven't updated my LinkedIn or CV yet, so you should do
  that (or, in the case of LinkedIn, give me guidance on what needs to be done). During
  my 6 monthes unemployed I have been working on sase fulltime. I am currently working
  on releasing a blog post to http://sase.sh (it should be done within the next week or
  two) before I start my looking for a new role, but was so excited to hear about
  Omnigent that I figured I would try applying to DataBricks.
- I would also like to create a short pitch for each role that you think I should apply
  for (make sure I'm really qualified for each).

Can you do some research with the goal of helping me with all of this?

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, grk, mus, gem, belonging to this dispatch's `research.0s.cdx`,
   `research.0s.cld`, `research.0s.grk`, `research.0s.mus`, `research.0s.gem`
   dependencies, matching by `wait_name` and the canonical research label's existing
   `__<suffix>.md` suffix. Never reassign suffixes from list order. Open the research
   repo with `/sase_repo`, then read each report through its canonical research
   reference (or the `ref` field's `file:<id>` reference if the original has moved)
   using `sase artifact read`. Do not read predecessor chat transcripts. If the records
   above do not identify exactly one report per expected suffix, stop and report the
   missing or ambiguous input instead of guessing.
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
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest
   findings from every report above and your own research, resolve conflicts, cut
   duplication, and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker agent
   `research.0s.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0s.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l
   "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails, report
   that failure; do not report the task as fully complete.

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
