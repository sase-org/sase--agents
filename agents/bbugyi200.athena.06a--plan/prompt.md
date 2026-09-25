#gh:gh_sase-org__sase Can you help me migrate sase flag beads to a new "flag" task bead type (see the
sase-p3 epic bead for context on task bead types)?

- We made a mistake when we initially designed sase flags.
- For one, sase's feature flags are only applicable to the "sase" sase project.
- Also we should only support two kinds of Feature Flags (I think we support 4 ATM):
  - `beta`: for new potentially unstable features
  - `sunset`: for deprecations (so we can remove deprecated features behind a feature
    flag) and/or for backward-compatibilty logic (which should always be removed at some
    point).
- Existing flag beads have terrible descriptions. Make sure this new flag task bead type
  has some useful required fields that agents must set in order to create a new flag.
  Think hard about which fields to require.
- This new flag task bead type should be defined in project-local configuration (e.g. in
  this repo's sase/sase.yml file).
- Make sure to migrate any existing flag beads over to new "flag" task beads.
- Make sure that any memory files related to feature flags/flag beads are
  updated/deleted appropriately.
- See the sase-pq epic bead for related work that is in-progress. Make sure that your
  work does not conflict with that epic (and that the "flag" task type are eventually
  supported on all the same UI surfaces). Leave notes on that epic bead and/or that epic
  bead's phase beads if necessary to coordinate (the epic lander agent will read these
  at the very least, but phase agents will also read their bead notes when they are
  first launched).
- #beau

#plan