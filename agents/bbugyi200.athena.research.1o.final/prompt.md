%id(final, clan=research.1o) %m:@xlarge
%wait:research.1o.cdx %wait:research.1o.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Artifact link files frequently cause merge conflicts that
sase agents need to resolve.

- See the `research.1n.cdx` sase agent for an example of one such agent (i.e. an agent
  that had to resolve an artifact link merge conflict).
- These link files are created frequently so these merge conflicts should ideally never
  happen.
- We've already done a considerable amount of work to make bead conflicts infrequent so
  you MAY be able to take inspiration from that.

Can you do some research with the goal of helping me decide the best way to implement
this (make artifact link conflicts nearly impossible--if not completely impossible)? End
your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1o.cdx` and
   `research.1o.cld` dependencies, matching by `wait_name` and the canonical research
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