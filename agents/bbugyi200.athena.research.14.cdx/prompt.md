%clan(research.14, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] It is very important that users that fully adopt sase and use
it in some of their projects can still use the agent CLIs that sase supports directly
(by using Claude code to do some research or create a quick commit, for example).
Currently, however, there seem to be some instructions that guide agents towards using
tools that only work when a sase agent is defined.

Can you do some research with the goal of helping me understand what it would take to
make sase projects usable by agent CLIs? Ideally, we should support as many of sase's
features as possible when running agent CLI's directly. For features that cannot be
supported, however, it should be clear to the agent (without adding to agent instruction
files too much--ideally, we don't add to agent instruction files at all) what they
should do instead.]]) %id:research.14.cdx
%model:@research_a 
#gh:gh_sase-org__sase It is very important that users that fully adopt sase and use
it in some of their projects can still use the agent CLIs that sase supports directly
(by using Claude code to do some research or create a quick commit, for example).
Currently, however, there seem to be some instructions that guide agents towards using
tools that only work when a sase agent is defined.

Can you do some research with the goal of helping me understand what it would take to
make sase projects usable by agent CLIs? Ideally, we should support as many of sase's
features as possible when running agent CLI's directly. For features that cannot be
supported, however, it should be clear to the agent (without adding to agent instruction
files too much--ideally, we don't add to agent instruction files at all) what they
should do instead. #research(report_target=research.14.cdx.md)