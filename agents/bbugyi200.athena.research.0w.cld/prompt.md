%id(cld, clan=research.0w) %m:@research_b  #gh:gh_sase-org__sase I want to add support for stand-alone proc shells (i.e.
shells that don't belong to an agent family) to sase.

- MOTIVATION
  - This will allow the user to run commands that claim (and release when appropriate)
    sase project workspaces.
  - These proc shells should also support standard xprompt directives when possible and
    useful (the `%wait` directive should be supported to wait for agents or anything
    else that directive supports, for example).
- REQUIREMENTS
  - We should introduce a new `%proc` directive to support this functionality.
  - The `%proc` directive should be able to be used in xprompt swarms and should thus
    support excellent multi-line and single line syntax.
  - For multi-line syntax, let's start supporting code blocks after the `::` with the
    `%proc` directive and as a new, general-purpose type (I want to be able to specify
    this type as a xprompt input argument at some point in the future). This code block
    may or may not contain a language specifier. If it doesn't, we should default to
    using Bash.
  - For single-line syntax, let's accept a string argument (execute that string as a
    Bash script), a `bash=` kwarg (the same as the string case), and a `python=` kwarg
    (execute the string as a Python script--I'm thinking we should probably inject
    sase's environment here, right? Otherwise why use a Python script?).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research(report_target=research.0w.cld.md)