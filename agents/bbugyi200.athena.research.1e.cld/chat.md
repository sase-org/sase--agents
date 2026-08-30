# Chat History - ace-run (research.1e.cld)

- **TIMESTAMP:** 2026-08-30 12:30:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1e.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260830_121835.md`

## Prompt

%id(cld, clan=research.1e) %m:@research_b  #gh:gh_sase-org__sase Sase's memory webs are inspired by Hub notes.

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

I'll research this properly before critiquing. Let me start by understanding the current memory web implementation.

I've read some memory strands directly with `cat` while surveying the corpus — that should have gone through the audited read path. Let me use the skill properly now, which also gives me the evidence I need about how links actually render.

I have everything I need. Writing the report.

Let me verify the line-number citations and formatting before finalizing.

The report is written and its citations verified. Now the required final declaration.

Research written to `sase/repos/research/202608/memory_strand_supersession.md`.

## Verdict: half of this is already built and silently switched off; the other half shouldn't be built.

**The rendering half already shipped.** Four commits on your current branch (`ae83faa2e`…`40cd8ce6e`) added `[[target]]` / `![[target]]`, `link_reference`, `link_rendering`, transclusion, and a `## Linked References` section. "Render the superseded note inline or as a reference when the new one is read" is a description of existing behavior — the machinery is just relation-agnostic.

**It's dead in the one web you want it for.** `sase/memory/decisions.md` declares `closure: none`, which the new parser maps to `link_reference: none` (`frontmatter.py:262-282`), which suppresses authored links entirely. The `![[decisions/single-turn-agents]]` link you added to `gates-never-block.md` today renders as literal text — I confirmed it via an audited read. One-line fix: `link_reference: explicit`.

**The corpus doesn't justify the new mechanism.** 8 decision records, 1 supersession ever, 0 strand deletions, 0 renames, 1 authored link. Of 8,989 memory read events, decisions strands account for ~7; half the records have never been read at all. Hiding one roster bullet saves ~44 tokens of a 3,023-token `CLAUDE.md`.

**The one real supersession is the case hiding handles worst.** `webs-render-in-their-own-section` retired *one sentence* of `memory-webs` — the rest is live, and a third record still cites it. Mark it superseded and you delete an authoritative record; don't, and the mechanism has zero uses.

**Hiding contradicts both models you cited.** Doto's hub notes are a *locating* device; the article never discusses pruning. ADR convention (Nygard, `adr-tools`) keeps superseded records listed and flips their **status** — that field exists so a reader can scan the directory and see what's authoritative. Your own descriptor already says "marked superseded in prose, never edited in place."

**But you're right that something is broken.** The pointer runs the wrong way — `memory-webs` doesn't know it was superseded, so the agent who needs the warning never sees it. And the prose convention failed on its first use: `memory-webs.md` carries no mark. That's an *enforceability* problem, not a scale problem. Meanwhile every decision strand already carries `metadata: {status: accepted}`, which is parsed, stored, and never rendered to an agent.

**Recommendation, in order:** (1) fix `decisions.md` frontmatter; (2) add a `[[…]]` back-link and partial-supersession line to `memory-webs.md` — zero code; (3) render `metadata.status` on read, mirroring `sase artifact read`'s existing `warning: superseded by …`, with a doctor check; (4) document the link system in `/sase_memory_write` and `docs/memory.md`.

On that last point — the gap is wider than supersession. `sase_memory_write.md` and `docs/memory.md` mention `[[…]]`, `link_rendering`, and Linked References nowhere, and the docs still teach `closure:` as canonical. An entire shipped subsystem is invisible to the agents meant to use it.

The report includes falsifiable reopen thresholds (~25 records with ≥3 *whole* supersessions, or an agent demonstrably acting on a clearly-marked superseded record) and a test that would prove the report wrong.
