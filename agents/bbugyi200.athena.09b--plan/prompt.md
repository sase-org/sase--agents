#gh:gh_sase-org__sase Can you help me split out the `runners` and `priority` kwargs, which are
specific to sase's agent queue logic, to a new `%q/%queue` directive? %w(runners=3)

- Make sure this directive has all the same completion support in the prompt input
  widget and external editors (via LSP support) as other directives.
- The `runners` kwarg should also be supported as a positional argument (`%q:5` should
  be equivalent to the current `%w(runners=5)`, for example).
- The `priority` kwarg should also support a `p` shorthand (so, for example, `%q(p=20)`
  should be equivalent to `%q(priority=20)` which should be equivalent to the current
  `%w(priority=20)`).
- Make sure you thoroughly search all linked repos for references to these keywords and
  convert them over to using this new directive. I think some of my chops defined in the
  bugyi-chops repo might need updating as well.

#plan %m:@xlarge