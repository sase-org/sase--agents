# Chat History - ace-run (research.1e.cdx)

- **TIMESTAMP:** 2026-08-30 12:28:40 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.1e.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260830_121835.md`

## Prompt

%clan(research.1e, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] Sase's memory webs are inspired by Hub notes.

- See the
  https://writing.bobdoto.computer/the-difference-between-hub-notes-and-structure-notes-explained/
  article for context.
- According to that article, "By pointing to where particular trains of thought can be
  found, indicated by the first note in the sequence, hub notes make it easy to find
  areas of your zettelkasten you'd like to explore.".
- For memory webs, the `sase/memory/<web>.md` file is analogous to a hub note in a way
  currently since it points to many different memory strand files.
- The problem with memory webs is that all memory strand files are always referenced.
  Ideally, we should be able to have one memory strand supersede another, which should
  result in the superseded note being rendered (either "inline" or as a "reference")
  when the new note is read via the `sase memory show/read` commands.
- The superseded memory file would then not be shown in the hub note (and thus would not
  be rendered in the "Memory Webs" section of agent instruction files).
- For the "sase" sase project, this functionality will be useful for the decisions
  memory web (since new decisions might supersede old ones), for example.
- Make sure that agents are aware of the ability of memory strands to supersede one
  another by updating the /sase_memory_write xprompt skill's instructions.

Can you do some research with the goal of critiquing the above idea? Is it worth doing
at all? End your analysis with either a recommended solution or justification for why
you think I should not proceed with this idea.]]) %id:research.1e.cdx
%model:@research_a 
#gh:gh_sase-org__sase Sase's memory webs are inspired by Hub notes.

- See the
  https://writing.bobdoto.computer/the-difference-between-hub-notes-and-structure-notes-explained/
  article for context.
- According to that article, "By pointing to where particular trains of thought can be
  found, indicated by the first note in the sequence, hub notes make it easy to find
  areas of your zettelkasten you'd like to explore.".
- For memory webs, the `sase/memory/<web>.md` file is analogous to a hub note in a way
  currently since it points to many different memory strand files.
- The problem with memory webs is that all memory strand files are always referenced.
  Ideally, we should be able to have one memory strand supersede another, which should
  result in the superseded note being rendered (either "inline" or as a "reference")
  when the new note is read via the `sase memory show/read` commands.
- The superseded memory file would then not be shown in the hub note (and thus would not
  be rendered in the "Memory Webs" section of agent instruction files).
- For the "sase" sase project, this functionality will be useful for the decisions
  memory web (since new decisions might supersede old ones), for example.
- Make sure that agents are aware of the ability of memory strands to supersede one
  another by updating the /sase_memory_write xprompt skill's instructions.

Can you do some research with the goal of critiquing the above idea? Is it worth doing
at all? End your analysis with either a recommended solution or justification for why
you think I should not proceed with this idea. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll ground the critique in the cited hub-note article, SASE’s current memory-web implementation, and the project’s canonical memory/skill guidance. I’m using the SASE memory-read skill because these concepts and generated xprompt skills have audited reference instructions.

The project’s existing “Memory Webs” decision already anticipated this exact pressure: it says supersession should reuse the established `supersedes` / `superseded-by` relation model once prose cross-references stop scaling. I’m now checking whether that prior design is actually compatible with memory-strand rendering and lookup, rather than treating it as automatically correct.

The requested destination is a nested SASE research sidecar repository, not part of the main checkout. I’m switching to the repository-opening workflow now so the eventual report is written and finalized against the correct repository identity.

The key tension is now clear: the desired behavior is valuable, but “reuse artifact relations” is not automatically a clean implementation. Memory initialization must be deterministic from committed memory files, while artifact-link truth currently lives in a separate relation store. I’m comparing those ownership models before settling the recommendation.

The evidence points to a qualified “yes”: supersession is worth supporting as a current-vs-history correctness feature, not as a token-saving feature. The existing decisions corpus has no whole-record replacement yet—the one apparent example replaces only a sentence—so the report will recommend a narrow relation model that lands with the first genuine replacement and explicitly rejects hiding that partial-update example.

The report is complete and passed structural checks (`git diff --check`, citation/internal-path existence, and balanced code fences). Its recommendation is to proceed only with a true whole-record replacement, using a local typed edge and active roster rather than coupling memory initialization to the artifact sidecar graph.

Research written to [memory_web_strand_supersession_critique.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202608/memory_web_strand_supersession_critique.md).

Recommendation: proceed, but only alongside the first genuine whole-strand replacement. Use a validated local `supersedes` edge, show only active strands in generated rosters, preserve historical exact reads, and avoid coupling memory initialization to the artifact sidecar graph. The current memory-web decision pair is only a partial amendment and should not be treated as supersession.
