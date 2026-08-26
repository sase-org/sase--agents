%id(cld, clan=research.16) %m:@research_b  #gh:gh_sase-org__sase We recently added the new "Agents" sub-tab to the "Artifacts"
tab (see the sase-tj epic bead). We also fixed some defects related to / made some
improvements to artifact links (see the sase-tw epic bead). I now want to add a rich
integration with artifact links to every tab in the TUI (even chops can link to the
agent artifacts they were responsible for launching!).

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
with a recommended solution and user interface (make sure you think hard about this). #research(report_target=research.16.cld.md)