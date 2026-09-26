- **PLAN:**
  [202609/model_shortcut_replacement.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_replacement.md)
- **AGENTS:**
  - [bbugyi200.apollo.1x--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1x.md)

  We just fixed project tag completion (see the sase-1ag epic bead for context). Can you
  now help me add similar support for the `=` and `==` syntaxes that are used to trigger
  completion for the `%model` directive in the prompt input widget and external editors
  (via LSP support)?

- Namely, since the `%model` directive can only exist in a prompt once, we should
  replace the existing directive (if any) when a model / model alias is selected from
  the completion menu.
- If there is no other `%model` directive in the prompt, then we should preserve the
  current behavior (don't move the new model directive to the top/front of the prompt
  like we do for project tags).
- Make sure that we do not replace existing `%model` directives when they are used in an
  alternation (see the `%alt` directive and its short-hand syntax for context). Also,
  check to make sure that we respect project tags in alternations as well.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
