- **PLAN:**
  [202608/nested_snippet_sessions.md](https://github.com/sase-org/sase--plans/blob/main/202608/nested_snippet_sessions.md)
- **AGENTS:**
  - [bbugyi200.athena.zm--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md)

In the prompt input widget, we support expanding snippets with the `<tab>` keymap. The
user can then step through the various "tab-stops" using the `<tab>` and `<shift+tab>`
keymaps. The problem is that nesting snippets (e.g. expanding a different snippet after
jumping to `$2` in a snippet defined as `foo $1 bar $2 baz $3 buz`) results in us
forgetting the tab-stops for the current snippet. Can you help me fix this by adding
better support for nested snippets?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
