- **PLAN:**
  [202608/simple_artifact_ref_expansion.md](https://github.com/sase-org/sase--plans/blob/main/202608/simple_artifact_ref_expansion.md)
- **AGENTS:**
  - [bbugyi200.athena.09r--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09r.md)

Can you help me migrate the artifact ref expansion for all artifact ref types to a
simple reference like the `@research` ref does?

- Also, no more `@` prefixes for file path references.
- For example, `@plan:202608/foobar.md` should now resolve to
  `the 202608/foobar.md file in the plans sidecar repo`.
- Make sure you review and simplify the ref expansion for all known artifact ref types.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
