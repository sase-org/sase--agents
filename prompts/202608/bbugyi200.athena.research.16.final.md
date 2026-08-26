- **AGENTS:**
  - [bbugyi200.athena.research.16.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.16.final/README.md)

%id(final, clan=research.16) %m:@research_lead %wait:research.16.cdx
%wait:research.16.cld #gh:gh_sase-org__sase You are the lead researcher: two
independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

We recently added the new "Agents" sub-tab to the "Artifacts" tab (see the sase-tj epic
bead). We also fixed some defects related to / made some improvements to artifact links
(see the sase-tw epic bead). I now want to add a rich integration with artifact links to
every tab in the TUI (even chops can link to the agent artifacts they were responsible
for launching!).

- I think we can accomplish this by adding a single new "Links" panel that allows the
  user to view and traverse the links associated with the currently selected sase
  entity.
- This keymap should also support jumping to the corresponding linked-to entity in the
  TUI using as few key presses as possible (similarly, link traversal should be
  incredibly intuitive and take as few key presses as possible).
- We should use a single keymap across all tabs to trigger this new panel (select an
  appropriate trigger key for this--maybe `$`?).
- We should figure out a way to display the links related to the currently selected
  entity somewhere in the TUI. This location should be the same across all tabs and all
  entities. It should provide useful information about the links but must be very
  concise.
- None of this functionality should be available or visible when the currently selected
  entity does not have any associated links.
- #beau

Can you do some research with the goal of exploring a few different user interfaces for
this new panel and helping me decide the best way to implement it? End your analysis
with a recommended solution and user interface (make sure you think hard about this).

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.16.cdx` -> `__a`, `research.16.cld` -> `__b`), then read both reports.
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
