%id(final, clan=research.0t) %wait(priority=20) %m:@research_lead
%wait:research.0t.cdx %wait:research.0t.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to investigate and close out all of the remaining open sase feature flags, which represent deprecations and/or new features (some of which have been enabled already and others which are off by default). I already have some agents working on the `artifact_links` and `pluggable_finalizers` feature flags, so those are being handled. Can you do some research with the goal of helping me understand what needs to be done to get rid of the rest of the feature flags? End your analysis with a list of next steps associated with each open feature flag (except for the two that are already being worked). Keep your report concise and practical.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0t.cdx` -> `__a`, `research.0t.cld` -> `__b`), then read both reports.
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