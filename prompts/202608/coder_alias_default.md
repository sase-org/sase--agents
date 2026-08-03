- **PLAN:**
  [202608/coder_alias_default.md](https://github.com/sase-org/sase--plans/blob/main/202608/coder_alias_default.md)
- **AGENTS:**
  - [bbugyi200.athena.sp--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sp.md#member-plan)

Can you help me set the default value for the `@coder` model alias to `codex/gpt-5.5`? You should then be able to remove
the default values for the `@claude_coder` and `@codex_coder` model aliases since these can now just use `@coder` as
their default values. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author
the appropriate tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 517 B</summary>

```markdown
Can you help me set the default value for the `@coder` model alias to `codex/gpt-5.5`? You should then be able to remove
the default values for the `@claude_coder` and `@codex_coder` model aliases since these can now just use `@coder` as
their default values. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author
the appropriate tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.
```

</details>

<!-- /sase:section:rendered -->
