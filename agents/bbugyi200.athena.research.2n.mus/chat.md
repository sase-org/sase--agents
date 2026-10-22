# Chat History - ace-run (research.2n.mus)

- **TIMESTAMP:** 2026-09-26 14:02:38 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.2n.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_135408.md`

## Prompt

%id(mus, clan=research.2n)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 4-researcher swarm.
The other researchers, `research.2n.cdx`, `research.2n.grk`, `research.2n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to merge the
prompt stash panel with the prompt history panel using sub-tabs on that new, merged
panel.

- Also, I want to add a new, third sub-tab to this panel that contains archived/trashed
  prompts (aka the "stash trash"--this term should be added to the glossary as well as
  "prompt stash" and its alias, "stash") that the user deleted with the `d` keymap on
  the new sub-tab that the prompt stash panel is migrated to.
- We should start moving deleted prompts to this tab instead of deleting them entirely.
- We should only store up to the last `<N>` deleted prompts on this tab (then they
  should actually be deleted).
- `<N>` should be configurable via a new sase config field but should default to 20.
- Appropriate keymaps should be added to this new sub-tab that holds the stash trash.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

Research complete. Report written and registered:

- Report: `sase/repos/research/202609/prompt_stash_history_merge_trash_design__mus.md` (new file, no overwrite)
- Artifact registered: `explicit:c4715ec4894b40ad8ba5ed04` with label `research:202609/prompt_stash_history_merge_trash_design__mus.md`
- Final declaration accepted (commit).

Key findings: the stash is a Rust-owned JSONL store (`sase-core` `prompt_stash/`) behind a Python facade with permanent `d` delete; history is a separate Python-only sharded record with no delete at all — so the merged panel must be a shell hosting the existing panes, not a rewrite. I recommend building trash as `trashed` flags in the Rust store (schema bump) with atomic limit enforcement, a `Prompts` shell with Stash/History/Trash sub-tabs on the `ConfigCenterModal` pattern, Trash keymaps mirroring Stash (`r`/`tab` restore, `d` permanent delete, `D` empty), `ace.prompt_stash_trash_limit` defaulting to 20 (fail-open, `0` = disabled), and two new glossary strands. I also flag that "archive" and "trash" should not be conflated and that `d` on pinned rows needs a guard.
