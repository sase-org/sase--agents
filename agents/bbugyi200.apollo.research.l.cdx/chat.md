# Chat History - ace-run (research.l.cdx)

- **TIMESTAMP:** 2026-09-28 18:44:24 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.l.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_182948.md`

## Prompt

%id(cdx, clan=research.l)
%m:codex/gpt-5.6-sol@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 5-researcher swarm.
The other researchers, `research.l.cld`, `research.l.grk`, `research.l.mus`, `research.l.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

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
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
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

I’m using the SASE repo, audited memory-read, artifact, and final-declaration skills because this research touches the TUI and artifact lifecycle and writes into the linked research repository. I’ll independently inspect the current prompt/completion architecture, compare practical next-word approaches against current primary sources, write the `__cdx.md` report without overwrite, then register the exact file as requested.

The governing notes reinforce two key constraints for the recommendation: prompt prediction must stay off latency-sensitive TUI paths, and the artifact command should copy—not move—the report. I’m now tracing the actual input/completion and prompt-history code so the report can recommend an implementation that fits this codebase rather than a generic autocomplete design.

The existing implementation already has most of the plumbing: an off-thread, mtime-keyed prompt-history index (up to 20,000 prompts), in-memory ranking, and a completion panel. But that index deliberately discards word order and duplicate positions, so it cannot answer “what follows this context?”; next-word prediction needs a separate sequence-aware model. There is also a keybinding mismatch worth flagging: today `Ctrl+T` opens/narrows while `Ctrl+F`/`Ctrl+L` accepts, so the proposed repeated-`Ctrl+T` flow is a real interaction change, not merely a new fallback.

A chronological holdout on the local history is encouraging: a simple 5-word-context backoff model reached 34.6% top-1 overall, while abstaining unless evidence was strong raised precision to 76.5% at 30.6% coverage. Half of successful starting points continued for at least two correct words, so the repeated-key interaction has real leverage—but only with confidence gating and a clean chain state. I’ll capture those results as directional (not a product promise) and recommend an on-device personalized n-gram MVP, not a hot-path LLM.

The report is written and passes a whitespace/diff sanity check. Its recommendation is a project-aware 1–5-gram Rust-core model with conservative abstention and a word-only repeat-`Ctrl+T` state machine; it also documents the current keybinding/whitespace conflicts, privacy constraints, benchmark method, alternatives, and rollout metrics. I’m registering the exact file now as the durable `research:` snapshot.

Research completed and registered successfully.

- Report: [prompt_next_word_prediction__cdx.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/prompt_next_word_prediction__cdx.md)
- Artifact: `file:explicit:1193148f9be1cd7271236487`
- Label: `research:202609/prompt_next_word_prediction__cdx.md`

Core recommendation: implement a local, project-aware, confidence-gated 1–5-gram predictor in `sase_core`, with repeated `Ctrl+T` chaining limited to word completions. Defer general or remote LLM integration until measured evidence justifies it.
