# Chat History - ace-run (research.r.cld)

- **TIMESTAMP:** 2026-07-29 19:47:31 EDT
- **MODEL:** claude/opus
- **AGENT:** research.r.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_193349.md`

## Prompt

%id(cld, clan=research.r) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I recently produced some research (see the sase_sites_platform.md file in the research sidecar repo) related to an initiative to support sase sites, which are meant to be custom (though with a structured framework / expected API usage by site readers/writers) HTML websites that can be shared with agents/humans (e.g. teammates) and read from / written to by sase agents. Can you do some more research to help me refine this idea a bit?

- It seems like the original research is leaning towards having two different types of sase sites: A project site and a custom site.
- I would like to explore the idea of instead just supporting a single generic sase site that can be linked with zero or more other sase sites and/or artifacts.
- To produce the project sase site for each enabled sase project, we could just start producing a single sase site for every meaningful sase artifact, like plans and beads and agents for example, and then linking them all together under the same project site. This perhaps acts like a structural /hub node that specifies tabs and website layout.

End your analysis with a recommended approach. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by reading the original research, then explore how sase artifacts are currently modeled.

I have a solid evidence base. Writing the report now.

Research written to `sase/repos/research/202607/sase_sites_unified_site_model.md`.

## Verdict: adopt the single generic site — with three corrections

Your instinct is right, and it's better supported than you framed it. **SASE already ships this model in Markdown.** I verified on this machine:

- `agents_sync/rendering_index_pages.py` renders a five-level hub chain (root → owner → machine → hood → family → agent), and every one of the **5,407** agent pages opens with a breadcrumb across it
- **2,784** plans carry header blocks linking to their prompt, agents, and commits — as cross-repo GitHub URLs
- Commit trailers already carry reference links into the sidecars: **2,064** `SASE_AGENT=`, **742** `SASE_PLAN=`, **1,632** `SASE_MACHINE=`
- The ACE preview reader already keys on "canonical artifact reference" as its unit of viewing

So the corpus never had two kinds. `project`/`custom` was bundling three separate axes — provenance, structure, and publication — into one enum. Only publication deserves its own machinery, and as an *optional facet on any site*, not a second type.

**The three corrections the proposal needs:**

1. **Identity = the artifact ref, not a new ID space.** `plans:202607/foo.md` *is* that plan's site. No creation step, no 13k-row registry, drift semantics inherited. This kills the prior note's opaque-ID model. **Blocker found:** there is no `bead:` or `agent:` ref kind — `_store_types.py:44` explicitly excludes beads and agents from document roles, and `bug:` is a GitHub issue. Adding those two kinds is small, unblocks everything, and pays off immediately in ACE completion and the LSP regardless of sites.

2. **A link is a reference, not a grant.** This is the one that would bite you. Your graph is nearly fully connected, so publish-by-reachability from one plan reaches 3,011 chat transcripts. Notion does exactly this (subpages publish by default, opt-out per page) — invert it. Published set = explicit scope ∩ audience ceiling, never reachability; out-of-scope links degrade to stubs, reusing `hosted_links.py`'s never-guess discipline.

3. **Address every artifact; materialize by scope.** "A site per artifact" is about addressing, not emitting 21,452 files.

**One addition worth your attention:** draw the node boundary where the privacy boundary is. Prompt snapshots become a tab of their plan, chats a tab of their agent, commits become rows. That removes ~17,000 nodes *and* makes the transcripts structurally unreachable as independent link targets.

**Correction to the prior research:** its widget spec sources data through "the existing ACE query language," but `docs/query_language.md:10` says plainly that it's ChangeSpec-only and the Agents tab has a separate language; bead and plan search are independent linear scans. `query: "bead:sase-26.*"` isn't valid anywhere. Widgets need to name their corpus explicitly in v1.

External precedent is strong: Backstage runs exactly this model (one envelope, kind discriminator, **read-only processor-generated `relations`**), and Datasette validates per-record pages with JSON twins off an index.

I made that file, so I'll commit it.

Committed and pushed.

**`5a09865 docs(research): evaluate a unified SASE site model`** — adds `202607/sase_sites_unified_site_model.md` to the research sidecar. Working tree is clean and level with `origin/main`; the commit message file was consumed by the successful commit.

One thing surfaced during the rebase worth knowing: a sibling commit landed just below mine, `06f385e docs: research generic SASE site composition`, adding `202607/sase_sites_generic_composition.md` (749 lines). That's a parallel report on the same question from another agent — I didn't write it and haven't read it. If you want the two reconciled (they may agree, or may differ on identity and publication semantics, which is where my report puts the load-bearing decisions), that's a worthwhile next pass.
