# Chat History - ace-run (94--plan)

- **TIMESTAMP:** 2026-10-19 17:00:34 EDT
- **MODEL:** claude/opus
- **AGENT:** 94--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202610/gh_sase_org__sase-ace_run-94__plan-261019_164938.md`
- 2. --code — `~/.sase/chats/202610/gh_sase_org__sase-ace_run-94__code-261019_164938.md`

**Plan:** /home/bryan/.sase/plans/202610/research_swarm_figure_references.md


## Prompt

#gh:gh_sase-org__sase Can you help me instruct the linker agent in the `#research_swarm` macro swarm to
add a thoughtful sentence that links (using a local link) to any mermaid diagram that
the linker agent adds to the final document (so every figure is referenced)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.

%m:@xlarge %auto

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202610/research_swarm_figure_references.md`

> # Plan: The research_swarm linker references every Mermaid figure it places
> ## Goal
> When `#research_swarm` runs with diagrams (`diagrams=true`, or `image=true` without
> `diagrams=false`), the linker agent places the image agent's validated Mermaid diagrams
> into the published `<name>.md`. Today the placed figures cannot be linked to and nothing
> in the text points at them. After this change, every figure the linker places:
> 1. carries a stable in-document anchor, `figure-<id>`; and
> 2. is introduced by one thoughtful sentence, written by the linker, that links to it
>    with a local link (`[the publication-order diagram](#figure-publication-order)`) and
>    tells the reader what to look for in it.

*See full plan file for details.*

