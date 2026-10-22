# Chat History - ace-run (research.3n.grk)

- **TIMESTAMP:** 2026-10-05 07:09:13 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3n.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_065248.md`

## Prompt

%id(grk, clan=research.3n)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3n.cdx`, `research.3n.cld`, `research.3n.mus`, `research.3n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the SASE.md agent-instruction migration independently and write a `__grk.md` report. First I'll load the required skills and inspect the current instruction architecture.

I'll skip the coordinator deep-research loop and research this myself. Next I'll inventory repos, open the research sidecar, and map how agent instructions are generated today.

Research sidecar is already in this workspace. I'll open it formally, then pull the budgeted-router paper and the instruction-generation code.

The budgeted-router paper is prior research, so I’ll read that plus the current instruction-generation pipeline and skip this swarm’s peer reports.

The dirty-tree problem if we rewrite instruction files at launch is a real constraint. Next I’ll map provider load paths, tribes, and the current generator.

I have a verified load-surface matrix and a recommendation. Next I’ll write the report under a unique `__grk.md` name and register it.

**Build a launch-time instruction projector. Keep committed `AGENTS.md`. Do not add a root `SASE.md` or a `%tag` directive.**

The report is `sase/repos/research/202610/launch_time_instruction_projection__grk.md`, registered as `research:202610/launch_time_instruction_projection__grk.md`.

The request is right about the last mile: SASE already compiles memory into `AGENTS.md` and already knows the provider at spawn. What each CLI actually concatenates is accidental, and that is what produces the Grok double-load and the Codex-home miss.

The proposed vehicle is the wrong one.

- `sase/memory/` is already the source spec. A root `SASE.md` collides with `sase/memory/sase.md` and is invisible to every vendor CLI.
- `AGENTS.md` is the cross-tool standard. Unmanaged `sase tmux-agent` sessions and a bare clone still need it.
- `%tag` was retired for `%tribe`. Launch context already has provider, kind, clan, tribe, and alias.
- Overwriting tracked shims dirties git. Grok also concatenates tracked `CLAUDE.md`; `.gitignore` cannot hide it.

A load-surface fact that changes the design: workspaces live under `$HOME`, so `~/CLAUDE.md` sits on Claude’s ancestor walk. Claude’s AGENTS.md fallback never fires. Deleting project `CLAUDE.md` would make Claude SASE agents load home instructions only. Grok never reads `~/AGENTS.md` at all (`~/.grok/` is its global). Codex only sees home via `$CODEX_HOME`. Home union belongs in the projector.

**Recommendation, in order:** (1) projector in the adapters that presents exactly the files/flags/shadow-home entries this CLI will load once, untracks shims, and reconciles reused workspaces; (2) the already-specified budgeted-router renderer work, independently; (3) optional `when:` / Jinja facets on `{provider, kind, clan, tribe, alias}` for audience-specific body text.
