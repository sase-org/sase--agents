- **AGENTS:**
  - [bbugyi200.kellys_mbp.research.4.cdx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.research.4.cdx/README.md)

%clan(research.4, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like
to add the ability for users to add new projects in bulk from the "Projects" tab on the
"SASE Admin Center" panel.

- This will be useful, for example, when users are onboarding a new machine and want to
  enable the set of projects they are currently working on for that machine.
- We should provide excellent completion for the organizations/repos that the user is
  most likely to select.
- See how we do this for the `#gh` VCS xprompt workflow's argument for inspiration.
- We need to make sure to do this in a VCS-agnostic way so future VCS plugins are
  supported automatically.
- As a part of this change we should stop auto-enabling new projects that are created
  when an argument is passed to a VCS xprompt workflow that is associated with a new
  (i.e. currently unknown to this machine's sase) project.

Can you do some research with the goal of helping me decide the best way to implement
this? In particular, think very hard about what the best UX for this functionality looks
like. End your analysis with a recommended solution.]]) %id:research.4.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I would like to add the
ability for users to add new projects in bulk from the "Projects" tab on the "SASE Admin
Center" panel.

- This will be useful, for example, when users are onboarding a new machine and want to
  enable the set of projects they are currently working on for that machine.
- We should provide excellent completion for the organizations/repos that the user is
  most likely to select.
- See how we do this for the `#gh` VCS xprompt workflow's argument for inspiration.
- We need to make sure to do this in a VCS-agnostic way so future VCS plugins are
  supported automatically.
- As a part of this change we should stop auto-enabling new projects that are created
  when an argument is passed to a VCS xprompt workflow that is associated with a new
  (i.e. currently unknown to this machine's sase) project.

Can you do some research with the goal of helping me decide the best way to implement
this? In particular, think very hard about what the best UX for this functionality looks
like. End your analysis with a recommended solution. #research
