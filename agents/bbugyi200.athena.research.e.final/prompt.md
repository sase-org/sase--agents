%name:research.@.final %m:@research_lead %wait:research.e.cdx %wait:research.e.cld %g:research
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I want to generalize the concept of plan / question /
launch notifications so all of them use the same structure and sase notification
constructor. We should use the existing `sase notify create` command for this,
which will need to be signifigantly enhanced I think. As a part of this change,
I intend to remove the (never used) dynamic `improve_plan` and `tester` family
member hooks (I'm not even sure how they work, but I'm pretty sure we will need
to do something about them to progress with this initiative).

Can you do some research to help me understand what this task entails? End your
analysis with a list of questions that, if answered correctly, would allow you
to confidently design and implement this functionality.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.@.cdx` -> `__a`, `research.@.cld`
   -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory, create `<month-dir>/<name>/`, and
   move the two reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never overwrite: on any
   collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings from both reports and your own
   research, resolve conflicts, cut duplication, and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```