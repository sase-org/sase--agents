- **PLAN:**
  [202609/prompts_overlay_trash_view.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompts_overlay_trash_view.md)
- **AGENTS:**
  - [bbugyi200.apollo.28--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.28.md)

Can you help me improve the new, merged "Prompts" panel (see the
~/tmp/screenshots/20260927_054835.png screenshot for an example of what this panel looks
like currently)?

- Let's start using 100 as our default stash trash limit instead of 20.
- Let's start rendering the "Trash" sub-tab as a little trash icon on the "Stash"
  sub-tab instead, with a keymap (let's use `t` for this keymap or, if `t` is not
  available, `T`) to open a stash trash view.
- Let's make the sub-tab title bar look MUCH nicer (use your best judgement).
- Let's start mapping `@` to the first stash entry when on the "Stash" sub-tab. This
  way, when there are multiple stashed prompts, the user can press `@@` to quickly pop
  the very last prompt that was stashed.
- Update sase's glossary entries related to the stash if appropriate.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
