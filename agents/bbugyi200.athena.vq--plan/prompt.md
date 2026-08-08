#gh:gh_sase-org__sase Can you help me start adding a `research` property to the Highlights PDF note
that is added to PDF files created by the `research-highlights` file hook in the
sase.yml file (defined in my chezmoi repo)?

- Currently, we add the `status`, `parent`, and `title` properties to this note.
- This property should have a value of the relative (to the research sidecar repo) file
  path of the markdown file that was used to create the PDF (for example,
  202608/artifact_reference_rendering.md).

#plan