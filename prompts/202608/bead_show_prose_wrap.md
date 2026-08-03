- **PLAN:**
  [202608/bead_show_prose_wrap.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_prose_wrap.md)
- **AGENTS:**
  - [bbugyi200.athena.sl--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sl.md#member-plan)

Can you help me start wrapping the description/note text displayed by the `sase bead show` command at a specific line
length?

- Default to 120 characters, but add a new CLI option to make this configurable.
- Also, let's remove the `-S|--style` options supported `color` value (which seems to be same as `rich`) and change the
  short-option for this CLI option from `-S` to `-s`.
- Make sure we don't wrap URLs or inline code snippets (ex: `foo bar baz`).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last
  but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 865 B</summary>

```markdown
Can you help me start wrapping the description/note text displayed by the `sase bead show` command at a specific line
length?

- Default to 120 characters, but add a new CLI option to make this configurable.
- Also, let's remove the `-S|--style` options supported `color` value (which seems to be same as `rich`) and change the
  short-option for this CLI option from `-S` to `-s`.
- Make sure we don't wrap URLs or inline code snippets (ex: `foo bar baz`).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last
  but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
```

</details>

<!-- /sase:section:rendered -->
