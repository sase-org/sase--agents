- **PLAN:**
  [202608/prompt_ordered_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)
- **AGENTS:**
  - [bbugyi200.athena.ub--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.ub.md)

We currently already support a robust and reliable set of ways to auto-generate a dash character prefix (e.g. `- ` or
` -`, depending on the indentation of the current line) for a bullet in a prompt that is being typed in the prompt input
widget (e.g. via integrations with the `o` / `O` / `<ctrl+j>` keymaps). Can you now help me add support for doing the
same for numbered lists?

- These numbered list bullets should start with `<N>. `, where `<N>` is some positive integer that can have zero or more
  spaces before it (we determine how many spaces to use based on the indentation of the current line).
- Make sure this works with all of the same keymaps that work for unordered lists.
- Unlike unordered lists, however, we should make sure to auto increment/decrement other members of the ordered list
  when adding a new member if necessary.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last
  but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
