# Chat History - ace-run (research.l.cld)

- **TIMESTAMP:** 2026-09-28 18:47:13 EDT
- **MODEL:** claude/opus
- **AGENT:** research.l.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_182948.md`

## Prompt

%id(cld, clan=research.l)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.l.cdx`, `research.l.grk`, `research.l.mus`, `research.l.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add
excellent "next-word" prediction for the very next word in the prompt input widget using
the user' / project's prompt history (and maybe just common sense?--think hard about how
to make this work). This would need to be fast and would be triggered using `<ctrl+t>`
after using `<ctrl+t><ctrl+t>` to complete the first / selected word in the completion
menu. This way they can just keep hitting `<ctrl+t>` if the next-words that we guess are
correct.

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

I'm mapping the existing `<ctrl+t>` completion and prompt-history word index, so the report builds on what's already there. Next I'll read the word-completion and soft-completion modules.

Still mapping the existing code: checking what a second `<ctrl+t>` actually does when the menu is open, because the proposed flow depends on it.

Next I'm checking for existing ghost-text rendering (the command line has "Right to accept ghost text") and whether Textual's TextArea supports inline suggestions.

Now checking whether any prompt-word logic already lives in the Rust core (`sase_core_rs`), since the boundary rule may decide where a predictor belongs.

Now comparing today's real `<ctrl+t>` word ranking (run from the repo code) with a context-aware version on a two-letter prefix.

Research is done; writing the report now. First confirming the target filename is free.

Report written. Registering it as a durable artifact.

The report is written to `sase/repos/research/202609/prompt_next_word_prediction__cld.md` and registered as a durable artifact (`file:explicit:45070b8f141931135a4847cd`). The commit is declared for the host to make.

**Verdict:** a good idea, but not as specified. I replayed your real prompt history on apollo (670 prompts, Sept 1–28), training on earlier prompts and scoring later ones word by word.

**Findings:**
- **`<ctrl+t><ctrl+t>` doesn't accept the first or selected word today.** I checked by driving the real widget in a test harness. A second press on an open word menu just re-renders it, and resets the highlight to row 1 if you'd moved it. The chain needs a defined starting point.
- **Two-thirds of the history is machine-generated** (449 of 670, mostly epic phase launches). The model must train only on prompts you typed. Prompt entries also have no project field, but every prompt starts with a `#gh:` tag, so project can be derived from the text.
- **Your phrasing is very repetitive, which n-grams exploit.** 72 of your 219 typed prompts start with "Can you help me". A 4-gram model gets:
  - about 23% first-guess accuracy on genuinely new prompts;
  - 88% on prompts that re-type an earlier one, with correct runs averaging about 11 words;
  - versus about 7% for context-free ranking like today's history-word menu.
- **Inserting the guess before you see it loses keystrokes on new text** (about −7.5% net), because wrong guesses cost an undo. Showing the guess first as dim inline text turns that into about +15% theoretical savings, with shown guesses right 55–64% of the time. Textual's text area already supports this inline text, and the Command Line panel already uses it for history suggestions.
- **The biggest measured win is one you didn't ask for.** Using the preceding words to rank the existing `<ctrl+t>` word completion doubles first-choice accuracy at a 1-letter prefix (18% → 38%). At 2 letters it goes from 39% to 51%.
- **"Common sense" isn't worth it for v1.** A background model trained on the project docs added only +0.7 points. General English mostly predicts short words like "to" and "the". No local LLM runtime is installed, and one would be too slow and heavy per keystroke.

**Requirement changes I'm proposing** (all in the report's §5 table):
- Show the predicted word(s) as dim inline text; `<ctrl+t>` accepts one word and `ctrl+f`/`→` accept all of it (the same split fish uses).
- Make `<ctrl+t>` on an open word menu accept the highlighted row.
- Only show a guess when the model is confident.
- Train on typed prompts only, by adding an "origin" field when prompts are saved.
- Use the project as a boost rather than a filter, since per-project history is small.
- Drop "common sense" from v1.
- Optionally, also show a confident guess right after you type a space, not only after a completion.

**Recommended solution, in order:**
1. Make `<ctrl+t>` on an open menu accept the highlighted row.
2. Build a word-sequence model in `sase-core` (Rust), trained on typed prompts and updated as you submit. Use it immediately to rank current-word completions.
3. Add your chaining feature: after a completion, show the confident next word(s) inline and let `<ctrl+t>` take them one at a time.
4. Add an opt-in mode that shows confident guesses at every word boundary.

I put the model in Rust because of the project's rule that shared completion logic belongs in the core. It also matters for memory: a couple of years of your history would take about 200 MB in Python.

**Caveats:**
- The data covers one machine (apollo) and one month.
- The savings figures are upper bounds that ignore the time spent reading suggestions.
- The evaluation scripts were throwaway files in `/tmp`; the report's appendix has enough detail to rebuild them.
