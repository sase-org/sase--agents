%name:research.@.final %m:@research_lead %wait:research.c.cdx %wait:research.c.cld %g:research
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I wanna unify agent families so users can more easily conceptualize them as just a different way of grouping agents on the agents tab. Can you do some research to help me understand what conceptual barriers I'm going to need to design around in order to make this happen? Keep in mind that part of the goal is to migrate as much functionality from xprompt workflows (Yas possible to xprompt swarms (markdown files). For example:

- I know that I will need to allow agents in the same family to run in parallel. I plan on adding support for a new `wait=<bool>` keyword argument to the `%name` directive for this.
- I know that Python and Bash xprompt workflow steps will need to be allowed to be root agent rows in order to support, for example, defining an xprompt swarm that requires a command to be run that updates the software you are working on (e.g. sase) before one or more agents (e.g. to verify the work) can run. Moreover, this is just needed to make them definable in xprompt swarms I think, which would be preferable to xprompt workflows.

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