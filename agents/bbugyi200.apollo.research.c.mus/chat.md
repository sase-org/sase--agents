# Chat History - ace-run (research.c.mus)

- **TIMESTAMP:** 2026-09-25 19:43:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.c.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_193845.md`

## Prompt

%id(mus, clan=research.c)
%m:muse/muse-spark-1.3-contributor@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 4-researcher swarm.
The other researchers, `research.c.cld`, `research.c.grk`, `research.c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Updating
the default values used for sase's size model alias pools (`@medium`, for example) and
models supported by completion in the prompt input widget and external editors (via LSP
support) is painful considering how often we need to do it. I would like to make this
much easier so maintainers can update both of these by updating as few files as
possible/desirable.

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

Research complete. Report written to `sase/repos/research/202609/size_alias_and_completion_model_updates__mus.md` and registered as a durable snapshot (`research:202609/size_alias_and_completion_model_updates__mus.md`, artifact `explicit:17b2aa54905fd377957b7e5c`).

Key findings:

- Size-alias pools already have a single edit point (`src/sase/llm_provider/model_alias_defaults.yml`); tests use a frozen fixture so value-only changes break nothing, and the `docs/llms.md` alias table regenerates via `just fmt-docs`.
- Completion models are already single-sourced per provider (`llm_known_model_names()`), and both the TUI prompt widget and the Rust LSP consume the same Python-built catalog — verified the Rust side hardcodes no model names, so no cross-repo changes are ever needed.
- The real pain is secondary duplication: stale config-comment examples, hand-maintained known-model/short-alias docs tables, exact-slug keys in Claude usage windows, and `retry.claude.fallback_model: "sonnet"` — with nothing failing loudly on drift.

Recommendation: don't centralize provider model lists (would break the plugin-hook contract); instead add a referential-integrity test, generate the remaining docs tables, scrub stale config examples, and publish a short maintainer checklist. Full analysis, inventory, plan critique, and requirement adjustments are in the report.

Final declaration accepted for the research repo commit.
