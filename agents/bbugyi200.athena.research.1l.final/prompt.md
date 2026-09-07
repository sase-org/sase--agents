%id(final, clan=research.1l) %m:@xlarge
%wait:research.1l.cdx %wait:research.1l.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to add support for integrating an LLM provider's usage
metrics into sase.

- In particular, users that are using their subscription instead of the API for the
  given provider are interested in how much usage they have remaining until they hit a
  limit.
- We should support this in a generic fashion that allows us to easily add support for
  any new LLM provider that might get added to sase in the future.
- We may eventually integrate input/output token usage, billing data, and other
  statistics for API users as well but this will not be a part of our initial solution.
- To start I was planning on implementing this for only the Claude provider, the Codex
  provider, and the Grok provider.
- I currently need to use the following URLs to check my usage limits manually. It would
  be much easier if they were shown in the TUI directly somewhere:
  - https://claude.ai/new#settings/usage
  - https://chatgpt.com/codex/cloud/settings/analytics#usage
  - https://grok.com/?checkout=success&tier=SUBSCRIPTION_TIER_GROK_PRO&interval=monthly&revenue=30&currency=USD&_s=usage

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about how to reliably fetch the current user's remaining usage before
hitting a limit for each of the three providers we intend to support at first. End your
analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1l.cdx` and
   `research.1l.cld` dependencies, matching by `wait_name` and the canonical research
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