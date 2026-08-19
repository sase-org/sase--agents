- **PLAN:**
  [202608/update_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/update_panel.md)
- **AGENTS:**
  - [bbugyi200.athena.080--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.080.md)

Can you help me improve the `,U` keymap by having it trigger a new panel instead of its
current behavior?

- This new panel should display a list of options to the user, which should be
  selectable via a single key press.
- One of those options should be to update everything (matching the keymap's current
  functionality).
- We should also provide options to update:
  - sase, sase-core, and all sase plugins that are installed
  - all sase LLM / agent CLI providers that are installed
  - agents from the agents sidecar repo (if our local store is missing published agents
    from another machine)
- Describe each one of these options the best you can when displaying them to the user
  in this new panel (keep it concise).
- This keymap and this panel should be fast so only use data that we have already
  fetched (I think we already fetched the data we need periodically; t just won't be
  fresh).
- As a part of this change we should stop triggering sase's admin center panel when one
  of these options is selected. Instead we should use a proc to perform any work we need
  in the background and then prompt the user (y/n) like we do now (without showing the
  "SASE Admin Center" panel).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
