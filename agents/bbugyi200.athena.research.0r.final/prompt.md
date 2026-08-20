%id(final, clan=research.0r) %wait(priority=20) %m:@research_lead
%wait:research.0r.cdx %wait:research.0r.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I've been improving sase's support for artifacts recently and
generalizing / defining what an "artifact" exactly is. The next step I plan to take is
to add excellent support for linking artifacts to other artifacts.

- We will add a new "artifact markdown file (aka artifact md file)" term to the
  glossary. Every sase artifact should have a corresponding artiface md file:
  - Markdown artifact files should support this directly (i.e. they should serve as
    their own artifact md files) via a `links` field in their frontmatter.
  - Other types can use an `<name>.md` file in the same directory as their artifact md
    file, where `<name>` is the basename of the artifact file.
- All links should be rendered at top of artifact md files in a nice table with markdown
  hyperlinks to the appropriate artifact files on GitHub.
- The `RELATED` notes left on task beads (I think agents are adviced to leave these by
  the /sase_new_task xprompt skill, but I'm not sure) currently should be converted to
  formal links via a new `sase artifact link` command (that allows an artifact to be
  linked to another--in this case one bead should be linked to the other)!
- Also, all artifact refs in prompts should result in the appropriate links being
  created from that agent to that artifact.
- All links should have a required relation/description (so it is clear why these
  artifacts were linked).
- We will add a new `sase artifact read` command and encourage agents to use it for
  direct, tracked artifact reads instead of `sase repo open` (which should still be used
  when modifying files inside sidecar repos or when asked to do broad exploration over
  the artifacts contained in a sidecar repo)!
  - All reads agents make with this command should result in that agent being linked to
    that artifact!
- We will eventually add a new "Agents" sub-tab to the "Artifacts" tab. This is out of
  scope for this current feature but should be kept in mind. (Completed agents are just
  artifacts and will be linked to like any other artifact eventually!)

Can you do some research to help me decide the best way to implement all of this? End
your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0r.cdx` -> `__a`, `research.0r.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```