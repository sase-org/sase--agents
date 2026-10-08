# Chat History - ace-run (research.0n.cld)

- **TIMESTAMP:** 2026-10-08 14:13:36 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0n.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_135159.md`

## Prompt

%id(cld, clan=research.0n)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0n.cdx`, `research.0n.grk`, `research.0n.mus`, `research.0n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to make the sase-listen repo a first-class sase plugin.

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

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Still reading code: the CLI parser registry and the completion cache keys. Next I'll check how sase-listen gets installed alongside sase.

Found a key constraint: sase-listen's docs and AGENTS.md record a deliberate "standalone tool, not a sase plugin" decision. I'm reading the plan that made that call.

sase and sase-listen install together without dependency conflicts. Now I'm timing startup and entry-point scans to see whether the design is fast enough.

Confirmed a gap in sase's plugin inventory, and that entry-point metadata scans take about 5ms. Last checks: existing beads about plugin commands, then I'll write the report.

Research is done; I'm checking one detail about global options, then writing the report.

Report written. Registering it as a durable artifact now.

I wrote the report and registered it as `file:explicit:5bb7220439f37390c2c7e681` (label `research:202610/sase_listen_first_class_plugin_commands__cld.md`). The report is committed to the research repo after this turn.

**Verdict: yes, it's a good idea, if it's built as a general way for any plugin to add a command.** The biggest win is one install and upgrade path: `sase update` and the Updates tab replace the hand rollouts behind `sase-1g7.4` and the still-open `sase-1gc`. `sase-listen` also has no shell completion today, so completion is new value.

**Things worth knowing first:**
- **The Updates tab part is already done.** `sase--plugin` is a repository topic, not a label, and it's set. `sase plugin show listen` already lists it as a built-in plugin. What's left is getting the install, the "installed" display and completion right.
- **This reverses a recorded decision.** sase-listen's plan, `AGENTS.md` and docs say "standalone tool, not a sase plugin". That decision's case against a sase dependency (the no-sase-import rule) still holds; the rule against `sase_*` entry points and the topic can be relaxed safely. The `PATH` concern still needs fixing: plugin installs don't put `sase-listen` on `PATH`.
- **Three things will break on a machine with only the plugin install:**
  - The cross-machine feed publish runs `ssh <host> sase-listen feed receive` (`feedhost.py:165`).
  - 57 messages tell users to run `sase-listen …`.
  - The `#research/audio` and `research_swarm` agent instructions call `sase-listen` by name.
- **Parsing `sase listen` arguments with sase's own parser breaks.** I tested it: sase-listen's subcommand overwrites the value sase uses to pick the top-level command (`ns.command == "render"`). Going through sase's full parser would also add about 1 s of startup.
- **Completion doesn't notice installed plugins today.** Its cache only tracks sase and sase-core-rs, and plugin install/update/uninstall never refresh it.
- **Size:** the plugin adds about 180 MB to sase's install, mostly a bundled ffmpeg plus numpy. sase and sase-listen 0.1.1 install together without dependency conflicts.

**Changes I'd make to the requirements (called out as R1–R9 in the report):**
- Define "works exactly like `sase-listen`" as: same arguments, exit codes, output, config and environment; only the program name shown changes.
- Make sase-listen's messages use whichever name it was invoked as, and keep the standalone `sase-listen` working.
- Make the feed publish fall back to `sase listen` when `sase-listen` isn't installed on the remote host.
- Have the research instructions prefer `sase listen`, then `sase-listen`, then `uvx sase-listen`.
- Move each machine to the plugin install, removing the standalone copy on the feed host last.
- Have completion refresh itself whenever plugins change (details in the recommendation below).
- Print an "install with `sase plugin install listen`" hint when the command is used without the plugin.

**Recommended solution:**
1. **New plugin entry-point group, `sase_commands`.** The entry name is the command (`listen = "sase_listen.sase_command"`). It points to a small module in sase-listen with `build_parser(prog)` and `main(argv, prog)`, with no sase imports.
2. **Run plugin commands before sase builds its parser.** Any first word that isn't a built-in command is looked up from package metadata and handed straight to the plugin's own `main()`. That gives exact behaviour at about 50–60 ms extra, and built-in commands pay nothing.
3. **Use the plugin's parser only for help and completion.** Attach it under sase's parser with `parents=[…]`; I confirmed all 12 subcommands show up. Shell completion and the TUI command line then pick it up unchanged, so nothing moves into sase-core.
4. **Refresh completion automatically.** Add the installed plugin commands to the completion cache key (about 10 ms on the first `<TAB>` in each shell), and refresh after every plugin install, update or uninstall. Shells that are already open keep the old completion until restarted.
5. **Updates tab polish.** Add `sase_commands` to the plugin inventory and show "Commands: `sase listen`". Optionally warn when a standalone `uv tool` copy also exists.

The report also compares three alternatives: running `sase-<cmd>` executables git-style, a pluggy registration hook, and keeping sase-listen as a separate tool that the Updates tab manages. The last is the fallback if sharing sase's install ever becomes painful.

It ends with open questions for you:
- Should plugin commands follow sase's short-option rule? 36 of sase-listen's 47 options have no short form.
- Is apollo (the feed host) going plugin-only too?
- Is the extra install size acceptable on the Mac?

I also found a few unrelated issues: sase's plugin inventory lists a retired entry-point group and misses `sase_macros` and `sase_pager_history`, and sase-listen has a dead `cli.py`. I didn't file beads for them, to avoid duplicates across the five researchers.
