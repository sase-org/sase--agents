#gh:gh_sase-org__sase I've been toying around with a way to generalize sase's glossary into a new
type of sase memory and I think I've got it. Can you help me implement this?

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
  specified by memory strand files (we currently call these "terms" in the case of the
  glossary, for example).
- If the `sase memory read <web>` command is used without providing any `<keyword>`,
  then all of the strands in that web should be displayed.
- As far as other use cases go, besides the glossary, I was thinking that architecture
  decision records (ADRs) might be a good 2nd use-case (using a
  sase/memory/webs/decisions/ web).
- Review the glossary_to_memory_webs.md file in the research sidecar repo before
  planning for context and inspiration. Keep the following notes in mind while reading
  this research file:
  - Dropping the `webs/` part of the path sounds good to me.
  - Using the term "reference memory" instead of "structured memory" sounds good to me.
  - It's fine for us to use a beta feature flag if needed to protect users from breaking
    changes while the feature is still being implemented, but I want this feature fully
    rolled out (i.e. remove this feature flag and close the corresponding flag bead)
    before this epic lands.
  - We can implement the decision web as a trial but it should be a core web instead of
    a reference web (reference webs will have no implemented use cases at first but I
    may migrate the decision web to a reference web in the future). Two agents recently
    did some research on what decision records we should consider adding to this web.
    Select the five best ones using your best judgment and add them. Also, add a 6th
    decision record dedicated to memory webs (this feature). Make sure these decision
    records have excellent names, keywords, aliases (if you think some are helpful), and
    contents but are also concise (remember that every token in context either helps or
    hurts us).
  - It is important that we migrate the sase/memory/task_types.md memory to a core web
    in v1, if possible. Can we implement this by having the plugin registry control what
    task_types web/strand memory files get created by the `sase init` command? If not,
    think hard about the most appropriate way to implement this.
  - No other webs should be created yet (just the existing "glossary" and "task_types"
    webs and the new "decisions" web).
- #beau

#plan #m_opus