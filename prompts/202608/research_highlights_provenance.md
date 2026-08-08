- **PLAN:**
  [202608/research_highlights_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202608/research_highlights_provenance.md)
- **AGENTS:**
  - [bbugyi200.athena.vq--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vq.md)

Can you help me start adding a `research` property to the Highlights PDF note that is
added to PDF files created by the `research-highlights` file hook in the sase.yml file
(defined in my chezmoi repo)?

- Currently, we add the `status`, `parent`, and `title` properties to this note.
- This property should have a value of the relative (to the research sidecar repo) file
  path of the markdown file that was used to create the PDF (for example,
  202608/artifact_reference_rendering.md).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
