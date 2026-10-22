# Chat History - ace-run (research.4x.gem)

- **TIMESTAMP:** 2026-10-19 08:12:58 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4x.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_075815.md`

## Prompt

%id(gem, clan=research.4x)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4x.cdx`, `research.4x.cld`, `research.4x.grk`, `research.4x.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently show the selected sase agent's instruction bundle in the file deck.

- I would like to start showing the agent's instruction bundle in a new memory deck
  instead.
- This deck would also include cards for other types of memory (and maybe macros?) that
  the agent used.
- Think hard about what other cards/blocks should be included and whether or not these
  cards actually belong in a different existing deck (the record deck maybe?).

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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Agent Memory Deck Architecture & Design: Research Summary & Recommendations

**Researcher**: `research.4x.gem`  
**Report Artifact**: [`research:202610/agent_memory_deck_architecture_and_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/agent_memory_deck_architecture_and_design__gem.md)  
**Artifact ID**: `explicit:a4aad534fb19610dd196888a`

---

## 1. Executive Summary & Verdict

* **Adopt the Dedicated `MEMORY` Deck (`DeckId.MEMORY`)**: Transitioning instruction bundles and memory reads out of the Files deck into a dedicated Memory deck is strongly endorsed. Structured memory (core notes, reference notes, memory webs) is a foundational pillar of SASE; giving it a first-class deck provides a dedicated surface for the agent's **Cognitive Context**.
* **Reject Storing Bundles in the `RECORD` Deck**: The Record deck is a compact tabular metadata ledger (averaging 15–30 lines per card across Lifecycle, Provenance, Relations, and Links). Injecting a 1,500-line Markdown instruction bundle or multi-page memory read reports creates a severe document-scale impedance mismatch, breaks Record's spread heuristics, and muddles its identity.
* **Purge Bundles from the `FILES` Deck**: Files deck semantics ("*Diffs and files the agent touched*") are violated by host-compiled system instructions. Purging them restores pure git diff / code edit visibility and eliminates false-positive availability signals on read-only runs.
* **Adjust Cycle Position (Move to #2)**: Rather than appending Memory as deck #6 at the far end of the cycle, place `MEMORY` immediately after `MAIN` (`MAIN` $\longleftrightarrow$ `MEMORY` $\longleftrightarrow$ `FILES` $\dots$). Toggling between what the agent generated (`MAIN`) and what it was instructed / retrieved (`MEMORY`) is the highest-frequency contextual leap when debugging.
* **Resolve the Picker Key Collision**: In the `p` (pick deck) modal, `m` is already bound to `MAIN`. Bind `e` (m**E**mory) to the Memory deck, directly mirroring the precedent where `n` was chosen for fi**N**al because `f` was claimed by Files.

---

## 2. Critique of Current State & The Proposal

### The Files Deck Flaw (`sase-1lj.4`)
In commit `552b38f7ed`, `instruction_bundle_pages(agent)` was appended to `desired_file_pages` as an expedient way to inspect `00-bundle.md`. However:
1. **Semantic Violation**: The Files deck is defined as "*Diffs and files the agent touched*". The bundle is an injected host prompt, not an agent edit.
2. **Availability Distortion**: `probe_files_deck()` returns `has_content=True` on read-only agents solely because `00-bundle.md` exists, falsely indicating staged edits.
3. **Paging Friction**: Developers reviewing code diffs must cycle past large Markdown bundles before reaching actual code modifications.

### Why Not the `RECORD` Deck?
The Record deck was evaluated as a candidate home for instruction and memory cards. It is an anti-pattern for three reasons:
1. **Density & Scale Mismatch**: Record cards (`Lifecycle`, `Provenance`, `Relations`, `Links`) are 15-line key-value tables rendered with plain `rich.text.Text`. An instruction bundle is a 1,500-line Markdown document. Cycling cards would jump wildly between 15-line summaries and 1,500-line walls of text.
2. **Spread Heuristics**: Spread mode (`RenderMode.SPREAD`) in Record stacks all cards vertically. Spreading a massive Markdown document across concise metadata cards renders the metadata unusable.
3. **Renderer Purpose**: `RecordView` is an audit fact sheet, not a full-featured Markdown document browser with code syntax highlighting.

---

## 3. Recommended Card Taxonomy for the `MEMORY` Deck

The Memory deck should be implemented as a `CardDocumentView` with the following 4 primary cards (plus an optional 5th coverage card):

```
┌────────────────────────────────────────────────────────────────────────┐
│  ◈ MEMORY DECK                                                         │
├──────────────┬──────────────┬──────────────┬─────────────┬─────────────┤
│ Instructions │ Memory Reads │   Strands    │   Macros    │ [Coverage]  │
│    (Card)    │    (Card)    │    (Card)    │   (Card)    │   (Card)    │
└──────────────┴──────────────┴──────────────┴─────────────┴─────────────┘
```

1. **Card 1: `Instructions` (`bundle`)**
   * **Telemetry Preamble**: Manifest facts from `00-manifest.json` (sequence, provider, attempt, delivery channel, render latency `render_ms`, tokens estimate, byte count).
   * **Integrity Status**: `bytes match` (green) or `MISMATCH` (bold red) with SHA-256 digest.
   * **Root & Helper Blocks**: Root bundle (`00-bundle.md`) as Block 0; helper bundles (`*.helper.md`) as Blocks 1..N, navigable with `[` and `]`.
   * **Body**: Full scrollable, syntax-highlighted Markdown.
2. **Card 2: `Memory Reads` (`reads`)**
   * **Audited Dynamic Reads**: Populated from `memory_reads.jsonl` via `MemoryReadEvent`.
   * **Block Structure**: Each read event forms a titled `CardBlock` with timestamp, producing role label, git blob version chip (`[v3:abc1234]`), and the mandatory reason (`-r "<reason>"`).
   * **Reproduced Content**: In-place rendering of the Markdown content returned to the agent during that read (eliminating the need for popup modals).
3. **Card 3: `Strands` (`strands` / `glossary`)**
   * **Memory Web Lookups**: Keyed strands (`glossary:<term>`, `decisions:<slug>`, `task_types:<slug>`).
   * **Transitive Closure**: Displays the requested term along with its evaluated transitive closure of dependent terms.
4. **Card 4: `Prompt Macros` (`macros`)**
   * **Taxonomy Distinction**: While macros (`src/sase/macros/`) are prompt expansions rather than durable Markdown memory notes (`sase/memory/`), they represent the user-authored half of the agent's prompt context.
   * **Content**: Loaded from `macros.json` via `load_macros_used(agent)`. Displays macro glyphs (`⌘` workflow, `▣` part, `❋` swarm), evaluated positional/named arguments, and template expansion previews.
5. **Card 5 (Recommended Addition): `Coverage` (`coverage`)**
   * **Memory Audit Matrix**: Cross-references project memory against agent execution. Shows which core notes were inlined, which reference notes were read on-demand, and which available memory notes were untouched. Provides immediate root-cause diagnosis when an agent fails to follow an available guideline.

---

## 4. Technical TUI Architecture & Ergonomics

| Attribute | Specification | Rationale |
| :--- | :--- | :--- |
| **Deck Identifier** | `DeckId.MEMORY = "memory"` | Standard enum member in `src/sase/ace/tui/widgets/decks/model.py`. |
| **Deck Name** | `"MEMORY"` | Clean, uppercase convention matching existing decks. |
| **Glyph** | `◈` | Matches `COLOR_MEMORY_GLYPH` established across SASE headers. |
| **Picker Key** | `e` (or `i`) | `m` is taken by `MAIN`. `e` follows the precedent of `FINAL` using `n` (fi**N**al). |
| **Cycle Order** | `MAIN` $\to$ `MEMORY` $\to$ `FILES` $\to$ `TOOLS` $\to$ `FINAL` $\to$ `RECORD` | Minimizes key distance between prompt reply and prompt instructions. |
| **Availability** | `probe_memory_deck()` | Returns `has_content=True` whenever `instruction_bundle_files` is present. |
| **Main Header Cleanup** | Replace modal hint `[1]` with `→ [e] Memory deck` | Streamlines `SASE CONTEXT` into a glance view pointing to the deck. |

---

## 5. Implementation Roadmap

1. **Phase 1: Deck Infrastructure**: Add `DeckId.MEMORY` to `model.py`, register `_DeckSpec` in `spec.py`, update `CARD_DOCUMENT_DECKS` in `card_documents.py`, and implement `probe_memory_deck()` in `availability.py`.
2. **Phase 2: Files Decoupling**: Remove `instruction_bundle_pages` from `src/sase/ace/tui/widgets/file_panel/_file_list.py` and `_agent_detail_files.py`.
3. **Phase 3: Memory Subsystem**: Create `src/sase/ace/tui/widgets/decks/memory/` containing `model.py`, `document.py`, `view.py`, `loader.py`, and cards (`bundle_card.py`, `reads_card.py`, `macros_card.py`).
4. **Phase 4: DeckPanel Mixin**: Implement `DeckPanelMemoryMixin` in `src/sase/ace/tui/widgets/decks/panel_memory.py` and bind it into `panel.py`.
5. **Phase 5: Visual Verification**: Update snapshot tests in `tests/ace/tui/snapshots/test_ace_png_snapshots_agents_deck_views.py` to assert the clean Files deck and record the new Memory deck visual baselines.

The complete research paper with full code listings, architectural comparisons, and test plans is durably preserved at [`sase/repos/research/202610/agent_memory_deck_architecture_and_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/agent_memory_deck_architecture_and_design__gem.md).
