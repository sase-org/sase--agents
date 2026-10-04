# Chat History - ace-run (research.l.gem)

- **TIMESTAMP:** 2026-09-28 18:38:01 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.l.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_182948.md`

## Prompt

%id(gem, clan=research.l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.l.cdx`, `research.l.cld`, `research.l.grk`, `research.l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Research Report Completed: Next-Word Prompt Prediction in SASE TUI

The research report has been written and registered as a durable artifact snapshot.

- **Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/prompt_next_word_prediction__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/prompt_next_word_prediction__gem.md)
- **Artifact Ref:** `file:explicit:15daf050695441ae1c6f3e94`
- **Label:** `research:202609/prompt_next_word_prediction__gem.md`

---

## Key Findings & Synthesis

### 1. Critique of the Proposed Plan: Is it a Good Idea?
**Verdict:** The core intuition is strong—developer prompts for agents exhibit high repetition across command invocations (`just check-full`, `sase bead create`), standard directives (`Please verify that...`), and parameter flags (`-p ... -l ...`). However, the proposed interaction model and unconstrained word-by-word generation have significant pitfalls:

1. **Blind Buffer Insertion Fails on Inevitable Errors**:
   - If pressing `<ctrl+t>` blindly writes a predicted word directly into the document buffer, any incorrect prediction corrupts the prompt text and forces the user to stop, backspace, and re-type. This completely breaks typing momentum.
2. **The Single-Word Perceptual Bottleneck**:
   - In HCI cognitive modeling (GOMS/KLM), human verification latency (reading text on screen and verifying correctness) takes ~200–350 ms. Fast typists type at ~100–150 ms per character/short word. Requiring the user to verify and press `<ctrl+t>` 5–6 times for generic words (*"in"*, *"the"*, *"file"*, *"under"*, *"the"*) is actually **slower than typing**. Value comes from predicting **multi-word phrases, command sequences, and domain arguments**.
3. **Keybinding Collisions with SASE TUI Conventions**:
   - In [`PromptTextAreaKeyHandlingMixin`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/widgets/_prompt_text_area_key_handling.py#L390), `<ctrl+t>` currently triggers manual prefix completion. Once the menu is open, `<ctrl+f>` / `<ctrl+l>` accepts candidates; pressing `<ctrl+t>` again does not currently accept.
   - At whitespace (empty token prefix), `<ctrl+t>` currently invokes [`_try_file_history_completion()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/widgets/_file_completion_open.py#L521) (recent file references). Re-using `<ctrl+t>` for next-word prediction requires an explicit, disambiguated modal state machine.
4. **Corpus Sparsity & The "Cold Start" Deficit**:
   - Unlike generic web text, user prompt histories contain only hundreds to low thousands of entries. Pure n-grams over history alone will fail frequently on new projects or novel tasks.

---

### 2. Operationalizing "Common Sense" at Keystroke Speeds (<1 ms)

Evaluating candidate architectures against the strict sub-millisecond latency requirement of terminal typing:

| Approach | Latency | Memory | Quality / Common Sense | Fit for SASE |
| :--- | :--- | :--- | :--- | :--- |
| **Local SLM (ONNX/GGUF)** | 25–70 ms | 300–800 MB | High semantic fluency | **Rejected**: Too slow for 60 FPS TUI frame budgets; bloats package distribution. |
| **Cloud LLM Streaming** | 300–1500 ms | Minimal | Superior | **Rejected**: Far too slow for synchronous keystroke chaining. |
| **Unigram Bag-of-Words** ([`PromptWordIndex`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/history/prompt_word_index.py#L56)) | < 0.5 ms | < 5 MB | Zero sequential awareness | **Rejected**: Measures co-occurrence, but has no concept of sequential word order. |
| **3-Tier Statistical N-Gram Engine** | **< 0.5 ms** | **10–20 MB** | Excellent for commands & idioms | **Recommended**: Sub-millisecond, deterministic, lightweight, zero external dependencies. |

**How "Common Sense" Works Without a Neural Net:**
We ground "common sense" in a 3-tier interpolated statistical model (Modified Kneser-Ney / Jelinek-Mercer smoothing):
- **Tier 1 (Project History, Weight ~0.50):** N-grams from prompts matching the active project via [`PromptHistoryProjectCatalog`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/history/prompt_history_project_filter.py#L81) and VCS tags (captures local targets, paths, branches).
- **Tier 2 (Global User History, Weight ~0.30):** N-grams across all historical shards in `~/.local/state/sase/prompt_history/` (captures personal instructions and style).
- **Tier 3 (Domain Common Sense Prior, Weight ~0.20):** A static, embedded table of ~5,000 software engineering collocations (git command sequences, testing idioms, markdown structures, prepositions). This guarantees intelligent suggestions even on day 1 of a brand-new project.

---

### 3. Recommended Adjustments to Requirements

1. **Ghost Text Preview (Soft Completion) over Blind Insertion:**
   - Predictions should project as subtle, non-disruptive ghost text at the cursor (using SASE's existing [`PromptSoftCompletionMixin`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/widgets/_prompt_soft_completion.py#L58) infrastructure).
   - Pressing `<ctrl+t>` accepts the ghost word and projects the next. Normal typing ignores and dismisses the ghost text without polluting the buffer.
2. **Dual-Granularity Acceptance (Word vs. Phrase):**
   - Keep `<ctrl+t>` for word-by-word advancement, but provide an accelerator (`<ctrl+l>` / `<ctrl+f>`) to accept the entire multi-word predicted phrase when confidence is high.
3. **Short-Word Vocabulary Retention:**
   - Unlike `PromptWordIndex` (which enforces `min_length >= 5` to filter out short words for prefix search), the next-word prediction index must retain 1–4 character words (`in`, `to`, `for`, `git`, `pr`, `ci`, `run`, `fix`) as they are essential syntactic glue.
4. **Explicit 4-State Machine for `<ctrl+t>`:**
   - `IDLE` (inside a word): `<ctrl+t>` opens completion menu.
   - `MENU_OPEN`: `<ctrl+t>` accepts highlighted item, closes menu, inserts trailing space, and transitions to `CHAINED_PREDICTION`.
   - `CHAINED_PREDICTION`: `<ctrl+t>` accepts ghost word and updates the prediction chain.
   - `WHITESPACE_STANDALONE`: If prior text exists on line, shows next-word ghost text; if line is empty, opens file history.

---

### 4. Implementation Architecture (Rule 1.3 Compliance)

In accordance with SASE Rule 1.3 (*Rust Core Backend Boundary*), core prediction and indexing logic belongs in the Rust backend:
- **`sase_core::prompt_prediction` (Rust in `sase-core`)**:
  - Implements sequential tokenization, n-gram trie, Kneser-Ney smoothing, and embedded domain priors.
  - Exposed via PyO3 to `sase_core_rs`.
  - Reusable across the TUI, `sase-nvim` (Neovim LSP), and CLI.
- **`sase.ace.tui` (Python)**:
  - Connects `PromptTextAreaKeyHandlingMixin` and `PromptSoftCompletionMixin` to render ghost text and dispatch `<ctrl+t>` / `<ctrl+l>` state transitions.

The SASE finalizer declaration has been successfully submitted and accepted for the commit obligation in `sdd:research` (`202609/prompt_next_word_prediction__gem.md`).
