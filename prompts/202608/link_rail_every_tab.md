- **PLAN:**
  [202608/link_rail_every_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)
- **AGENTS:**
  - [bbugyi200.athena.0eh--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md)

We recently added the new "Agents" sub-tab to the "Artifacts" tab (see the sase-tj epic
bead). We also fixed some defects related to / made some improvements to artifact links
(see the sase-tw epic bead). I now want to add a rich integration with artifact links to
every tab in the TUI (even chops can link to the agent artifacts they were responsible
for launching!). Can you help me implement this?

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
- Review the link_rail_every_tab.md file in the research sidecar repo for context and
  inspiration before planning. You should also review the annotations that I left on
  this research file, which can be found in the ~/bob/ref/chat/link_rail_every_tab.md
  file.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
