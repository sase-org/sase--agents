- **AGENTS:**
  - [bbugyi200.athena.research.2w.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2w.cld/README.md)

%id(cld, clan=research.2w) %m:claude/opus@xhigh %q(1.5x, w=0.25) #gh:gh_sase-org**sase
You are researcher cld in a 5-researcher swarm. The other researchers,
`research.2w.cdx`, `research.2w.grk`, `research.2w.mus`, `research.2w.gem`, are
independently investigating the same request and will write their own self-named reports
ending in
`**cdx.md`and`**grk.md`and`**mus.md`and`**gem.md`. Your report will end in `**cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add excellent support for bead file attachments.

- We already support leaving notes of the form `@<path_to_file>` as long as
  `@<path_to_file>` is the only contents of the note.
- We should add support for `@<path_to_file>` references anywhere in a note and require
  that `@@` be used if a literal `@` is needed.
- We should have robust (but optional--not all users will necessarily run the
  `sase bead show` command using a terminal that supports viewing images, for
  example--also I'm not sure that sase agents will want this enabled since it might be
  easier for them to use image file paths to read images directly) support for viewing
  images
- Finally, make sure that large and arbitrary binary files are supported. Think hard
  about the best way to add support for these.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=cld)
