- **PLAN:**
  [202610/ctrl_t_typed_chain_yield.md](https://github.com/sase-org/sase--plans/blob/main/202610/ctrl_t_typed_chain_yield.md)
- **AGENTS:**
  - [bbugyi200.apollo.3v--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3v.md)

I think we recently broke the `<ctrl+t>` keymap in the prompt input widget for many of
its use-cases. I'm assuming the next-word prediction epic broke this. For example, when
I type `+bob-cli bob-m<tab>` I would expect `bob-mac-capture` to expand, but it does
not. Can you help me confirm/deny my suspicion, diagnose the true root cause, and fix
the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
