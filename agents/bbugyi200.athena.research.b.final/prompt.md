%name:research.@.final %m:@research_lead %wait:research.b.cdx %wait:research.b.cld %g:research
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I suspect that I am not using sase beads to their full potential. Can you do some research With the goal of recommending the most impactful practical improvements, I should consider making to sase beads? Do some research on how steveyegge's beads project has evolved on GitHub for inspiration (I've found this project to be a bit over-complex at times though, so don't let your research become over-reliant on what you think steveyegge would do). End your analysis with the most impactful / useful improvements you think I should consider making to sase beads.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase sdd path research --ensure)/$(date +%Y%m)

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