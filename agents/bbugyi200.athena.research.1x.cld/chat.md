# Chat History - ace-run (research.1x.cld)

- **TIMESTAMP:** 2026-09-14 12:56:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1x.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260914_124311.md`

## Prompt

%id(cld, clan=research.1x) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1x.cdx`, is independently investigating the same request and will write its
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

I think I want to rename sase's AXE tab to "Schedule" and
make a few other renames as well.

- We should rename "lumberjacks" to "routines".
- We should rename "chops" to "jobs".
- We should replace all references to "AXE" with "sase's scheduler".
- Unrelated, but still a rename: We should rename the `sase ace` command to `sase tui`
  and replace all references to "ACE" with "sase's TUI".

Can you do some research with the goal of critiquing this change? Is it one that you
think I should make? If not, are there better names that you would recommend I use?
Include a concise list of all of the references that would need to be replaced in your
analysis. End your analysis with a set of recommended names you think I should consider. 
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

I've written the report and registered it as an artifact. The end-of-turn declaration was accepted, so the host will commit the file to the research repo.

- **Report:** `sase/repos/research/202609/scheduler_tui_rename_critique__b.md`
- **Artifact:** `file:explicit:67f138a651cac7458c9dc0ce`, label `research:202609/scheduler_tui_rename_critique__b.md`

**Verdict:** make the rename, with one name changed and a limit on how deep it goes.

- **`sase ace` → `sase tui`:** yes. The expansion "Agentic Change Explorer" is out of date now that ChangeSpecs are Patches and the TUI opens on Agents. Nothing is called `sase tui` yet. Don't rename the `sase.ace` package wholesale, though. It also holds changespec, query, patch, hooks and mentors code, so the new name would be wrong for those.
- **AXE → scheduler:** yes. The README already says "AXE schedules" and `docs/mentors.md` already says "the scheduler". Three things to watch:
  - `src/sase/ace/scheduler/` already exists and should be renamed.
  - Users may think "the scheduler" decides when queued agents start. The runner-slots docs already use "scheduler" for that.
  - About a third of `src/sase/axe/` (56 of 155 modules) is agent-runner code, not scheduler code.
  - For the command, use `sase scheduler`, not `sase schedule`. In prose, write "the SASE scheduler" and "the SASE TUI" rather than "sase's …".
- **AXE tab → "Schedule":** acceptable, but I slightly prefer "Scheduler". The tab also starts and stops the daemon and lists background commands that aren't scheduled.
- **Chops → jobs:** yes. `docs/axe.md` already calls them "jobs". The word has minor existing uses: the command palette's `jobs` alias opens the Procs panel, plus `hook_jobs.py`, chat-install jobs and GitHub Actions jobs.
- **Lumberjacks → routines:** I'd skip this one. A "routine" usually means a single automation (Claude Code's own routines are one scheduled agent), but a lumberjack is a supervised process that runs many jobs. "A routine containing jobs" reads backwards. Use **lane** instead: the default config and your chezmoi configs already describe lumberjacks as lanes ("Fast lane…", "audit lane"). Runner-up is "loop".

**What would need replacing:** about 5.7k whole-word "axe" lines, 1.1k "lumberjack", 2.5k "chop" and 19k "ace/ACE" (inflated by `sase.ace` imports). The report's inventory groups them by area:
- CLI commands, flags and your shell aliases.
- The `ace:`/`axe:` config roots, keymap names and your chezmoi configs.
- The chop script and plugin API: 29 `sase_chop_*` scripts, 2 in sase-telegram, the `SASE_CHOP_*`/`SASE_AXE_*`/`SASE_ACE_*` env vars and the `sase.chops` helper package.
- On-disk state: `~/.sase/axe/`, the `ace-run` artifact folders and the `~/.sase/ace_*` files.
- The Rust core, which builds and validates the config, plus the linked plugins, TUI strings, docs, memory notes, glossary and skills.
- 667 TUI screenshot-test images.

Past renames (task → proc, ChangeSpec → Patch) kept the old names working as aliases. Doing the same here needs `sunset` feature flags, and the config-key aliases have to land in sase-core first. I'd leave `ace-run` and `~/.sase/axe/` as internal names.

**Recommended names:**

| Today | Recommended |
| --- | --- |
| `sase ace` | `sase tui` |
| `sase axe` | `sase scheduler` |
| AXE tab | "Scheduler" |
| lumberjack | lane |
| chop | job |
| `ace:` / `axe:` config | `tui:` / `scheduler:` |
| `sase_chop_*` / `SASE_CHOP_*` | `sase_job_*` / `SASE_JOB_*` |
| `sase.chops` | `sase.jobs` |
| `sase.ace.scheduler` | `sase.patch_lifecycle` |
| orchestrator | keep as is |
