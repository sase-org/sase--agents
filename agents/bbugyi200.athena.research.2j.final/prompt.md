%id(final, clan=research.2j)
%m:opus@xhigh
%wait:research.2j.cdx %wait:research.2j.cld %wait:research.2j.mus %wait:research.2j.gem %q(10, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about adding
support to agent data cards (see the sase-17d epic bead for context) for sub-cards,
which I will term "agent data card blocks" (aka "card blocks").

- These should work like decks in that they use a spread view by default and a paged
  view when the merged contents are past a configurable threshold.
- The user should be able to use new `<ctrl+shift+j/k>` keymaps to cycle through the
  currently selected card's blocks.
- Our first use-case for this functionality should be to split the "Main" deck's "Reply"
  card into several blocks (one per sase shell `AGENT CHAT` sub-section). The final card
  (i.e. the last agent's/monitor's/gate's output) should be shown first when this card
  is paged (i.e. viewed as a sequence of blocks). In other words, we should reverse the
  order of the card blocks for the "Reply" card (e.g. `<ctrl+shift+j>` should cycle to
  the 2nd to last sase shell's output block).
- #beau

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
   in cdx, cld, mus, gem, belonging to this
   dispatch's `research.2j.cdx`, `research.2j.cld`, `research.2j.mus`, `research.2j.gem` dependencies, matching by `wait_name` and the canonical research
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
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```