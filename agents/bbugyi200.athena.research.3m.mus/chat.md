# Chat History - ace-run (research.3m.mus)

- **TIMESTAMP:** 2026-10-05 06:47:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3m.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_063855.md`

## Prompt

%id(mus, clan=research.3m)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3m.cdx`, `research.3m.cld`, `research.3m.grk`, `research.3m.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about
giving sase macro invocations (`#foo`, for example) a distinct name so it is easier to
talk about / reference them and their unique syntax.

- I think that "sase macro invocation" (aka "smack"--note that "invocation" has the
  sound "kay" in it) is a good name.
- We should add a new glossary memory web strand for this term.
- This opens up new ways of talking about this topic and related topics I think. For
  example, we could start referring to the "raw prompt" as the "smack prompt".

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

Top finding: reject "smack" — standardize on the code's existing term "macro reference" instead.

Done. Wrote independent `__mus` report without consulting peer reports:

- Report: [smack_macro_invocation_naming__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/smack_macro_invocation_naming__mus.md:1) (316 lines)
- Registered: `sase artifact create -p "<absolute-report-path>" -l "research:202610/smack_macro_invocation_naming__mus.md"` → `id: explicit:680ca6a244755086ff6f6022`, exit 0. Source stays in research repo (no `--move`).
- Final declaration accepted for `commit` (research repo).

Summary of recommendation in the report:

- "Smack" fails the prior `xprompt → macro` scorecard: opaque acronym (SMI ≠ smack, "kay" from *invocation*'s `c` is folk etymology), says nothing about mechanism/timing, carries hit/drug-slang tone, fails grammar slots, and churns vocabulary weeks after epic `sase-1eq`.
- No `smack` strand. The real gap is reference vs definition vs expansion drift; `macro reference` already dominates `processor.py`, `prompt_metadata.py`, `content_layout.py`.
- Reject "smack prompt" for "raw prompt": part-for-whole error colliding with three established "raw" senses (submitted text, `AGENT RAW PROMPT` artifact/TUI label, `<label>` placeholders) with a large identifier/docs blast radius.
- Adjusted plan: standardize on "macro reference", defer any strand (if added: keyword `Macro Reference`, slug `macro-reference`), keep raw/submitted/unexpanded vs expanded/launch, document the lifecycle in `docs/macros.md`.

No `just check`: change is inside `sase/repos/research/`, excluded from that gate.
