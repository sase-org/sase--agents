# Chat History - ace-run (0eh--plan)

- **TIMESTAMP:** 2026-08-26 14:48:06 EDT
- **MODEL:** claude/opus
- **AGENT:** 0eh--plan

**Plan:** /home/bryan/.sase/plans/202608/link_rail_every_tab.md


## Prompt

#gh:gh_sase-org__sase We recently added the new "Agents" sub-tab to the "Artifacts" tab (see the
sase-tj epic bead). We also fixed some defects related to / made some improvements to
artifact links (see the sase-tw epic bead). I now want to add a rich integration with
artifact links to every tab in the TUI (even chops can link to the agent artifacts they
were responsible for launching!). Can you help me implement this?

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
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/link_rail_every_tab.md`

> # Plan: A link rail on every tab
> ## Problem
> ACE has three top-level tabs and a typed artifact-link graph that only one of them can
> see. `RelationPanel` renders link relations, but `_app_action_availability.py:282`
> hard-gates `toggle_relation_panel` to the Artifacts tab, and the panel's host mixin
> reads a pane API (`self.contract`, `self.relation_index()`,
> `self.selected_entry_target()`) that the Agents tree and the AXE sidebar do not have. So
> an agent row cannot show what it cited, a chop cannot show what it launched, and a bead
> on the Beads pane shows its links in a rail whose link segment has no key at all —
> `_rail_mode_key` returns `""` for `RelationRole.LINK` (`relation_panel.py:~470`), and

*See full plan file for details.*

