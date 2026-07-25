#gh:gh_sase-org__sase Can you help me migrate normal linked repos (i.e. not companion repos like `sase--plans`) to use the sase/repos/linked/ directory instead of the sase/repos/ directory?

- We should also start clearing the sase/repos/linked/ directory when preparing the workspace directory for sase agents (so we should delete exactly one workspace directory's linked repo clones before every sase agent launch).
- With that said it would be nice if we didn't have to pay the full cost of cloning linked repos every time an agent calls the sase workspace open command. Try your best to keep make this fast somehow.
- This change should come with no backward compatibility code but you should go through all of the sase projects on this machine (run the `sase project list` command to find these) and delete any sase/repos/ subdirectories that correspond with linked repos associated with that project.

#tale #m_fable