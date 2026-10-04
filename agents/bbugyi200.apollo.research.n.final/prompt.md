%clan(research.n, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want all users
working on a sase project to have access to all (non-sensitive) bead attachments by
default.

- Review the attachment_storage_and_access.md file in the research sidecar repo and the
  sase-1ck epic bead for context before performing your research.
- I plan on launching another epic after the sase-1ck epic bead is closed to make these
  changes.
- I think we can implement this by moving non-sensitive attachments from the
  sase--attachments sidecar repo to the public sase--beads repo.
- It's fine if large files are only ever supported via sase's remote machine support.
- I'm not sure how we should identify whether or not a file is sensitive or not. I'm
  thinking that agents should have the ability to specify that an attachment be private
  somehow, but they should default to using public attachments. I'm not sure how they
  should decide when to use a private attachment though.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.n.final %m:@xlarge
%wait:research.n.cdx %wait:research.n.cld %wait:research.n.grk %wait:research.n.mus %wait:research.n.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want all users
working on a sase project to have access to all (non-sensitive) bead attachments by
default.

- Review the attachment_storage_and_access.md file in the research sidecar repo and the
  sase-1ck epic bead for context before performing your research.
- I plan on launching another epic after the sase-1ck epic bead is closed to make these
  changes.
- I think we can implement this by moving non-sensitive attachments from the
  sase--attachments sidecar repo to the public sase--beads repo.
- It's fine if large files are only ever supported via sase's remote machine support.
- I'm not sure how we should identify whether or not a file is sensitive or not. I'm
  thinking that agents should have the ability to specify that an attachment be private
  somehow, but they should default to using public attachments. I'm not sure how they
  should decide when to use a private attachment though.

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
   dispatch's `research.n.cdx`, `research.n.cld`, `research.n.grk`, `research.n.mus`, `research.n.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```