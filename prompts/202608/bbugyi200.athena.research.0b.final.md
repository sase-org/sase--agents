- **AGENTS:**
  - [bbugyi200.athena.research.0b.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0b.final/README.md)

%id(final, clan=research.0b) %wait(priority=20) %m:@research_lead %wait:research.0b.cdx
%wait:research.0b.cld #gh:gh_sase-org__sase You are the lead researcher: two
independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I recently made some improvements to the "Artifacts" tab (see the sase-js epic bead for
context) and would like to continue improving these sub-tabs by adding new
functionality. Before doing that however, I think it's a good idea to try to unify these
sub-tabs as much as possible by providing a similar interface for each for users and a
practical contract for artifact ref type designers to follow to make sure new sidecar
repo tabs follow the same standard. Can you do some research with the goal of helping me
decide the best way to implement this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0b.cdx` -> `__a`, `research.0b.cld` -> `__b`), then read both reports.
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
