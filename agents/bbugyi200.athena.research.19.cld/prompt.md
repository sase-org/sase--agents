%id(cld, clan=research.19) %m:@research_b  #gh:gh_sase-org__sase I've had the ambition to create a custom sase pager for a
while.

- We recently implemented a custom pager for the `sase bead show` command, which makes
  me think now might be a good time to do this.
- We should make sure that we use the same pager for the `sase bead show` command that
  we do for this new, enhanced pager.
- We should add a new `sase <subcmd>` command (use your best judgement for the
  `<subcmd>` sub-command name) that allows the user to interact with this feature from
  the command-line somehow. I'm not sure of how to make this useful. Think hard about
  this. If its genuinely not needed/useful don't add the new `sase <subcmd>` command
  (but provide your reasoning).
- As our first new use-case, the `v` keymap on the "Agents" tab should start to use this
  as its pager instead of what we use now.
- This pager should support the `<ctrl+n/p>` keymaps to jump to the next/previous entity
  (e.g. file, bead, etc...). By "jump to", I mean re-draw the contents with that file's
  header at the top of the screen.
- We should also support single-keypress navigation to traverse links to refs and really
  anything that the `v` keymap supports rendering hints for currently (if genuinely
  useful).
- The keys associated with each link should be rendered ahead of time (using `0-9`, then
  `a-z`, then `A-Z`, then `00-ZZ` (we shouldn't need to resort to multiple keys often,
  but make sure we support this just in-case).
- We should support both artifact refs (see the sase-ug epic bead, mentioned below, for
  some current context on these) and regular file paths and everything else that the `v`
  keymap on the "Agents" tab supports (within reason).
- Make sure link traversal leaves great breadcrumps that the user can see and are
  visually appealing. The user should be able to use the `<backspace>` keymap to jump
  backwards through this breadcrumb trail.
- Review the sase-ug epic bead, which is in-progress, prior to deciding on your solution
  to make sure this work aligns with that epic's work (where applicable, if at all).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research(report_target=research.19.cld.md)