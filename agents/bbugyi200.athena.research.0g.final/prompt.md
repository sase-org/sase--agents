%id(final, clan=research.0g) %wait(priority=20) %m:@research_lead
%wait:research.0g.cdx %wait:research.0g.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I would like to merge the functionality of sase monitors (see
the sase-kp epic bead) with sase procs (see the sase-lh epic bead) by adding support for
a new type of detatched proc that we will call "named procs" (aka "sase shells") that
will be powered by the `sase proc` command under-the-hood, but that is wrapped by a new
`sase shell` command (that more-or-less takes the place of the `sase monitor` command,
which should be removed).

Can you do some research with the goal of helping me decide the best way to implement
this? See the detached_proc_convergence.md file in the research sidecar repo for some
related research you should maybe know about. End your analysis with a recommended
solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0g.cdx` -> `__a`, `research.0g.cld` -> `__b`), then read both reports.
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