# Chat History - ace-run (research.0n.mus)

- **TIMESTAMP:** 2026-10-08 14:00:23 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.0n.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_135159.md`

## Prompt

%id(mus, clan=research.0n)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.0n.cdx`, `research.0n.cld`, `research.0n.grk`, `research.0n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete and declared.

Top finding: the plan is sound but needs one reframe — `sase listen` must be a hosting of sase-listen's single implementation, not a second implementation kept in parity by hand.

What I verified and wrote up in [plugin_subcommands_sase_listen__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/plugin_subcommands_sase_listen__mus.md) (registered as `research:202610/plugin_subcommands_sase_listen__mus.md`, snapshot `file:explicit:fc59fe2b68704758a9ba15ec`):

- No entry-point group contributes sub-commands today; the static `_COMMAND_REGISTRARS` + `entry.py` dispatch chain needs a plugin hook at three small sites.
- Completion walks the live parser, so plugin commands appear automatically — except the spec cache key ignores installed plugins, so install/uninstall must explicitly invalidate and refresh stamped completions.
- The Updates tab is already catalog-driven off the `sase--plugin` topic, so that requirement is verify-not-build (`sase plugin show listen` does not resolve yet; topic indexing plus `list -r` is pending).
- Recommended solution: new `sase_commands` entry-point group with a light-registration rule (sase-listen's per-module `add_parser` shape fits, but its top-level imports are too heavy for startup), collision/reservation policy, cache-key plus refresh-hook fix, snapshot gate pinned to `SASE_DISABLE_PLUGINS`, and staged sequencing ending in Updates-tab verification.
