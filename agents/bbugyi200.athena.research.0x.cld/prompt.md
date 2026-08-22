%id(cld, clan=research.0x) %m:@research_b  #gh:gh_sase-org__sase I would like to implement a new `%if` directive that allows
me to specify (in the prompt) that agents should only only launch if a particular
condition, specified by a new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context and make sure this
  research either aligns with that research or that you reconcile any differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research(report_target=research.0x.cld.md)