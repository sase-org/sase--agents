#gh:gh_sase-org__sase
#fork:sase-5w Can you now help me add a new `sase repo` command?

- Add a `list` subcommand. Make sure this command lists all repos for the current project or for all projects (use a CLI option to make this configurable) and that every linked repo and sidecar repo is shown in the output, along with whether or not a particular project workspace has that repo cloned.
- The `sase workspace open` command should be migrated to a new `sase repo open` command. Make sure you update all agent instructions as necessary.
- We should also add a new sase repo log command that shows a log of which agents opened which repos and for what reasons. See how the sase memory log command handles this for inspiration.
- #beau 

#epic #m_fable