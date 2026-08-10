%id(cld, clan=research.05) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to start creating a corresponding bead for every
external bug (e.g. GitHub issue--but this should use our plugin system I think) created
for sase projects that are enabled on the given machine (I'm assuming we will use one or
more chops for this, but I am open to suggestions).

- I also want to do the same thing for Patches (i.e. create a new patch for each PR on
  enabled projects that was not created by a sase agent).
- I then want to merge the "Beads" and "Bugs" sub-tabs on the "Artifacts" tab in an
  elegant way that displays only beads but makes it very clear which beads are
  associated with bugs (and provides useful operations for editing/viewing those bugs).
- Again, we should do something similar for patches: Rename the "PRs" sub-tab of the
  "Artifacts" tab to "Patches" and start making it clear which Patches have PRs that
  were created externally associated with them. Keep in mind that, in the case of
  patches, sase agents do something create PRs and associate them with patches (so the
  existnce of a corresponding PR does not mean that the Patch was triggered by an
  external PR).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research