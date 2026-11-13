# Chat History - ace-run (research.4k.cld)

- **TIMESTAMP:** 2026-11-13 17:58:37 EST
- **MODEL:** claude/opus
- **AGENT:** research.4k.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261113_174022.md`

## Prompt

%id(cld, clan=research.4k)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4k.cdx`, `research.4k.grk`, `research.4k.mus`, `research.4k.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support to sase for Google's new Argon and Hydrogen models.

- We should update all model completion surfaces to include these models.
- As a part of this change, we should update the `#research_swarm` macro to use the new
  Hydrogen model instead of the current Gemini model that we use for that macro swarm.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm surveying the existing model catalog (Argon was already added to the `agy` provider in October) and will next do web research on Google's Argon/Hydrogen release.

Tracing which code paths feed model completion (TUI picker, directive completion, macro `model` inputs) so I can tell which surfaces update automatically from `models.yml`.

Checking the remaining surfaces: shell/CLI completion, sase-nvim, and sase-telegram for any hard-coded model lists.

Only one hand-maintained keyword list exists in sase (`short_model_name`). Quickly checking sase-nvim and sase-telegram for hard-coded model lists.

Mapping the test and doc blast radius of a `models.yml` change so the recommendation can list concrete files.

I have what I need. Writing the report now; first confirming the target filename is free.

Report written and registered; submitting the commit declaration for the research repo.

The report is written and registered as an artifact (`file:explicit:bae7e0518f144167fef457c8`). The host will commit it to the research repo after this turn.

**Report:** `sase/repos/research/202611/gemini4_argon_hydrogen_support__cld.md`

**Findings**
- **Argon is already in sase.** It was added to the `agy` (Antigravity) model list in October. Its "needs Google AI Ultra" warning is now wrong: Antigravity also offers Argon on paid Google AI Pro.
- **Hydrogen came out yesterday and is not in sase yet.** This machine's `agy` already lists `gemini-4-hydrogen-{xhigh,high,medium,low}`. I ran `gemini-4-hydrogen-xhigh` on a trivial prompt and it worked.
- **Most completion surfaces update automatically.** They all read `src/sase/llm_provider/models.yml`: `%model` completion, macro `model` arguments, the model picker, the editor language server, short names, and the generated docs.
  - The agent-list label needs one manual edit: add `"hydrogen"` to the keyword list in `short_model_name`, or Hydrogen rows show as `gemini`.
  - Shell `--model` completion never lists concrete models for any provider, so it won't show Hydrogen either.
- **`#research_swarm` is defined in the `sase-research-artifacts` plugin, not in sase.** The current Gemini model, `agy/gemini-3.8-flash-high`, appears twice: as the `gemini_model` default and in the `@image` alias pool.
- **Bare `agy` launches are broken today.** The default `agy` models, `gemini-3.7-flash-high` and `-low`, are now Enterprise-only, and `agy` rejects them on this account ("not recognized"). Any launch that falls back to an `agy` default fails.
- **`agy` 1.5.8 now has a working `--effort` flag**, though sase still treats `agy` as having none. A suffixed name plus a conflicting `--effort` is rejected, as is a level the model lacks.

**Recommended solution**
1. **sase commit:**
   - Add the four Hydrogen models to `models.yml` right after Argon, with short names `hydrogen4x`, `hydrogen4h`, `hydrogen4m`, `hydrogen4l`.
   - Fix the Argon warning to "needs Google AI Pro or Ultra".
   - Move the `agy` defaults to Gemini 3.8 Flash high/low, which every plan can use.
   - Add `"hydrogen"` to `short_model_name`, update the tests, and run `just fix` to regenerate the docs.
2. **Plugin commit:** set the `gemini_model` default to `agy/gemini-4-hydrogen-xhigh`. I suggest changing the `@image` pool's `agy` model too, but that's your call. The plugin doesn't need a newer minimum sase version, so the two commits can land in either order.
3. **Separate follow-up tasks, not part of this change:**
   - Using `agy --effort` instead of baking effort into the model name.
   - Adding Gemini 4 Carbon and the Orchestrator (`gemini-pro-orchestrator-g1-pro`).
   - Refreshing the `agy` list: add Claude 5.5, drop Claude 4.6 and GPT-OSS when Google removes them on Nov 18.
   - Fixing the remaining `gemini-3.7-flash` references in `sase/macros/reads.md`, the docs, and your chezmoi snippets (`m_agy*`, `m_swarm`, `tmux_ai_window`), which no longer work on this account.
   - Optionally, adding concrete models to shell completion.

Moving the defaults to 3.8 Flash goes beyond what you asked. I'm recommending it because it's the same block of `models.yml` and fixes something broken today. I chose 3.8 Flash over Hydrogen because sources disagree on whether free accounts get Hydrogen in Antigravity, and 3.8 Flash is available on every plan.

Sources:
- [Antigravity: Choose a model](https://antigravity.google/docs/models/)
- [Antigravity CLI effort docs](https://antigravity.google/docs/cli/commands/effort)
- [Antigravity blog: Hydrogen and Orchestrator](https://antigravity.google/blog/gemini-4-hydrogen-in-google-antigravity)
- [Google: Introducing Gemini 4 Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- [Gemini API models](https://aistudio.google.com/docs/models)
- [Google: Gemini 4 Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/)
- [InfoWorld](https://www.infoworld.com/article/4248403/google-adds-multi-model-orchestrator-gemini-4-hydrogen-to-antigravity.html)
- [9to5Google](https://9to5google.com/2026/11/12/gemini-4-hydrogen-launch/)
- [The Decoder](https://the-decoder.com/googles-gemini-4-hydrogen-outscores-the-bigger-argon-just-four-weeks-after-its-launch/)
- [SiliconANGLE](https://siliconangle.com/2026/11/12/google-releases-gemini-4-hydrogen-a-lower-cost-model-said-to-outscore-argon/)
- [gHacks](https://www.ghacks.net/2026/11/13/google-releases-gemini-4-hydrogen-in-search-and-the-gemini-app-replacing-gemini-3-8-flash/)
- [MarkTechPost](https://www.marktechpost.com/2026/11/13/google-gemini-4-hydrogen/)
