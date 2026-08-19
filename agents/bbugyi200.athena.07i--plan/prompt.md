#gh:gh_sase-org__sase We currently support refs of the form `@<ref>:<ref_arg>` in sase agent prompts.
We also support good completion for `<ref_arg>`. The problem is that this completion is
not always up to date. For example if an agent commits a markdown file to the research
sidecar repo and then, shortly after that, I type `@research:` in the prompt input
widget, the new markdown file does not show in the completion menu. Can you help me fix
this?

- I think we can fix this by adding support for a new `@<ref>::` syntax that triggers
  (with the last `:`) a sync of the relevant repo to fetch recent files for the
  completion menu.
- Make sure the second colon is immediately deleted.
- Also make sure that the user is made aware of what's happening in a visually appealing
  way.
- After the corresponding repo has been synced, the completion menu should be triggered.
- #beau

#plan