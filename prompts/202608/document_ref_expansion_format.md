- **PLAN:**
  [202608/document_ref_expansion_format.md](https://github.com/sase-org/sase--plans/blob/main/202608/document_ref_expansion_format.md)
- **AGENTS:**
  - [bbugyi200.athena.z9--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.z9.md)

The `sase-kp.land.w0.r0` sase agent (see #sshot) just failed to launch. This agent used
the `@research` artifact ref in its prompt, which I think is what caused the problem.
Can you help me fix this? Also, simplify the research sidecar repo's ref expansion, so
`@research:202608/artifacts_pane_contract/artifacts_pane_contract.md` expands to
`the 202608/artifacts_pane_contract/artifacts_pane_contract.md file in the research sidecar repo`?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
