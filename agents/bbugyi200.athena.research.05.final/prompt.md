%id(final, clan=research.05) %wait(priority=20) %m:@research_lead
%wait:research.05.cdx %wait:research.05.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to start creating a corresponding bead for every
external bug (e.g. GitHub issue--but this should use our plugin system I think) created
for sase projects that are enabled on the given machine (I'm assuming we will use one or
more chops for this, but I am open to suggestions).

- I also want to do the same thing for Patches (i.e. create a new patch for each PR on
  enabled projects that was not created by a sase agent).
- I then want to merge the "Beads" and "Bugs" sub-tabs on the "Artifacts" tab in an
  elegant way that displays only beads but makes it very clear which beads are
  associated with bugs (and provides useful operations for editing/viewing those bugs).
- Again, we should do something similar for patches: Rename the "PRs" sub-tab of the
  "Artifacts" tab to "Patches" and start making it clear which Patches have PRs that
  were created externally associated with them. Keep in mind that, in the case of
  patches, sase agents do something create PRs and associate them with patches (so the
  existnce of a corresponding PR does not mean that the Patch was triggered by an
  external PR).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.05.cdx` -> `__a`, `research.05.cld` -> `__b`), then read both reports.
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