# Chat History - ace-run (research.3n.mus)

- **TIMESTAMP:** 2026-10-05 07:00:36 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3n.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_065248.md`

## Prompt

%id(mus, clan=research.3n)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3n.cdx`, `research.3n.cld`, `research.3n.grk`, `research.3n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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

Research complete.

Report written to `sase/repos/research/202610/sase_md_unified_instruction_spec__mus.md` and registered as `research:202610/sase_md_unified_instruction_spec__mus.md` (artifact `explicit:90c16a035b72fc7aceba5a53`). Final declaration accepted for commit.

Bottom line: yes, unify behind a single authored source plus a deterministic renderer — but single-sourcing alone fixes neither cited bug. The Grok double-load and Codex home-gap are emission problems (what files land in the workspace), so the renderer needs commit-time and lease-time call sites conditioned on a closed provider axis. I recommend against `%tag`: `%`-directives are run-time prompt modifiers, agent identity is ephemeral, and free-form tags explode the surface matrix. Use fenced conditional blocks keyed on provider (later role), with per-surface budget enforcement, provenance headers, and a tested provider load-set table.
