#gh:gh_sase-org__sase Can you help me start suppressing / not showing these warning messages about
machines on my tailnet (discovered via sase's remote machine discovery) which are not
connected? The user can always troubleshoot / connect these machines using the
`sase machine init` command in the future, but after inital setup (i.e. the first time
the `sase machine init` command is run), we shouldn't be bothered with remote machine
prompts / warnings. See the command output below for context.

#plan

```
❯ sase init -a

Project: actstat (gh_bbugyi200__actstat)
SASE initialization check

Up to date:
  ok   init config   owner identity is configured as bbugyi200@athena
  ok   init machine  remote machine enrollment review is current
  ok   init memory   memory files are current
  ok   init repo     configured sidecars, project repo config, and ignore rules are current
  ok   init skills   provider skill files are current

Warnings:
  init machine: Pixel 10 Pro XL health probe failed: TimeoutError
  init machine: Kelly’s MacBook Pro health probe returned HTTP 502

Project: bob-cli (gh_bobs-org__bob-cli)
SASE initialization check

Up to date:
  ok   init config   owner identity is configured as bbugyi200@athena
  ok   init machine  remote machine enrollment review is current
  ok   init memory   memory files are current
  ok   init repo     configured sidecars, project repo config, and ignore rules are current
  ok   init skills   provider skill files are current

Warnings:
  init machine: Pixel 10 Pro XL health probe failed: TimeoutError
  init machine: Kelly’s MacBook Pro health probe returned HTTP 502

Project: sase (gh_sase-org__sase)
SASE initialization check

Up to date:
  ok   init config   owner identity is configured as bbugyi200@athena
  ok   init machine  remote machine enrollment review is current
  ok   init memory   memory files are current
  ok   init repo     configured sidecars, project repo config, and ignore rules are current
  ok   init skills   provider skill files are current

Warnings:
  init machine: Pixel 10 Pro XL health probe failed: TimeoutError
  init machine: Kelly’s MacBook Pro health probe returned HTTP 502

Initialization summary: 3 checked, 3 current
```