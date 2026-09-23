# Chat History - ace-run (0q6--plan)

- **TIMESTAMP:** 2026-09-23 11:58:11 EDT
- **MODEL:** claude/opus
- **AGENT:** 0q6--plan

**Plan:** /home/bryan/.sase/plans/202609/updates_tab_agent_cli_install.md


## Prompt

#gh:gh_sase-org__sase We already have the ability to install agent CLIs from the command-line using the
`sase agent install <provider>` command. Can you now help me add support for installing
these agent CLIs directly from the "Updates" tab of the "SASE Admin Center" panel?

- We should also support selecting multiple agent CLIs from this tab and bulk installing
  all of them at once.
- Think hard about what the best UX for this functionality is.
- Make sure that any new keymaps you add have appropriate keys assigned to them that
  work and do not conflict with other keys in use on that tab.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge %auto

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202609/updates_tab_agent_cli_install.md`

> # Plan: Install agent CLIs from the Admin Center Updates tab
> ## Context: what exists today
> - **CLI installer.** `sase agent-cli install` (`src/sase/agent_clis/install.py`,
>   `src/sase/agent_clis/cli_install.py`) runs only provider-declared **install scripts**.
>   SASE fetches the script, shows its URL, SHA-256, command, and target, asks for
>   confirmation, and runs it without a shell. Today only Muse Code declares a script. The
>   npm-managed CLIs (Claude Code, Codex CLI, OpenCode, Qwen Code, Grok Build) are
>   reported as skips (`declares no SASE-runnable install script; npm install -g …`).
>   Antigravity (`manager: native`) can only be installed manually. Bulk install is not
>   useful while only one CLI can be installed, so phase `npm-installs` adds npm packages

*See full plan file for details.*

