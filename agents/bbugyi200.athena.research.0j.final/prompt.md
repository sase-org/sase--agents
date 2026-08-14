%id(final, clan=research.0j) %wait(priority=20) %m:@research_lead
%wait:research.0j.cdx %wait:research.0j.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to unify the different Artifacts tabs with the goal of
using an API / contract of some sort to allow specific sidecar/artifact repos to specify
how their corresponding tabs behave. This will also make adding new functionality more
rewarding in the future (if we get the abstraction right), since all custom sidecar
repos (even ones that are configured for other users that we don't know about) get new
functionality for the cost of a single implementation.

- See the artifacts_pane_contract.md file in the research sidecar repo for related
  research / inspiration (keep in mind this file is a bit dated since some of the
  requirements this agent was given were not quite right/complete and I ran this agent a
  few days ago--related changes have been made since then).
- I do want the "Patch" sub-tab to be included in this unification, with the goal of
  migrating this tab over to the same look and feel as the other sub-tabs.
- Before we do this, however, I would like to figure out how to generalize some of the
  "Patch" tab's coolest features (powerful search syntax, saved queries,
  ancestors/children jumpers, etc...) so they can be included in the contract.

Can you do some reasearch to help me decide the best way to implement this based on the
requirements and notes listed above?

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0j.cdx` -> `__a`, `research.0j.cld` -> `__b`), then read both reports.
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