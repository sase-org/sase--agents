# Chat History - ace-run (0af--plan)

- **TIMESTAMP:** 2026-08-22 11:18:33 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0af--plan

**Plan:** /home/bryan/.sase/plans/202608/bead_show_artifact_links.md


## Prompt

#gh:gh_sase-org__sase Can you help me make sure that any bead links are displayed with their proper provenance and relationships (in a visually appealing way) in the `sase bead show` command's output? Add a CLI option to this command to disable this behavior (i.e. not show links).

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/bead_show_artifact_links.md`

> # Plan: Provenance-aware artifact links in `sase bead show`
> ## Outcome and product contract
> `sase bead show <id>` should make typed artifact relationships immediately useful
> without confusing them with scheduling dependencies. By default, full output will show
> every link that touches the bead, including links stored on another bead, links owned by
> a document sidecar, and aggregate-only links such as an agent citation of a bead. It
> will use the relation registry to describe every edge from the displayed bead's
> perspective: outgoing directed edges use their authored relation, incoming directed
> edges use the registered inverse, and undirected `related` edges remain symmetric.
> `DEPENDS ON` and `BLOCKS` remain separate sections backed only by `sase bead dep`.

*See full plan file for details.*

