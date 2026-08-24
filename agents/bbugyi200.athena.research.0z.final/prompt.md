%id(final, clan=research.0z) %m:@research_lead
%wait:research.0z.cdx %wait:research.0z.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I've been toying around with a way to generalize sase's
glossary into a new type of sase memory and I think I've got it.

- To start, some naming changes. We should make sure to update all relevant references:
  - short-term memory will now be called "core memory".
  - long-term memory will now be called "structured memory".
- We will add two new types of memory that are not represented as tiers (i.e. we will
  stick with using just the "Tier 1" and "Tier 2" H2 sections in agent instruction
  files):
  1. "memory strands": These are small memory notes inspired by zettel in a
     zettelkasten. These notes will be stored in files of the form
     `sase/memory/webs/<web>/<name>.md`, where `<web>` is the name of the web that the
     strand lives in and `<name>` is the name of the strand.
  2. "memory webs": These are inspired by hub notes in a zettelkasten. They should be
     defined in files of the form `sase/memory/webs/<web>.md` that correspond with an
     existing `sase/memory/webs/<web>/` directory.
- Memory webs should be configured by users by adding the appropriate sase/memory/ files
  to the machine's home directory or to project directories. This project and the
  bob-cli project should have their sase/sase.yml glossary configurations migrated to
  use this structure (i.e. create a new "glossary" web that is presented as a core
  memory--see the next bullet).
- A memory web should be presented to agents in agent instruction files as either core
  memories or strucured memories (one per memory web). Users should be able to configure
  whether a web is rendered as a core memory (like the glossary web should be) or a
  structured memory via the frontmatter of the `sase/memory/webs/<web>.md` file
  corresponding with that web.
- The `sase glossary` command would be migrated to the
  `sase memory read <web>:<keyword> [<web>:<keyword> [...]]` command where `<web>` is
  the name of a web and `<keyword>` is a repeatable argument that takes keywords
  specified by memory strand files (for example, we currently call these "terms" in the
  case of the glossary).
- If the `sase memory read <web>` command is used without providing any `<keyword>`,
  then all of the strands in that web should be displayed.
- As far as other use cases go, besides the glossary, I was thinking that architecture
  decision records (ADRs) might be a good 2nd use-case (using a
  sase/memory/webs/decisions/ web).

Can you do some research with the goal of critiquing this idea and, if you think I
should proceed, helping me decide the best way to implement this? Flesh out any open
questions that remain, but do your best to answer them on your own. End your analysis
with a recommended solution and, if you like the idea, some additional potential use
cases (i.e. What other memory web notes might I or someone else create in the future?).

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0z.cdx` -> `__a`, `research.0z.cld` -> `__b`), then read both reports.
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