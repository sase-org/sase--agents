%clan(research.0y, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to migrate the sase/memory/task_types.md memory file
to a finalizer that is only active for sase managed projects.

- This finalizer, like all finalizers, should be configurable via a Project Local sase
  config field, which should be added to sase-managed projects by the `sase init`
  command automatically (e.g. `use: builtin@tasks` will be added).
- The goal is to move all of this text out of agent instruction files (to keep
  short-term memory as focused as possible) and only prompt agents to think about
  whether they need to create task beads or not at the very end of the turn.
- I will soon migrate this text to a memory file, once I add a new memory file type.
  This is upcoming work I still need to research, but something you may want to keep in
  mind when thinking about this text.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.0y.cdx
%model:@research_a 
#gh:gh_sase-org__sase I want to migrate the sase/memory/task_types.md memory file
to a finalizer that is only active for sase managed projects.

- This finalizer, like all finalizers, should be configurable via a Project Local sase
  config field, which should be added to sase-managed projects by the `sase init`
  command automatically (e.g. `use: builtin@tasks` will be added).
- The goal is to move all of this text out of agent instruction files (to keep
  short-term memory as focused as possible) and only prompt agents to think about
  whether they need to create task beads or not at the very end of the turn.
- I will soon migrate this text to a memory file, once I add a new memory file type.
  This is upcoming work I still need to research, but something you may want to keep in
  mind when thinking about this text.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research(report_target=research.0y.cdx.md)