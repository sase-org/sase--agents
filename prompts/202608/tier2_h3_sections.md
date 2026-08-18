- **PLAN:**
  [202608/tier2_h3_sections.md](https://github.com/sase-org/sase--plans/blob/main/202608/tier2_h3_sections.md)
- **AGENTS:**
  - [bbugyi200.athena.05o--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05o.md)

The `sase init` command currently auto-generates a `**GLOSSARY TERMS:**` line in agent
instruction files. Can you help me start using a new H3 markdown section under the tier
2 section instead?

- To support this change we should start adding an H3 section under that, dedicated
  specifically to long-term memory files. Long-term memory file H4 sections will be
  generated below that.
- Also let's start listing each glossary term in an unordered bullet list in this new
  "Glossary Terms" H3 section that we generate.
- Make sure these sections are numbered correctly.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
