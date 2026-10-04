# Chat History - ace-run (research.l.image)

- **TIMESTAMP:** 2026-09-28 19:10:40 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.l.image
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_182948.md`

## Prompt

%id(image, clan=research.l) %model:@image
%wait:research.l.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:5e77d167329390c9d4f333f4271f9d1c`

- **Node:** `agent-delta:20260928182954:1f5d76e88226bd25`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260928182954:1f5d76e88226bd25.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.l, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add
excellent "next-word" prediction for the very next word in the prompt input widget using
the user' / project's prompt history (and maybe just common sense?--think hard about how
to make this work). This would need to be fast and would be triggered using `<ctrl+t>`
after using `<ctrl+t><ctrl+t>` to complete the first / selected word in the completion
menu. This way they can just keep hitting `<ctrl+t>` if the next-words that we guess are
correct.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.l.final %m:@xlarge
%wait:research.l.cdx %wait:research.l.cld %wait:research.l.grk %wait:research.l.mus %wait:research.l.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.l.cdx`, `research.l.cld`, `research.l.grk`, `research.l.mus`, `research.l.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

### Assistant

Reading the five researcher reports now (cdx done), then I'll verify the code claims and run my own experiment before consolidating.

Five reports read. Now verifying the disputed code facts myself (ctrl+t on open menu, soft-completion surface, Textual ghost text, ctrl+f binding).

Running the replay experiment now (local-only vs archive+local training, human-typed test prompts only).

Results are in but the top of the output got cut and my chain-run metric was muddled. Fixing the run-length simulation and adding an archive-only variant, then rerunning to a file.

Reports moved into `202609/prompt_next_word_prediction/` (snapshots verified identical). Pulling the remaining chain-start numbers for the weighted variant, then writing the consolidated report.

Before writing, one quick check on undo granularity, since several reports promise "one undo peels one word".

Undo holds up: Textual checkpoints every edit longer than one character, so each `" word"` accept is its own undo step. Writing the consolidated report now.

Layout is complete. Now the final declaration.

I merged the five reports into one, and my recommendation is: **build it, with a few changes.** The report is at `sase/repos/research/202609/prompt_next_word_prediction/prompt_next_word_prediction.md`, next to the five renamed researcher reports. The commit has been handed to the host.

**Recommended solution:** build a local next-word model from your own prompts that only suggests when it's confident. It counts which word followed the last few words in past prompts (an n-gram model).
- **Where it lives:** in `sase-core` (Rust), like the existing Ctrl+K prompt-history filter.
- **Training data:** the prompts you typed yourself, plus the shared prompt archive, with recent local prompts weighted higher.
- **What you see:** the guess appears as dim "ghost" text after the cursor. `<ctrl+t>` takes one word and shows the next guess; `ctrl+f`/`→` take the whole ghost.
- **What doesn't change:** completion for special tokens (`#`, `%`, `@`, paths and so on) and the recent-files menu on whitespace.

**Changes to your plan:**
- **The trigger doesn't work today.** Pressing `<ctrl+t>` a second time on an open word menu doesn't accept the word. It rebuilds the menu and moves the highlight back to row 1. First step: make `<ctrl+t>` on an open word menu accept the highlighted row.
- **You need to see the guess before accepting it.** If `<ctrl+t>` inserts words unseen, fixing wrong guesses costs more keystrokes than it saves on new text (−7.5%, from cld's replay). Showing ghost text first fixes that. Textual's text widget already supports it, and the Command Line panel already uses it.
- **Only guess when confident.** Seed rule: the last 2+ words match past prompts, the word was seen at least 3 times, it's clearly the favourite, and it wins at least 60% of the time. Shown guesses were right about 70–80% of the time.
- **Leave out "common sense" for now.** Adding more or broader text barely helps: about +1–2 points of accuracy. An LLM, local or remote, is too slow for a keypress.
- **Rank the current word by context too.** cld found that using the previous words to rank today's first `<ctrl+t>` completion doubles its accuracy at a 1-letter prefix (18% → 38%). That's the biggest measured win, and it needs no new UI.
- **Train only on prompts you typed.** About 70% of the local prompt history is machine-generated, so prompts need a record of whether they were typed or generated.

**What my own research found:**
- **The shared prompt archive** covers March–September, is mostly written on athena, and holds 50× the text of apollo's single month of history. None of the five researchers looked at it. It only raises accuracy on new text from 24.4% to 26.5%. Its real value is giving a machine with little history (like apollo) a model from the start.
- **Why cdx's numbers looked better:** its test mixed in the machine-generated prompts. cld's numbers and mine agree: about 42% of next words guessed right overall, and 22–26% on new prompts.
- **Chaining only after a completed word gets about 60% of the benefit.** Most words are typed rather than completed. An opt-in mode that shows the guess automatically at word boundaries would get the rest.
- **Memory:** a plain Python version of the model over the full archive used about 180 MB, which is another reason to put it in Rust.
- **The reports got a few facts wrong.** gem said the existing soft completion shows inline; it actually shows in the prompt border. mus worried `<ctrl+t>` conflicts with a full-height toggle; that key only applies in the Command Line panel.

**Expected payoff:** on new text it saves only about 4–9% of keystrokes. On formulaic or re-typed prompts it saves 20–70%. Part of that second case is already covered by Ctrl+K history recall, saved xprompts and snippets.

**Suggested order:**
1. `<ctrl+t>` accepts the highlighted word.
2. The `sase-core` model, the typed-vs-generated record on each prompt, and a replay tool to tune the thresholds.
3. Ghost-text chaining (your feature), and context-aware ranking of the current word.
4. The opt-in automatic ghost mode.

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<source-stem>_infographic.png` in the same directory.


## Response

I’ll use the image-generation skill to turn the consolidated report into a concise infographic. Because the report lives in the research sidecar, I’ll also use the audited repository/artifact workflow, then save the PNG beside the Markdown source.

The infographic will emphasize the decision and interaction loop, with the measured payoff and guardrails kept visible: local 4–5-gram model, confidence gate, ghost preview, one-word acceptance, and no LLM on the keystroke path.

The first file-level inspection didn’t reproduce the visible text layer reliably, so I’m validating the saved PNG itself before registering it.

The saved PNG now passes visual inspection at full resolution. I’m registering a duplicate as a SASE image artifact while preserving the requested source-adjacent file.

The infographic is complete, visually verified, and registered. I’m now handing the sidecar change to the host for commit.

Created the infographic using built-in image generation and saved it here:

[prompt_next_word_prediction_infographic.png](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/prompt_next_word_prediction/prompt_next_word_prediction_infographic.png)

It was registered as artifact `file:explicit:40b8183911b12ba9e2c9ddf0`.

Final prompt: a polished, terminal-inspired infographic covering the local n-gram pipeline, ghost-text controls, measured benefits, guardrails, and Rust recommendation.
