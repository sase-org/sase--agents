- **AGENTS:**
  - [bbugyi200.athena.research.0q.cdx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0q.cdx/README.md)

%clan(research.0q, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to
make sase beats more powerful by making them configurable via sase plugin hooks.

- Namely I would like users to be able to define plug-ins that define new types of task
  beads.
- Task beads do not currently have a type field so this will need to be added. This new
  `type` field should be required.
- Therefore we will need to update our existing agent instructions regarding task beads
  to make sure that they create tasks of the appropriate types.
- Since the available task bead types depend on what plugins are installed on the
  current machine, we will need to be smart about how we generate agent instructions for
  projects.
- On a related note, to make sase project initialization deterministic based on the
  current sase project (not what plugins happen to be installed on the current machine),
  we should start supporting a new project-local sase config field that specifies what
  plugins are required to work on that project. Users that attempt to work on a sase
  project that do not have all required plugins installed should be presented with an
  error/warning/option to install the missing plugins.
- Each task type should specify a set of fields that need to be set to create a task
  bead of that type. Some of these fields may represent data (a flag bead's removal
  date, for example), but others may form a template that the task bead will render
  below its description (like a GitHub issue template).
- Some task beads types I think we should support:
  - bug: Not an external bug, but a bug that an agent identifies while working on
    unrelated work. (LOCATION: builtin)
  - feature: A recommended feature improvement that an agent thinks is a good idea but
    is out of scope of its current work. (LOCATION: builtin)
  - memory: A recommended memory file update created by an agent. (LOCATION: builtin)
  - flake: Used to report a flaky test. (LOCATION: builtin)
  - CI: Used to report a failing test or lint that is confirmed to be a true failure
    (not a flake).
  - flag: Used the track a feature flag removal. (LOCATION: I plan to factor this out to
    a new sase-flag-tasks GitHub repo).
  - GitHub: We should use this issue type for task beads that get synced with external
    GitHub issues. (LOCATION: should we move to the sase-github repo)

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.0q.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I want to make sase beats
more powerful by making them configurable via sase plugin hooks.

- Namely I would like users to be able to define plug-ins that define new types of task
  beads.
- Task beads do not currently have a type field so this will need to be added. This new
  `type` field should be required.
- Therefore we will need to update our existing agent instructions regarding task beads
  to make sure that they create tasks of the appropriate types.
- Since the available task bead types depend on what plugins are installed on the
  current machine, we will need to be smart about how we generate agent instructions for
  projects.
- On a related note, to make sase project initialization deterministic based on the
  current sase project (not what plugins happen to be installed on the current machine),
  we should start supporting a new project-local sase config field that specifies what
  plugins are required to work on that project. Users that attempt to work on a sase
  project that do not have all required plugins installed should be presented with an
  error/warning/option to install the missing plugins.
- Each task type should specify a set of fields that need to be set to create a task
  bead of that type. Some of these fields may represent data (a flag bead's removal
  date, for example), but others may form a template that the task bead will render
  below its description (like a GitHub issue template).
- Some task beads types I think we should support:
  - bug: Not an external bug, but a bug that an agent identifies while working on
    unrelated work. (LOCATION: builtin)
  - feature: A recommended feature improvement that an agent thinks is a good idea but
    is out of scope of its current work. (LOCATION: builtin)
  - memory: A recommended memory file update created by an agent. (LOCATION: builtin)
  - flake: Used to report a flaky test. (LOCATION: builtin)
  - CI: Used to report a failing test or lint that is confirmed to be a true failure
    (not a flake).
  - flag: Used the track a feature flag removal. (LOCATION: I plan to factor this out to
    a new sase-flag-tasks GitHub repo).
  - GitHub: We should use this issue type for task beads that get synced with external
    GitHub issues. (LOCATION: should we move to the sase-github repo)

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research
