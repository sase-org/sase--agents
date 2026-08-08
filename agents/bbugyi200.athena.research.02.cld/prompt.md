%id(cld, clan=research.02) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution. #research