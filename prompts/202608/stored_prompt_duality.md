- **PLAN:**
  [202608/stored_prompt_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)
- **AGENTS:**
  - [bbugyi200.athena.rs--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.rs.md#member-plan)

Can you help me improve the prompts that we store in sase agent chat markdown files and in prompt markdown files?

- Let's start always storing the unrendered and the rendered agent prompt (see how the difference in the contents that
  we render in the `AGENT XPROMPT` and `AGENT PROMPT` sections of the agent metadata panel on the agents tab for
  context) in every sase agent chat markdown file and every prompt markdown file?
- We currently seem to only store the unrendered version I think (you should verify this).
- For any xprompt reference found in an unrendered prompt (regardless of whether in a sase agent chat file or in a
  prompt file) that has been published to the `<project>--agents` sidecar repo, we should start tranforming this
  reference (e.g. `#foo`) into a markdown hyperlink that links to the file (via a GitHub URL) containing that xprompt
  definition.
- Make sure that this feature has good support for chezmoi repos by linking to the appropriate files in the appropriate
  chezmoi repo when the `use_chezmoi: true` sase config field is set.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last
  but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
