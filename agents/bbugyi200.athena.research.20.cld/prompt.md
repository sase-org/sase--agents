%id(cld, clan=research.20) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.20.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I want to generalize the "AXE" tab
/ `sase axe` command (soon to be renamed to "Supervisor" / `sase supervisor`--this is
how I shall refer to these from this point on).

- The "Supervisor" tab will be renamed to "Service".
- The idea of this tab is that it will be the UX for a new `sase service` command that
  we add.
- We should add a few appropriate terms to sase's glossary memory web. Think hard about
  this one and make sure that these new glossary terms have excellent (but concise)
  definitions! Memories live with sase agents for a long time.
- The `sase service` command should likely have `start/stop/restart` subcommands (you
  decide) but its primary purpose is to run and manage all of the configured sase
  service procs.
- The `sase service` command will run inside of a platform-specific (e.g. systemd for
  Linux) service. The motivation here is to allow the `sase service` command to run on
  startup. This means that the `sase service` command needs to work with mac/linux
  native services
- The `sase service` command should have an `init` subcommand that installs the service
  on to the current machine. The `sase init` command should wrap this command by
  prompting the user if they want to run this command (make sure we only prompt them
  once when the `-a|--all` CLI option is used).
- Sase Service Procs
  - The `sase supervisor` command will be a builtin service proc that is run and managed
    by the `sase service` command.
  - The `sase_gateway` command (which we already have a service set up for on this
    machine and on the apollo machine) will be migrated to a builtin service proc that
    is run and managed by the `sase service` command (the existing services on this
    machine and the apollo machine should be removed/disabled).
  - The Telegram inbound receiver proc should be migrated to a service proc which is
    defined by the sase-telegram plugin. A consequence of this is that service procs
    need to be able to be specified/defined by plugin repos.
  - These service procs should also be hidden from the "Procs" tab of the "SASE Admin
    Center" panel by default by pre-filling the proc query bar with the `-service`
    filter. They should also not have any gear icon/indicator on the top-right of the
    TUI associated with them.
  - The `sase service` command should have a `proc` subcommand that allows users/agents
    to mange service procs from the command-line.
  - Think hard about the best way to make simple service procs **easy** to create
    (ideally via sase config) and very complex service procs **possible** to create.
  - Also, make sure it is easy for users to disable certain service procs via sase
    config (in case they don't want some beta/personal service proc running on one of
    their machines, for example).
- The "Service" Tab (previously named "AXE"/"Supervisor")
  - We should try our best to retain all existing functionality of the "Supervisor" tab
    by nesting all routine entries/nodes (let's start allowing these rows/entries on the
    "Service" tab to be referred to as "nodes"--we should update the glossary memory web
    accordingly) under the new supervisor service proc node that we add to the "Service"
    tab. Job nodes should continue to be nested under their corresponding routines.
  - Each active/enabled service proc should have a corresponding service proc node on
    the "Service" tab. The supervisor service proc is only special in that we render its
    routine/job nodes under it.
  - Users should be able to start/stop/enable/disable service procs directly from the
    "Service" tab when the corresponding service proc nodes are selected.
  - Background commands, which are currently triggered via the `!` keymap, should still
    be supported with mostly unchanged functionality but should be migrated to a new
    type of "oneshot service proc" and displayed as such (in some visually distinct and
    appealing way) in the "Service" tab.

Can you do some research with the goal of helping me decide the best way to implement
this? As a part of this research you should critique the idea itself and help me
determine whether or not it is worth pursuing and/or if the requirements should be
modified. Make any adjustments to the requirements that you feel are objective
improvements but clearly call these out. End your analysis with a recommended solution. #research(suffix=b)