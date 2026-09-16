# Chat History - ace-run (research.20.cld)

- **TIMESTAMP:** 2026-09-16 12:55:42 EDT
- **MODEL:** claude/opus
- **AGENT:** research.20.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260916_123435.md`

## Prompt

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
improvements but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Exploring the codebase now — AXE's command, its TUI tab, procs, the gateway, and the Telegram receiver. I'm sending out several search agents in parallel.

I'm reading earlier naming research on the AXE→Supervisor rename, since it affects which terms to propose.

Next I'm checking specific facts: which procs the gear icon counts, how config layers work, how `sase init` handles machine-wide steps, and how bgcmds end.

Checking the live gateway units on athena and apollo (read-only).

Checking how the Telegram receiver exits when disabled, since that shapes the restart-policy design.

Now checking primary docs for systemd, launchd, and linger behavior.

Research is nearly done: I've confirmed the Telegram receiver currently counts toward every TUI's gear icon. Checking the `sase init` step registry, then writing the report.

Writing the report now.

Fixing a few claims I didn't verify myself before registering the report.

Now registering the report as an artifact.

Registration worked. Now the final declaration step.

I wrote the report and registered it as `research:202609/sase_service_host_and_service_procs__b.md` (ref `file:explicit:8f8c6f6b86ab29162af489ab`); the host will commit it to the research repo. My verdict: the idea is worth pursuing as a multi-phase epic, but the requirements need some changes first.

## Why it's worth doing
The code and your live machines already work around problems this would fix:
- **AXE doesn't start at boot.** A TUI starts it (`sase tui --restart-axe`) inside a temporary systemd scope.
- **The gateway runs from a hand-copied unit** on both athena and apollo. The unit is missing the `--agent-bridge-command` flag the docs recommend. Its `network-online.target` dependency also does nothing, because that target doesn't exist for user units.
- **The Telegram receiver only stays alive because a 5-second job keeps re-submitting it.** Core code checks for the plugin's private origin string so the receiver doesn't block TUI restarts. The receiver also currently counts toward the gear icon in every TUI session.
- **macOS has no service support at all.**
- **Background commands don't record exit codes**, and re-running one skips the durable path.

## One constraint you probably haven't hit yet
On athena, the agent runners that jobs launch (and the Telegram receiver) run inside the AXE systemd scope. If `sase service` becomes a systemd unit with default settings, every `sase update` or `sase service restart` would **kill in-flight agents and background commands**. Anything meant to outlive the host must be launched in its own transient scope on Linux. On macOS the fix is `AbandonProcessGroup=true` plus a new session. The existing `systemd_scope.py` is a good starting point, and this fix is worth shipping even without the rest.

## Requirement changes I'd call objective (the report lists all 12)
- **Show disabled service procs as dimmed nodes.** Otherwise you can't select one to enable it from the tab.
- **Define "stop" versus "disable".** Stop lasts until start or reboot; disable lasts on this machine.
- **Give service procs a restart policy where a clean exit means "stay down", plus start conditions.** The Telegram receiver deliberately exits 0 when Telegram is disabled, so "always restart" would make it flap.
- **Add a real `service` marker to proc records and a `service` filter to the Procs query language.** Today `-service` is a plain-text exclusion that hides nothing useful.
- **Make `sase supervisor start/stop/restart` go through the host**, and retire the `ensure` timer and the TUI's direct start. Two things restarting the same process will race.
- **Build `sase service init` as a normal plan/apply `sase init` step.**
  - It should detect the old units (the gateway unit holds port 7629) and check the systemd setting that lets user units start at boot without a login.
  - It should remember when the user declines.
  - "Prompt only once with `-a`" should generalize the existing machine-step special case rather than adding a second one.
- **Make the Procs tab's `-service` prefill a config value** rather than hardcoding it.

## Judgment calls (flagged as such in the report)
- **Reconsider "Supervisor".** In supervisord and runit, the supervisor is the program that runs services, which would be `sase service` here. The word is also already used for the per-proc supervisor process in about 218 lines of code, in Rust wire fields, and in the Sase Monitor glossary entry. I recommend "Scheduler", as the earlier naming research did.
- **Label the tab "Services"** to match the plural "Agents" and "Artifacts".
- **Model background commands as transient oneshots.** A oneshot runs to completion; transient means it was created at runtime rather than from config.
- **Ship the gateway disabled by default.** Enable it on athena and apollo through their machine-specific config files.
- **Hold off on a Python plugin API.** A plugin can already add entries through its existing config layer, and Telegram needs nothing more.

## Recommended solution
- **One host process per machine** (`sase service run`), registered as a single systemd user unit or launchd LaunchAgent. If no unit is installed, it runs detached.
- **Long-running service procs are the host's direct children**, reusing the restart and crash-loop logic extracted from the AXE orchestrator.
- **Oneshots go through the existing detached proc path**, so restarting the host doesn't kill them.
- **Every run is recorded in the proc store.** The config schema, state, status format and restart decisions live in sase-core.
- **Config is a `service.procs` map merged by name across layers.**
  - A simple proc is just `command:`; core ones use `builtin:`.
  - Disabling on one machine is one line in that machine's config file (`enabled: false`).
- **The Services tab** shows the scheduler's routines and jobs nested under its node, and oneshots in their own section with exit codes.

The report also includes:
- the proposed wording for five new glossary entries and five edits (to land only once the feature ships);
- the full CLI layout;
- the systemd unit and launchd plist;
- an 8-phase rollout;
- a migration runbook for athena and apollo;
- a smaller fallback (fixed units for AXE and the gateway only) if the full epic is too big right now.
