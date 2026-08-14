- **PLAN:**
  [202608/provider_qualified_model_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_qualified_model_completion.md)
- **AGENTS:**
  - [bbugyi200.athena.012--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.012.md)

We already support model name and model alias completion in the prompt input widget and
in external editors via LSP support. Can you help me make it so when the user types a
provider name in and then types a forward slash, we show completion for all model names
that we know about that are valid for that provider? For example, typing `%m:claude/`
should trigger completion for all known claude model names. Think this through
thoroughly and create a plan using your `/sase_plan` skill. Choose and author the
appropriate tier, validate and revalidate until it passes, then submit it with
`sase plan propose` (as the skill instructs) before making any file changes.
