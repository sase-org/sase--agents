# Chat History - ace-run (research.c.cld)

- **TIMESTAMP:** 2026-09-25 19:50:55 EDT
- **MODEL:** claude/opus
- **AGENT:** research.c.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_193845.md`

## Prompt

%id(cld, clan=research.c)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.c.grk`, `research.c.mus`, `research.c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

Mapping every file a model or alias change has to touch; recent "add model" commits each touched 10–28 files. Next I'll trace where those files come from.

Opening the linked sase-core, sase-nvim, and chezmoi repos to check whether they hold their own copies of model lists.

Found an existing doc generator (`tools/render_model_alias_docs`); checking how much of the docs it covers and what still drifts by hand.

Checking the sase-nvim editor plugin for its own hardcoded model lists.

Reading how the provider-metadata cache is keyed, since moving model lists into a data file changes what the cache needs to watch.

Establishing the base rate: how many commits in the last few months retuned aliases or added models, and which file categories each one touched.

Nearly done mapping; now counting how many tests only restate the catalog data, since those tests force edits on every model bump.

Checking which LLM providers are built in versus external plugins, since that decides whether one central catalog can cover them all.

Quick runtime check of how an unlisted model resolves, then I'll write the report.

I have enough evidence. Glancing at an existing report's header style, then writing mine.

Writing the report now.

Report written. Registering it as a durable artifact snapshot.

Registration succeeded. Submitting the final declaration.

The report is written and registered as an artifact (`file:explicit:0a632663e68c18f80d050cdf`), and the host will commit it to the research repo.

**Report:** `sase/repos/research/202609/model_catalog_update_ergonomics__cld.md`

**The main finding:** the runtime data is already single-sourced. The size-alias pools live in `model_alias_defaults.yml`, and each provider's model list lives in its `llm_known_model_names()` hook. The TUI prompt completion, model picker, Rust LSP and sase-nvim all build their lists from those. Neither the Rust core nor sase-nvim keeps a copy of the model list.

The pain comes from material that is derived from that data but still edited by hand. Across the last ten commits that only changed models or pool values, the median commit touched 13.5 files, split like this:
- **Docs (48%):** hand-kept tables and prose that restate which providers each pool reaches. Only the alias table is generated, and nothing in CI checks that it's current.
- **Tests (29%):** tests that assert exact shipped values and per-model tests. One test even hard-codes the rule that Grok 4.6 continues after Grok 4.7.
- **Example strings:** placeholders, help text and config comments bumped just to look current. The GPT-6 Sol commit touched five source files only for this.
- **The effort-ladder decision record:** it gets edited on each retune, even though decision records are meant to be immutable.

**Critique:** It's a good idea; there were 9 such updates in the last 30 days. I'd change what it optimizes for:
- **Count hand-edited files, not files in the diff.** Regenerated docs showing up in the diff is useful, because reviewers see the user-visible effect.
- **Make the single edit safe.** When tests stop pinning exact values, a validator should enforce the effort-ladder and provider-redundancy rules instead, with messages that say which fix to make.
- **Check that generated docs are current in CI.**
- **Stop bumping examples to the newest model.** An example only needs to name a model that's still listed.
- **Keep removed models usable by name,** hidden from completion, so old prompts don't break.
- **Things I would not do:**
  - Move the model list into sase-core: every model bump would become a two-repo change plus a pin bump.
  - Discover models from the provider CLIs at runtime.
  - Calculate effort levels automatically from the ladder rule.

**Recommended solution:**
1. **One hand-edited manifest, `src/sase/llm_provider/models.yml`.** It holds the built-in model list (IDs, short names, warnings, per-provider defaults, `supersedes`, `status`) and the size-alias pools. The built-in provider hooks read from it, so completion, the picker and the LSP need no changes.
2. **A validator** that checks that pool members exist, their effort levels, the effort-ladder rule (using `supersedes`) and provider redundancy.
3. **One doc generator** that writes every table from the manifest, with a `--check` step enforced in CI.
4. **Tests that read expected values from the manifest** instead of restating them.

After this, a change like the Grok 4.7 commit goes from 19 hand-edited files to 1, with no test or prose edits. If you only do part of it, do the doc generation, test changes and examples policy; that's where most of the files are.

Your chezmoi custom aliases `sol_or_grok` and `opus_or_grok` still pin `gpt-5.6-sol` and `grok-4.6`, a generation behind the shipped defaults. An optional `sase doctor` warning for outdated pinned models would catch this; it's in the report as a possible follow-up.

The report ends with four open questions, starting with whether you want one manifest or two sibling files.
