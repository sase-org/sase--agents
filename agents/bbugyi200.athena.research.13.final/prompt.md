%id(final, clan=research.13) %m:@research_lead
%wait:research.13.cdx %wait:research.13.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

Sase seems to have support for three different installation
modes for plug-ins:

1. the published version of the python package
2. the dev version, which uses an editable local install
3. a "from git" option

I don't understand why the third option ("from git") is necessary since we can always
use the second option (dev/editable install) instead, right? The bugyi-chops plugin
which is installed on this machine, for example, uses a "from git" installation and I
would like to migrate this installation to use a dev/editable install instead.

Can you do some research with the goal of helping me understand what it would take to
remove support for "from git" sase plugin installations? End your analysis with a
recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.13.cdx` -> `__a`, `research.13.cld` -> `__b`), then read both reports.
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