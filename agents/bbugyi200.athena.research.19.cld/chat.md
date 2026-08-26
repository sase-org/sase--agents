# Chat History - ace-run (research.19.cld)

- **TIMESTAMP:** 2026-08-26 16:51:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.19.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260826_163203.md`

## Prompt

%id(cld, clan=research.19) %m:@research_b  #gh:gh_sase-org__sase I've had the ambition to create a custom sase pager for a
while.

- We recently implemented a custom pager for the `sase bead show` command, which makes
  me think now might be a good time to do this.
- We should make sure that we use the same pager for the `sase bead show` command that
  we do for this new, enhanced pager.
- We should add a new `sase <subcmd>` command (use your best judgement for the
  `<subcmd>` sub-command name) that allows the user to interact with this feature from
  the command-line somehow. I'm not sure of how to make this useful. Think hard about
  this. If its genuinely not needed/useful don't add the new `sase <subcmd>` command
  (but provide your reasoning).
- As our first new use-case, the `v` keymap on the "Agents" tab should start to use this
  as its pager instead of what we use now.
- This pager should support the `<ctrl+n/p>` keymaps to jump to the next/previous entity
  (e.g. file, bead, etc...). By "jump to", I mean re-draw the contents with that file's
  header at the top of the screen.
- We should also support single-keypress navigation to traverse links to refs and really
  anything that the `v` keymap supports rendering hints for currently (if genuinely
  useful).
- The keys associated with each link should be rendered ahead of time (using `0-9`, then
  `a-z`, then `A-Z`, then `00-ZZ` (we shouldn't need to resort to multiple keys often,
  but make sure we support this just in-case).
- We should support both artifact refs (see the sase-ug epic bead, mentioned below, for
  some current context on these) and regular file paths and everything else that the `v`
  keymap on the "Agents" tab supports (within reason).
- Make sure link traversal leaves great breadcrumps that the user can see and are
  visually appealing. The user should be able to use the `<backspace>` keymap to jump
  backwards through this breadcrumb trail.
- Review the sase-ug epic bead, which is in-progress, prior to deciding on your solution
  to make sure this work aligns with that epic's work (where applicable, if at all).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the current state of the codebase.

Now I have a complete picture. Let me write the research document.

Research written to `sase/repos/research/202608/sase_pager.md` (691 lines).

## What I found

**SASE already has four pagers, and none of them is a pager.** `cli_pager.page_or_print` (bead show), `artifact_cli/read.py:_print_or_page`, `hints/_files.py:_view_files_with_pager` (the `v` keymap's `bat | less`), and `graphics/_viewer_loop_media.artifact_text_viewer_command` — four call sites, four flag sets, zero shared contract. `cli_pager.py` is the newest and best front door and the wrong back end.

**More importantly: six-sevenths of this pager already exists in the tree.** `ctrl+n`/`ctrl+p` for next/prev entity is already the house idiom (`ZoomPanelModal`, `CommitViewModal`). `GlossaryPreviewModal` already does single-key link following with a `backspace` history stack. `memory_panel_travel.py` already has a bounded 32-entry trail; `trail_strip.py` already renders `TRAIL A › B › C` with elision. `VimSearchController` is already a reusable `/`-`n`-`N` controller re-hosted twice. And `MemoryReviewTuiApp` already proves the exact launch pattern needed: a standalone Textual app run both from a CLI subcommand and from inside ACE under `suspend()`. This is mostly consolidation, not invention — which changes the risk profile and the sequencing.

## What decided the design

I measured 2,422 local plan/research documents:

| | |
|---|---|
| Links per document | p50 **17**, p90 **51**, p99 97, max 187 |
| Links per 45-line screen (12,845 windows) | p50 **3**, p90 10, p99 21, max **46** |
| Docs fully covered by a 51-key alphabet | **90.2 %** |
| Docs whose *worst screen* exceeds 51 keys | **0.0 %** |

Your requested alphabet is exactly right, confirmed rather than assumed. Reserving the vim command keys (`j k g n q y o h G N Y`) leaves 51 single keys, which cover 90 % of documents end to end; `00`–`ZZ` becomes a real but rare tail used only past link ~50, allocated prefix-free so a label can never be ambiguous with a prefix.

Two other measurements mattered. A real `v` render on the Agents tab produces **924–1,154 hints** (from your own `tui_trace.jsonl`) — fine for a type-a-number bar, fatal for painted labels, so I specced a window-scoped fallback. And `sase bead show sase-ug` contains **13 bare bead ids** that today's scanner sees none of, because the path regex needs a `/` or an extension.

## Recommendation

One `SasePager(App)` fed a structured `PagerDocument` of sections, with the pager — not its callers — owning link discovery. `ctrl+n`/`ctrl+p` scrolls a section header to row 0 rather than swapping views (your phrasing implied a scroll, and it keeps `/` and `g`/`G` document-wide). Trail entries restore scroll offset and search state, not just the document.

**Yes to a CLI command: `sase pager`** — chiefly because it's the thing you put in `$SASE_PAGER`, so `export SASE_PAGER="sase pager"` routes every paging SASE command through it with plumbing that already ships. Secondarily, `sase pager bead:sase-ug plan:… src/…` (multi-ref, one view) is a capability that doesn't exist. I rejected `sase view`/`sase open` as colliding with `sase artifact read`/`open`.

## On sase-ug

Complementary, not competing: the rail answers "what is this entity linked to?" (graph edges, p50 1, ≤9 chips, `$`-prefixed), the pager answers "what does this text point at?" (textual mentions, p50 17, inline single keys). Different key budgets justify different grammars. But three seams must be shared or you get two divergent link systems: **ref→destination resolution** (the pager should consume `sase-ug.5`'s O(1) `LinkIndex`, not build a second one — the one real sequencing dependency), **ref→glyph/accent/short-label**, and **the trail object** (a `$1` hop into the pager and a `backspace` out should walk one history).

Four questions for you are at the end of the doc — the command name, whether the pager renders a `LINKS` rail before sase-ug lands one, whether `v` should eventually open the agent detail document itself, and the reserved-key set.
