%id(final, clan=research.0f) %wait(priority=20) %m:@research_lead
%wait:research.0f.cdx %wait:research.0f.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

Sase procs, which are currently called "tasks" but will soon
be renamed to "procs" (see the sase-lh epic bead) currently support processes that are
attached to the TUI and ones that are detatched. I would like to change this and migrate
all of the current procs that attach to a TUI to detached procs (we would then remove
the `sase task run` command's `-d|--detatched` option). I think the problem with this is
that the procs that attach to a TUI do not necessarily have a command associated with
them, which should be required for a detached proc (verify this is true).

Can you help me do some research into what it would take to migrate every existing proc
that attaches to a TUI to a detached proc by creating an associated command, if
necessary for that proc? (Maybe a `sase` sub-command or sub-sub-command? Think hard
about where this command should live.)

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0f.cdx` -> `__a`, `research.0f.cld` -> `__b`), then read both reports.
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