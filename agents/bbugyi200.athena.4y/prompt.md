#gh:gh_sase-org__sase We currently support a `worspace.strategy` config field for `linked_repos` that accepts a value of `none` to indicate that the linked repo's primary workspace directory should always be used. Can you help me get rid of this field completely and start having all linked repos use the same workspace strategy?

- The ability to set `none` as a linked repo's workspace strategy is only used for the chezmoi repo (configured in the ~/.local/share/chezmoi/home/dot_config/sase/sase.yml file).
- The only reason that I did this is because my chezmoi repo is a linked repo that is shared by multiple main sase projects.
- This means that if two different agents working on different sase projects but the same workspace number were to try to open a chezmoi workspace currently, the second one to open the workspace would wipe out the changes from the first one.
- We can fix this however, by starting to clone linked repo workspace directories locally in our current workspace directory. Let's use the new local (already ignored by git) .sase/workspaces/ directory for this.

#plan #m_fable