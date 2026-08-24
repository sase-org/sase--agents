# Chat History - ace-run (research.11.cdx)

- **TIMESTAMP:** 2026-08-24 14:31:54 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.11.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_141250.md`

## Prompt

%clan(research.11, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to start making better use of sase's artifact links.
For one I have a strong feeling that we are not linking artifact files like plans and
research files consistently or in an ideal way. It would be nice if we could improve
this somehow without increasing the average agent's context too much (e.g. by telling
every agent to always look for ways they can create artifact links in agent instruction
files, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? While you're at it, do some research on how we can improve artifact links in
general and use them in the best way. End your analysis with a recommended solution.]]) %id:research.11.cdx
%model:@research_a 
#gh:gh_sase-org__sase I want to start making better use of sase's artifact links.
For one I have a strong feeling that we are not linking artifact files like plans and
research files consistently or in an ideal way. It would be nice if we could improve
this somehow without increasing the average agent's context too much (e.g. by telling
every agent to always look for ways they can create artifact links in agent instruction
files, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? While you're at it, do some research on how we can improve artifact links in
general and use them in the best way. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the SASE reference-memory workflow because this research directly concerns artifact references and link semantics. I’ll trace the current implementation, existing link-producing workflows, and tests, then write an evidence-backed recommendation in the requested research directory.

The governing model is clear: `cites` and `read` are automatic provenance, while only four semantic relations are intentionally author-written. I’m now looking for the actual choke points—plan/research creation, prompt expansion, audited reads, finalization, and rendering—so the recommendation can concentrate intelligence there instead of adding standing instructions to every agent.

The requested directory is a linked research sidecar repository, so I’m switching to the required SASE repo-opening workflow before reading or writing there. I’ll keep the core implementation analysis in this checkout and use only the resolved sidecar path for the report.

A first measurement already shows the adoption problem is real and uneven: the live graph has 137 edges, but 78 are audited reads, 41 are generic `related`, 17 are `derives-from`, and only one is a prompt `cites` edge; there are zero `implements` and zero `supersedes` edges. I’m quantifying document coverage and checking whether current UI/automation exposes enough semantic signal to make better linking self-reinforcing.

The low-context lever is likely workflow-scoped guidance or host-side proposal generation, not more core memory. Because that touches SASE’s generated agent skills, I’m consulting the generated-skill workflow before evaluating where link recommendations should live.

The current system already has three distinct relationship sources—domain-native associations, automatic provenance, and curated graph edges—but they are not consistently surfaced as such. I’m checking the Rust row semantics and external lineage standards next, especially how they avoid duplicating authoritative relationships or turning every read into a claimed dependency.

I’ve finished the system and workflow audit. The clearest pattern is that link quality follows workflow-specific guidance, while generic artifact-producing workflows lack it; I’m now turning that into a measured design recommendation with a zero-cost default path for agents that aren’t producing artifacts.

The measurements are decisive enough to avoid a generic “remember to link things” policy: among 603 August plans, only two recently-created plans have curated links, while scoped research workflows perform much better. I’m documenting a workflow-owned design that uses existing run evidence and asks for semantic judgment only when an artifact is actually produced.

The report is written and passes basic Markdown/diff checks. I’m now applying the report’s own standard to the report itself: recording only two specific `derives-from` links to the prior SASE research it materially synthesizes, rather than linking every artifact I inspected.

The link command correctly refused to leave its auto-generated sidecar commit only in this ephemeral checkout. I’m following its prescribed publish step, then I’ll record the second edge and run the repository/finalizer checks.

The report now ends exactly with the requested recommendation, cites the external primary documentation inline, and its two deliberate source edges are live. Validation found no trailing whitespace; the remaining changes are the report plus audited-read indexes, which the SASE finalizer will preserve atomically.

Everything is ready. I’m submitting the required atomic final declaration now: the research report and its audited-read record go to the research sidecar, and the three plan-read audit records go to the plan sidecar. After this succeeds I’ll make no further repository changes.

Research completed and saved to [artifact_link_adoption_and_quality.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202608/artifact_link_adoption_and_quality.md).

Core recommendation: use workflow-owned lineage, the existing `links:` frontmatter inlet, deterministic automatic links, and bounded completion-time suggestions—without adding global agent instructions. I also linked the report to the two prior research artifacts it materially derives from.
