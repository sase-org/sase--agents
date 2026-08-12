- **AGENTS:**
  - [bbugyi200.athena.research.0a.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0a.final/README.md)

%id(final, clan=research.0a) %wait(priority=20) %m:@research_lead %wait:research.0a.cdx
%wait:research.0a.cld #gh:gh_sase-org__sase You are the lead researcher: two
independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

The `sase ace` TUI's startup time has gotten progressively worse lately (it regularly
takes >5s to finish starting up). Can you do some research with the goal of helping me
reduce this start-up time? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0a.cdx` -> `__a`, `research.0a.cld` -> `__b`), then read both reports.
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
