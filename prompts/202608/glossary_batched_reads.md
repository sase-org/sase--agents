- **PLAN:**
  [202608/glossary_batched_reads.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_batched_reads.md)
- **AGENTS:**
  - [bbugyi200.athena.069--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.069.md)

Can you help me add support to the `sase glossary show/read` commands for accepting
multiple terms as arguments?

- The goal with this change would be to reduce the amount of tokens used by the
  glossary.
- Make sure the auto-generated glossary section in agent instruction files is updated to
  recommend reading all terms at once if possible.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
