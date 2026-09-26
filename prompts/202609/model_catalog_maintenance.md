- **PLAN:**
  [202609/model_catalog_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_catalog_maintenance.md)
- **AGENTS:**
  - [bbugyi200.apollo.1t--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1t.md)

Updating the default values used for sase's size model alias pools (`@medium`, for
example) and models supported by completion in the prompt input widget and external
editors (via LSP support) is painful considering how often we need to do it. I would
like to make this much easier so maintainers can update both of these by updating as few
files as possible/desirable. Can you help me implement this? Review the
model_catalog_and_size_alias_maintenance.md file in the research sidecar repo for
context and inspiration before planning.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
