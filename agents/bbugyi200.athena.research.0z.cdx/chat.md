# Chat History - ace-run (research.0z.cdx)

- **TIMESTAMP:** 2026-08-24 07:23:12 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0z.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_070932.md`

## Prompt

%clan(research.0z, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I've been toying around with a way to generalize sase's
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
cases (i.e. What other memory web notes might I or someone else create in the future?).]]) %id:research.0z.cdx
%model:@research_a 
#gh:gh_sase-org__sase I've been toying around with a way to generalize sase's
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
cases (i.e. What other memory web notes might I or someone else create in the future?). Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m treating this as design research, not yet an implementation. I’ll examine the current glossary/memory machinery and both migrations, compare the model against Zettelkasten/ADR precedents, then write a cited recommendation into the research repository.

I’m using the SASE repository skill because `bob-cli` and the research store are separate repositories, and the audited memory-read workflow because the destination is a SASE research artifact.

The existing rules already expose two design constraints worth preserving: memory reads are audited, and CLI help/argument design is part of the public contract. I’m now tracing how glossary source files merge across home/project scopes and how they are rendered, since that inheritance behavior is the part most likely to become subtly wrong in a generalized model.

A first architectural tension is clear: the proposal is not only a storage migration. Glossary behavior currently spans Rust validation/matching, Python CLI/audit/reporting, generated instructions, LSP navigation, and a substantial ACE panel. The report will distinguish the generic “web/strand” substrate from glossary-only affordances so the migration doesn’t either regress those features or force every future web to pretend it is a glossary.

The external evidence supports the shape, with one important correction. Small addressable notes plus a hub/index are a sound fit, and ADR collections are almost a textbook second use case. But a directory alone is not a “web”; stable identities and explicit or policy-driven links must be part of the model. I’m drafting the recommendation around that distinction, plus a staged compatibility path for the current glossary UX.

The draft is complete. Its recommendation is to proceed, while separating delivery class from note shape, using stable strand slugs, shadowing whole webs across project/home scope, and keeping glossary phrase semantics opt-in. It also recommends “reference memory” over “structured memory” because the latter does not describe the actual load-on-demand behavior; the report includes a clean fallback if you prefer to retain “structured.”

The report is formatted, passes `git diff --check` and Prettier validation, and has been registered as an immutable SASE artifact. I’m now submitting the required SASE final declaration; I won’t make further repository changes after it.

Completed the research report: [Memory Webs and Strands](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202608/memory_webs.md).

Main conclusion: proceed with memory webs, but model `core/reference` as the loading axis and `note/web/strand` as the content-shape axis. The report recommends “reference memory” over “structured memory,” while accommodating either choice.

It includes:

- Proposed frontmatter and selector schemas
- Home/project precedence rules
- Glossary and `bob-cli` migration strategy
- ADR design
- CLI, auditing, Rust/Python boundaries, LSP, and ACE implications
- Phased implementation and testing plan
- Additional web use cases

Formatting and diff checks pass. Artifact: `file:explicit:49e682ce9b8662641ec2bbd6`.
