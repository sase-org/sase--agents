#gh:gh_sase-org__sase The `sase init -a` command seems to iterate over some projects that are not valid, enabled sase projects (see the output below). Can you help me diagnose the root cause of this issue and fix it? #tale
```
❯ sase init -a

Project: actstat (gh_bbugyi200__actstat)
SASE is initialized. No init subcommands need to run.
Checked: memory, repo, skills.

Project: basher
Project inventory warnings:
  active ProjectSpec file not found: /home/bryan/.sase/projects/basher/basher.sase
  WORKSPACE_DIR is not set
init --all: project file is unavailable

Project: bob-cli (gh_bobs-org__bob-cli)
SASE is initialized. No init subcommands need to run.
Checked: memory, repo, skills.

Project: dotfiles
Project inventory warnings:
  active ProjectSpec file not found: /home/bryan/.sase/projects/dotfiles/dotfiles.sase
  WORKSPACE_DIR is not set
init --all: project file is unavailable

Project: sase (gh_sase-org__sase)
SASE is initialized. No init subcommands need to run.
Checked: memory, repo, skills.

Project: symvision
Project inventory warnings:
  active ProjectSpec file not found: /home/bryan/.sase/projects/symvision/symvision.sase
  WORKSPACE_DIR is not set
init --all: project file is unavailable

Project: toobig
Project inventory warnings:
  active ProjectSpec file not found: /home/bryan/.sase/projects/toobig/toobig.sase
  WORKSPACE_DIR is not set
init --all: project file is unavailable

Initialization summary: 3 checked, 3 current, 4 unavailable
```