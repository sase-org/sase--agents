%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I want to unify agent families so users can more
easily conceptualize them as just a different way of grouping agents on the
agents tab. Can you do some research to help me understand what conceptual
barriers I'm going to need to design around / implement solutions for in order
to make this happen? Keep in mind that part of the goal is to migrate as much
functionality from xprompt workflows (YAML files) as possible to xprompt swarms
(markdown files), which I would ideally like to be able to use to define
workflows that are just as robust as those that we currently define using YAML
xprompt workflows. For example:

- I know that I will need to allow agents in the same family to run in parallel.
  I plan on adding support for a new `wait=<bool>` keyword argument to the
  `%name` directive for this.
- I know that Python and Bash xprompt workflow steps will need to be allowed to
  be root agent rows in order to support, for example, defining an xprompt swarm
  that requires a command to be run that updates the software you are working on
  (e.g. sase) before one or more agents (e.g. to verify the work) can run.
  Moreover, this is just needed to make them definable in xprompt swarms I
  think, which would be preferable to xprompt workflows.

What are some of the requirements I have not thought of? Are there any design
decisions that you would absolutely need from me before working implementing
something like this? End your analysis with a set of <=7 of the highest-value
questions you can think to ask to help push this initiative forward. #research