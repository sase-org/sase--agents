# Chat History - ace-run (research.g.grk)

- **TIMESTAMP:** 2026-09-26 16:02:42 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.g.grk
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_154839.md`

## Prompt

%id(grk, clan=research.g)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 4-researcher swarm.
The other researchers, `research.g.cdx`, `research.g.mus`, `research.g.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make it
easier to set file hooks for artifact files by using a more robust and reliable approach
to matching artifact files.

- I was thinking that we could maybe achieve this by having the `#research` xprompt set
  an environment variable by default.
- We would need to support an override for this as well (e.g. by adding a new input
  argument to the `#research` xprompt) to not set this environment variable in some
  cases (we will need to set this override for all of the researcher agents that run
  before the lead researcher agent in the `#research_swarm` xprompt swarm, for example).

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

I'll research independently and form my own recommendation. First I need the SASE research/xprompt/hooks surface and the write location, without looking at the other swarm reports.

I'll map the current xprompt, file-hook, and artifact matching machinery next, then judge whether an env-var default is the right lever.

The research-artifacts plugin and file-hook matching look like the core of this. I'll open those repos and pull glossary plus the current `#research` xprompts.

The current hook already excludes swarm reports by filename and agent name; next I’ll inspect the plugin, xprompt env plumbing, and how artifact events are matched.

The hook currently excludes swarm drafts by filename and agent-name globs. I'll inspect matching, xprompt `environment`, and artifact-create dispatch next.

I have enough to write the report: the env-var idea is the right policy, but matching has to be captured event metadata plus the original source path.

The report is registered. Next I’ll submit the turn’s finalizer declaration so the research sidecar write is committed.

The env-var override is the right **policy** for swarm drafts versus a normal `#research` write. It is not a complete matching design, and it does not unlock artifact-time file hooks on its own.

**Recommendation:** treat `#research` as the place that *defaults* hook intent, then match on **captured event metadata** and run the hook against the **original sidecar file**.

What the current machinery actually does:

- `#research` is a markdown xprompt. Markdown xprompts cannot set `environment:`; only YAML workflows can. Converting `#research` to YAML is the supported way to inject a variable.
- File-hook matching has no environment filter. It matches project, sidecar, path globs, agent-name globs, op, cause, and producer. Live `os.environ` is not consulted, and the detached hook runner would not see the agent’s env anyway.
- `research-highlights` already excludes swarm drafts with `!20*/*__*.md` plus `!research.*.cdx` (and the other researcher shorts). Artifact events already match on the **original** repo-relative path.
- Artifact dispatch is skipped because the **command argument** is the stored copy (`<stem>-<12-hex>.md`). Bob Highlights derives PDF basename and marker id from that basename. That is why `producers` is `[commit, sdd, finalizer]`.
- `#research_swarm` researchers call `#research(suffix=…)`. The lead does not call `#research`, and it registers the consolidated report only when `critique=true`. A default-on env on `#research` never reaches the lead.

**Do this:**

1. Host: for artifact events, pass the original source path into the hook command when it still exists (`#research` already forbids `--move`). Dedup against the later commit of the same `rel_path`.
2. Plugin: add `artifact` to `research-highlights` producers. Existing path and agent vetoes already drop drafts.
3. Convert `#research` to YAML with `file_hook` (bool, default `true`) setting `SASE_FILE_HOOK_INTENT=research-highlights`. Capture empty as “no intent.” Swarm researchers call `#research(suffix=…, file_hook=false)`.
4. Only after the lead is stamped (and intent is copied onto `agent_meta.json` for commit capture) consider `filters.intents` as a required match dimension. Keep the `__<suffix>` path veto.

Keep the swarm opt-out at the call site. Do not match live environment variables, and do not enable the `artifact` producer without original-path dispatch.

Full analysis: `research:202609/artifact_file_hook_matching_via_research_env__grk.md`

Registered snapshot: `file:explicit:5e9b960a00809430c8172b84` (label `research:202609/artifact_file_hook_matching_via_research_env__grk.md`). The source file remains in the research repo.
