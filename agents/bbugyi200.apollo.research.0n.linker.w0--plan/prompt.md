#gh:gh_sase-org__sase I would like to make the sase-listen repo a first-class sase plugin. Can you help
me implement this?

- To support this change, we should start allowing sase plugins to define sub-commands
  somehow.
- The sase-listen plugin should use this new functionality to define the `sase listen`
  command.
- This command should work exactly like the `sase-listen` command, but should support
  sase's CLI completion (make sure that completion is updated automatically when a
  plugin like this is installed).
- We should also start displaying this plugin on the "Updates" tab of the "SASE Admin
  Center" panel so users can manage its installation the same way they do for other sase
  plugins. I have already added the `sase--plugin` GitHub label on sase-listen's GitHub
  repo to support this.
- We should make it very clear to users when a plugin installs new sub-commands.
- Review the sase_listen_plugin_commands.md file in the research sidecar repo for
  context and inspiration before planning. I agree with all of the requirements
  recommended in that research file.
- #beau

#plan %m:@xlarge %auto %w:research.0n.linker