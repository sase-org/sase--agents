- **PLAN:**
  [202609/bead_note_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)
- **AGENTS:**
  - [bbugyi200.athena.0tv--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md)

I want to add excellent support for bead file attachments. Can you help me implement
this?

- We already support leaving notes of the form `@<path_to_file>` as long as
  `@<path_to_file>` is the only contents of the note.
- We should add support for `@<path_to_file>` references anywhere in a note and require
  that `@@` be used if a literal `@` is needed.
- We should have robust (but optional--not all users will necessarily run the
  `sase bead show` command using a terminal that supports viewing images, for
  example--also I'm not sure that sase agents will want this enabled since it might be
  easier for them to use image file paths to read images directly) support for viewing
  images.
- Finally, make sure that large and arbitrary binary files are supported. Think hard
  about the best way to add support for these.
- Review the bead_note_attachments.md file in the research sidecar repo for context and
  inspiration before planning.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
