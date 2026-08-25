- **PLAN:**
  [202608/strip_strand_markers_from_agent_docs.md](https://github.com/sase-org/sase--plans/blob/main/202608/strip_strand_markers_from_agent_docs.md)
- **AGENTS:**
  - [bbugyi200.athena.0dr--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dr.md)

Sase's memory webs use markdown comments of the form `<!-- sase:strands -->` to indicate
where strand file names, keywords, and descriptions should be rendered. This is fine
(and important) when it comes to the memory files themselves, but we should be able to
strip these lines (and the blank lines that preceed these lines) from the markdown that
gets rendered in agent instruction files, right? If so, use your /sase_plan skill to
plan the appropriate changes.
