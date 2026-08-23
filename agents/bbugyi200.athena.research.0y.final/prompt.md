%id(final, clan=research.0y) %m:@research_lead
%wait:research.0y.cdx %wait:research.0y.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to migrate the sase/memory/task_types.md memory file
to a finalizer that is only active for sase managed projects.

- This finalizer, like all finalizers, should be configurable via a Project Local sase
  config field, which should be added to sase-managed projects by the `sase init`
  command automatically (e.g. `use: builtin@tasks` will be added).
- The goal is to move all of this text out of agent instruction files (to keep
  short-term memory as focused as possible) and only prompt agents to think about
  whether they need to create task beads or not at the very end of the turn.
- I will soon migrate this text to a memory file, once I add a new memory file type.
  This is upcoming work I still need to research, but something you may want to keep in
  mind when thinking about this text.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0y.cdx` -> `__a`, `research.0y.cld` -> `__b`), then read both reports.
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