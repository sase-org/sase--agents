- **PLAN:**
  [202608/task_bead_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)
- **AGENTS:**
  - [bbugyi200.athena.05c--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md)

I want to make sase beads more powerful by making them configurable via sase plugin
hooks. Can you help me implement this?

- Namely I would like users to be able to define plug-ins that define new types of task
  beads.
- Task beads do not currently have a type field so this will need to be added. This new
  `task_type` field should be required.
- On a related note, to make sase project initialization deterministic based on the
  current sase project (not what plugins happen to be installed on the current machine),
  we should start supporting a new project-local sase config field that specifies what
  plugins are required to work on that project. Users that attempt to work on a sase
  project that do not have all required plugins installed should be presented with an
  option to install the missing plugins.
- Each task type should specify a set of fields that need to be set (we should support
  type-specific optional fields as well) in order to create a task bead of that type.
  Some of these fields may represent data (a flag bead's removal date, for example), but
  others may be used to form a template that the task bead will render below its
  description (like a GitHub issue template).
- Some task beads types I think we should support:
  - bug: Not an external bug, but a bug that an agent identifies while working on
    unrelated work. (LOCATION: builtin)
  - feature: A recommended feature improvement that an agent thinks is a good idea but
    is out of scope of its current work. (LOCATION: builtin)
  - memory: A recommended memory file update created by an agent. (LOCATION: builtin)
  - flake: Used to report a flaky test. (LOCATION: builtin)
  - CI: Used to report a failing test or lint that is confirmed to be a true failure
    (not a flake). (LOCATION: builtin)
  - flag: Used the track a feature flag removal. (LOCATION: I plan to convert this bead
    type to project-local configuration for the "sase" sase project).
  - GitHub: We should use this issue type for task beads that get synced with external
    GitHub issues. Note that agents should never create a task bead of this type, so we
    should not list it in the new auto-generated short-term memory file--make sure that
    this behavior is configurable for each task type. (LOCATION: should we move to the
    sase-github repo)
- See the task_bead_type_registry.md file in the research sidecar repo for context and
  inpiration. The research agent that produced this file was not made aware of any of
  the requirements listed below this bullet. My answers to the open questions (see the
  "Open questions for the owner" section) in that research file can be found below.
  1. Yes. Use the snapshot file.
  2. Yes project-config task types should be supported. We should add support for a
     `use: <plugin>@<bead_type>` field that is an improved version of the `use:` field
     used for artifact ref plugins. As a part of this change update the artifact ref
     `use:` field's syntax to require a `<plugin>@` prefix as well. We should use the
     `builtin@` prefix for builtin refs. For example, we should change the `use: plan`
     artifact ref configuration in this repo to `use: builtin@plan` and should change
     `use: research` to `use: sase-research-artifacts@research`.
  3. No audited reads.
  4. Each task bead type should be able to configure its own number for this. We should
     use a default value of `0` for all types except for the flake type, which should
     have a default value of `1`.
  5. Yes. Use field validators from day one.
  6. Immutable.
- Note that we currently implement flag beads as an entirely separate bead type. This
  was a mistake where we over-generalized the concept of feature flags, which are
  supposed to be specific to the "sase" sase project and not a functionality that was
  ever meant to be made available to other sase projects. The flag bead type will
  eventually be migrated to a task bead type but, as noted in the research file, we can
  treat that as out of scope for now.
- Make sure that the `when_to_use` task type field's (see the research file) value is
  rendered in agent instruction files via an auto-generated short-term memory file so
  agents know when they should consider creating a task bead of each particular type.
  Move the existing instructions that we have for task beads in short-term memory into
  this new short-term memory file.
- Make sure that all UI surfaces that display task beads use a colorful label that shows
  the task type. The color should be distinct for each task type.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
