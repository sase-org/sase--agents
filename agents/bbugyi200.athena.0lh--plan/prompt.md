#gh:gh_sase-org__sase Can you help me make it so the `sase init` command prompts to run the
`sase machine init` command less?

- When the `sase init` command's `-a|--all` option is used, we should only prompt the
  user if they want to run the `sase machine init` command once (not for every project).
- Once the user intializes a machine once with the `sase machine init` command, the
  `sase init` command should prompt the user to run the `sase machine init` command iff
  new machines have been discovered which were not reviewed the last time the
  `sase machine init` command was run on that machine.

#plan %m:gpt-6-astra