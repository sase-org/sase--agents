- **AGENTS:**
  - [bbugyi200.athena.research.1b.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1b.final/README.md)

%id(final, clan=research.1b) %m:@research_lead %wait:research.1b.cdx
%wait:research.1b.cld #gh:gh_sase-org__sase You are the lead researcher: two
independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The TUI is incredibly slow recently. Can you help me do some research by digging into
sase's logs to figure out where these performance problems are coming from and what we
could do to significantly improve the `sase ace` TUI's performance? End your analysis
with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1b.cdx` -> `__a`, `research.1b.cld` -> `__b`), then read both reports.
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
