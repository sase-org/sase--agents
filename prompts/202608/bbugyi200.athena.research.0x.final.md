- **AGENTS:**
  - [bbugyi200.athena.research.0x.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0x.final/README.md)

%id(final, clan=research.0x) %m:@research_lead %wait:research.0x.cdx
%wait:research.0x.cld #gh:gh_sase-org__sase You are the lead researcher: two
independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I would like to implement a new `%if` directive that allows me to specify (in the
prompt) that agents should only only launch if a particular condition, specified by a
new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context
  and make sure this research either aligns with that research or that you reconcile any
  differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0x.cdx` -> `__a`, `research.0x.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
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
