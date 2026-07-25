# Chat History - ace-run

- **TIMESTAMP:** 2026-07-22 10:10:22 EDT
- **MODEL:** claude/opus
- **AGENT:** i6

## Prompt

#gh:gh_sase-org__sase Can you help me give dashes that are used as bullets (i.e. the `-` in `- ` if `- ` is at the start of the line with nothing to the left of it but potentially spaces) a better foreground color in the prompt input widget so it is easy for users to spot them? Make sure this color is highly visible, appropriate, and doesn't clash with existing colors used in the prompt input widget. I want you to lead the design on this one. Just make sure it looks beautiful! %model:opus

## Response

I'll explore the prompt input widget to understand how it renders text and applies colors, then design a beautiful bullet-dash highlight.

I'll explore the SASE repo to find the prompt input widget. Let me start with parallel searches.

I'll wait for the exploration to complete before designing the highlight.

Let me look at the widgets directory for the prompt input widget and related highlighting files.

The main widget is likely `prompt_text_area.py`. Let me read it plus the key highlight files in parallel.

This is a clear mixin-based architecture. Let me find the base `_append_highlight_span` / `_build_highlight_map` mechanism, the other highlight mixins, and the tests + snapshot goldens.

Now I understand the overlay chain. `JinjaHighlightMixin` defines the base `_append_highlight_span`. Let me look at the remaining highlight mixins, the xprompt tokenizer kinds, and find tests + snapshot goldens.

Let me look at the xprompt tokenizer kinds fully and find the test files + snapshot goldens.

Let me look at the TODO highlight test (closest analog), the visual snapshot test, and locate the committed golden images.

Let me confirm the committed TODO golden PNGs and the prompt snapshot fixture helper (where fixture prompt text constants live).

Let me quickly check the TODO fixture text constants and confirm no existing bullet/dash highlighting exists.

I have a complete picture of the architecture. Here is the thorough report.

## Summary

The prompt input widget is `PromptTextArea`, a Textual `TextArea` subclass built from a stack of highlighting **mixins**. Each mixin registers its colors onto a shared `TextAreaTheme` (`syntax_styles` dict) and overlays character-offset spans via a shared `_append_highlight_span` helper. This is the exact mechanism you'll extend to add a leading `- ` bullet-dash color. It is NOT tree-sitter based for these overlays — it's manual span appending on top of the base markdown `TextAreaTheme`.

## 1. Files implementing the prompt input widget

- **Main widget:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/widgets/prompt_text_area.py`
  - `class PromptTextArea(...)` at lines 67-89 composes ~20 mixins on top of `VimTextArea`. The highlight mixins in the MRO are (lines 71-83): `YankHighlightMixin`, `SearchHighlightMixin`, `TodoHighlightMixin`, `AltSyntaxHighlightMixin`, `XPromptSyntaxHighlightMixin`, `CodeBlockHighlightMixin`, `PlaceholderHighlightMixin`, `JinjaHighlightMixin`.
- Base vim/textarea layers: `src/sase/ace/tui/widgets/vim_text_area.py`, `single_line_vim_text_area.py`.
- The container bar (border title, "TODO 4" counter, etc.) is `src/sase/ace/tui/widgets/prompt_input_bar.py`.

## 2. How highlighting is applied

Each highlight overlay is a mixin that follows the same three-part pattern. The foundational mixin is **`_jinja_highlight.py`**, which defines the shared span helper the others call:

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/widgets/_jinja_highlight.py`
  - `_append_highlight_span(start, end, style_name)` at **lines 73-82** — converts Python char offsets to per-row UTF-8 byte columns (via `_line_byte_spans`, lines 131-158) and appends `(start_byte, end_byte, style_name)` tuples to `self._highlights[row]` (the Textual `TextArea` highlight map).
  - The overlay chain root: `_build_highlight_map` at line 51 calls `super()._build_highlight_map()` (Textual's base markdown highlighter) then appends Jinja spans. Every other mixin's `_build_highlight_map` calls `super()` first, so overlays layer in MRO order.
  - Constants shared by all overlays: `_JINJA_THEME_NAME = "sase-jinja-prompt"`, `_MAX_OVERLAY_BYTES = 80_000`, `_MAX_OVERLAY_LINES = 1_200` (lines 18-20).

Colors are stored as Rich `Style` entries in a `TextAreaTheme.syntax_styles` dict. Each mixin has a `_register_*_text_area_theme` method that copies the base theme's `syntax_styles`, `.update()`s its own style names, and re-registers the theme (via `dataclasses.replace`). All colors are pulled live from `self.app.current_theme` (`.success`, `.warning`, `.accent`, `.secondary`, `.foreground`, `.error`), so they adapt to light/dark themes. Themes are re-registered on `on_mount` and `_app_theme_changed`.

So: not `render_line`-based coloring (except a small selection-restore tweak in TODO), not tree-sitter — it's **theme `syntax_styles` + manually appended `Highlight` spans**.

## 3. Colors currently used

All are theme color names off `app.current_theme` unless noted. The style-definition dicts:

**xprompt** — `_xprompt_syntax_highlight.py` lines 146-184:
- `xprompt.invocation` → `success`, bold (the `#foo` xprompt mention)
- `xprompt.invocation_arg` → derived success (blended toward fg)
- `xprompt.directive` → `warning`, bold
- `xprompt.directive_arg` → derived warning
- `xprompt.separator` → `secondary`, dim, bold
- `xprompt.skill` → derived `accent`, bold (the `/skill` references)

**jinja** — `_jinja_highlight.py` lines 92-111:
- `jinja.delimiter` accent/dim, `jinja.statement` & `jinja.keyword` accent/bold, `jinja.variable` secondary/bold, `jinja.filter` success, `jinja.comment` foreground/dim/italic, `jinja.operator` foreground/dim, `jinja.error` error/underline, `jinja.unknown` warning/underline, `jinja.match` foreground on accent-bg bold.

**placeholder** — `_placeholder_highlight.py` lines 143-148:
- `placeholder.delimiter` accent/dim, `placeholder.inner` secondary/bold (the `<...>` placeholders).

**alt fan-out** — `_alt_syntax_highlight.py` lines 89-96:
- `alt.delimiter` accent/bold, `alt.separator` accent/dim, `alt.branch_name` success/bold, `alt.error` error/underline (the `%{...}` alt syntax).

**TODO** — `_todo_highlight.py` lines 269-281 (colors computed by `todo_theme_colors`, lines 90-100):
- `todo.header` → foreground = contrast text, bgcolor = `RUNNING_COLOR` gold chip, bold
- `todo.body` → foreground blended 30% toward the gold, italic
- `RUNNING_COLOR` is imported from `src/sase/ace/tui/models/agent_status.py` (line 17).

Also `_codeblock_syntax_highlight.py`, `_search_highlight.py` (`search.current`), `_yank_highlight.py` (`yank.flash`) define transient overlays.

The xprompt span "kinds" enum lives at `src/sase/xprompt/xprompt_inspect.py` lines 33-40: `invocation`, `invocation_arg`, `directive`, `directive_arg`, `separator`, `skill`.

## 4. Exact locations to add a bullet-dash rule

Two categories of edits for any new highlight color:

**(a) Color/style definitions (the `syntax_styles.update({...})` blocks):**
- `_todo_highlight.py:269-281` (best template — plain foreground color, no tokenizer needed)
- `_xprompt_syntax_highlight.py:146-184`
- `_jinja_highlight.py:92-111`
- `_placeholder_highlight.py:143-148`
- `_alt_syntax_highlight.py:89-96`

**(b) Span-append logic (`_build_highlight_map` overrides that call `_append_highlight_span`):**
- `_jinja_highlight.py:51` (base) and `_append_highlight_span` def at `_jinja_highlight.py:73`
- `_todo_highlight.py:144-157`
- `_xprompt_syntax_highlight.py:89-115`
- `_placeholder_highlight.py:68-99`
- `_alt_syntax_highlight.py:62-77`

**Recommended approach:** clone `_todo_highlight.py` into a new `_bullet_highlight.py` mixin (it's the closest analog — a pure-Python regex span detector + a single foreground `Style`, no external Rust/tokenizer dependency). You'd:
1. Write a span scanner for leading `- ` (line-start bullets), analogous to `_todo_annotation_spans` / `_TODO_HEADER_RE` at `_todo_highlight.py:30,44-87`.
2. Add `_build_highlight_map` (like `_todo_highlight.py:144`) that appends a `"bullet.dash"` span.
3. Add `_register_bullet_text_area_theme` (like `_todo_highlight.py:255-289`) defining `"bullet.dash": Style(color=...)`.
4. Register the mixin in the MRO in **`prompt_text_area.py` lines 67-89** — order matters (later-appended spans win on overlap; TODO sits at line 73 above the syntax overlays). Also add the import near lines 7-37.

There is currently **no** existing bullet/list-marker highlighting anywhere in the highlight mixins or the tokenizers (confirmed by search).

## 5. Tests and snapshot goldens

**Unit tests (one per highlight mixin)** in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/ace/tui/widgets/`:
- `test_prompt_todo_highlight.py` — the model to copy for a bullet test (span contract tests + overlay/theme tests + a `_render_line` background-precedence test). Note the helper `_highlight_names()` at lines 29-30 and `CompletionTestApp` from `._completion_helpers`.
- `test_prompt_xprompt_highlight.py`, `test_prompt_alt_syntax_highlight.py`, `test_prompt_codeblock_highlight.py`, `test_prompt_search_highlight.py`, `test_prompt_yank_highlight.py`.
- Tokenizer-level: `tests/ace/tui/util/test_xprompt_syntax.py`.

**Visual snapshot test:** `tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py` (pytest marker `visual`). Contains `test_prompt_todo_restored_png_snapshot` (dark+light) and `test_prompt_todo_stack_png_snapshot`.

**Fixture prompt-text constants:** `tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py` — `XPROMPT_HIGHLIGHT_SOLO/STACK` (lines 60-68), `CODEBLOCK_*` (70-95), `TODO_RESTORED_PROMPT` (97-111), `TODO_HIGHLIGHT_STACK` (112-120). `mount_prompt_bar()` at line 150. (The TODO fixtures already contain `- [ ]` lines you'd re-use for a bullet golden.)

**Committed golden PNGs:** `tests/ace/tui/visual/snapshots/png/` — e.g. `prompt_todo_restored_dark_120x40.png`, `prompt_todo_restored_light_120x40.png`, `prompt_todo_stack_120x40.png`, plus `prompt_xprompt_highlight_*`, `prompt_codeblock_highlight_*`, `prompt_search_highlight_120x40.png`. Snapshot diffing harness: `tests/ace/tui/visual/png_diff.py` (`AcePngSnapshotFixture`). Test-run artifacts (actual.svg) go to `.pytest_cache/sase-visual/` — not the committed goldens.

For a new bullet rule you'd add: a unit test (clone `test_prompt_todo_highlight.py`), optionally a new visual test case + fixture constant in `_ace_prompt_png_snapshot_helpers.py`, and regenerate goldens into `tests/ace/tui/visual/snapshots/png/`.

Let me read the key files to design the bullet-dash highlight properly.

Let me read the shared span helper, the xprompt color-derivation helpers, and the TODO test to nail down the exact patterns and available theme colors.

I have the pattern down. Now let me look at the actual theme definitions and the prompt bar's border color so my color choice is informed and won't clash.

I'll search for theme definitions, the prompt input bar widget, and the RUNNING_COLOR value in parallel.

While that runs, let me study the test patterns I'll need to mirror.

Now the visual snapshot test and its helpers.

The `Theme(` construction didn't show up in that grep. Let me search more specifically for Textual theme definitions and read the prompt input bar and agent_status files.

The `register_theme` calls are for syntax-highlight sub-themes. Let me find the app-level color themes and the CSS for the prompt input bar border.

Let me look at the app.py for theme registration and the styles.tcss and DEFAULT_CSS for the prompt input bar.

Now let me read the PromptInputBar CSS block precisely and find where app themes are defined/set.

No explicit `Theme(` constructor exists in the ace app. Let me find how the theme is actually selected/set and check the todo_highlight for how it derives colors, plus search the whole repo for theme configuration.

Let me read the AceApp class definition and check what the `register_theme` calls in the highlight files actually register.

The `register_theme` calls are `TextAreaTheme` registrations (syntax highlighting), not App color themes. The app uses Textual's built-in themes via `$primary`/`$accent` CSS variables. Let me find which built-in theme is selected as default.

Let me look at the simplest existing overlay mixin (alt syntax) as a cleaner template, since my bullet overlay won't need TODO's background/selection-restore machinery.

The app sets `self.theme = "flexoki"` — a built-in Textual theme, and there's no theme switching (command palette disabled). Let me confirm the context and pull the concrete hex values from Textual's built-in theme definitions.

The alt mixin is the ideal clean template. Now let me wait for the theme color report to finalize the exact color choice.

`just install` is done. I'm waiting on the theme-color report (the key input for choosing a non-clashing, highly-visible color) before I write the code. I'll proceed as soon as it lands.

The filesystem-wide find is slow. Let me target the venv/site-packages directly.

I have everything needed. The background filesystem find is no longer needed. Here is the complete report.

## 1. Theme definitions for `sase ace`

The ace app does **not** define any custom Textual `Theme()` objects. It selects exactly one Textual **built-in** theme by name:

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/_state_init.py:87`
  ```python
  self.theme = "flexoki"
  ```

There is no theme switching: `AceApp` sets `ENABLE_COMMAND_PALETTE = False` (`src/sase/ace/tui/app.py:133`), and no other `self.theme = ...` assignment exists in `src/sase/`. So **`flexoki` is the sole, default theme.**

Note: every `register_theme(...)` hit in `src/sase/ace/tui/widgets/_*_highlight.py` registers `TextAreaTheme` objects (syntax highlighting inside text areas), **not** App-level color themes. They have no `primary`/`accent` slots.

The concrete hex values come from Textual's built-in theme table:
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/lib/python3.14/site-packages/textual/theme.py:230-248`

```python
"flexoki": Theme(
    name="flexoki",
    primary="#205EA6",    # blue
    secondary="#24837B",  # cyan
    warning="#AD8301",    # yellow
    error="#AF3029",      # red
    success="#66800B",    # green
    accent="#9B76C8",     # purple light
    background="#100F0F",  # base.black
    surface="#1C1B1A",    # base.950
    panel="#282726",       # base.900
    foreground="#FFFCF0",  # base.paper
    variables={ ... },
),
```

Color slots for the (only) theme, `flexoki`:

| Slot | Hex | Note |
|------|-----|------|
| primary | `#205EA6` | blue |
| secondary | `#24837B` | teal/cyan |
| accent | `#9B76C8` | light purple |
| foreground | `#FFFCF0` | near-white "paper" |
| background | `#100F0F` | near-black |
| surface | `#1C1B1A` | dark gray |
| panel | `#282726` | dark gray |
| success | `#66800B` | green |
| warning | `#AD8301` | yellow/amber |
| error | `#AF3029` | red |
| boost | not set (`None`) | Theme dataclass default `boost: str \| None = None` (theme.py:33) |

**Dark or light:** `flexoki` passes no `dark=` argument, so it uses the dataclass default `dark: bool = True` (theme.py:34). It is a **dark theme** (background `#100F0F`).

**Is `primary` visually distinct from `accent` and `secondary`?** Yes, clearly:
- `primary` = `#205EA6` — a medium **blue**
- `accent` = `#9B76C8` — a light **purple**
- `secondary` = `#24837B` — a **teal/cyan**

All three occupy different hue families (blue vs purple vs teal), so `primary` blue is distinguishable from both.

## 2. Prompt input bar border / border-title color

The widget is `PromptInputBar` (`src/sase/ace/tui/widgets/prompt_input_bar.py`). Its `DEFAULT_CSS` is empty for styling — all styling lives in the shared stylesheet `src/sase/ace/tui/styles.tcss` (`CSS_PATH = "styles.tcss"`, app.py:132).

Relevant rules:
- `src/sase/ace/tui/styles.tcss:2834-2840`
  ```css
  PromptInputBar {
      height: 3;
      border: solid $accent;   /* line 2836 */
      background: $surface;
      dock: bottom;
      padding: 0 1;
  }
  ```
- No `border-title-color` is set on `PromptInputBar`, so Textual defaults the border-title text to the **border color**, i.e. `$accent` (`#9B76C8` purple).
- Feedback/approve mode overrides the border to warning: `PromptInputBar.feedback-mode { border: solid $warning; }` (styles.tcss:3092-3093, `$warning` = `#AD8301`).
- Multi-pane left accent bars also use `$accent`: `.prompt-pane { border-left: thick $accent 30%; }` (styles.tcss:3055-3058) and `.prompt-pane.active { border-left: thick $accent; }` (3062-3064). Separators use `$accent` too (3088-3089).
- The completion / frontmatter sub-panels use `$secondary` and `$accent` borders (e.g. `#prompt-completion { border: solid $secondary; }` at 2846).

**Answer to your concern:** the prompt input bar's border and border-title use **`$accent` = `#9B76C8` (purple)**, **not** `$primary`. `$primary` (`#205EA6` blue) is not used anywhere on this widget's border chrome. So if you color bullet-dashes with `$primary` (blue), they will **not** blend into the accent-purple border. (For reference, `$primary` in this stylesheet is used mainly for modal container borders like `border: thick $primary`, not the prompt bar.)

## 3. `RUNNING_COLOR`

- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/agent_status.py:8`
  ```python
  RUNNING_COLOR = "#FFD700"
  ```
  Exact value: **`#FFD700`** (gold). Used as `f"bold {RUNNING_COLOR}"` in `_agent_list_render_agent.py:234` and parsed as the TODO chip background in `_todo_highlight.py:97`.

### Quick takeaway for your highlight-color choice
- Border of the prompt bar = `accent` `#9B76C8` (purple).
- `primary` `#205EA6` (blue) is unused on that border and is a distinct hue — safe for bullet-dashes without blending.
- Watch out separately for `RUNNING_COLOR` `#FFD700` (gold) and `secondary` `#24837B` (teal), which are used elsewhere in the prompt chrome (TODO chip, completion panel border).

All information is in. Let me record my design decision to memory-worthy notes mentally and lay out the plan, then implement.

**Design decision (I'm leading this):**
- **Sole theme is `flexoki` (dark).** Existing prompt highlights consume `success` (green `#66800B`), `warning` (amber `#AD8301`), `accent` (purple `#9B76C8`, also the prompt-bar border), `secondary` (teal `#24837B`), `error` (red `#AF3029`), and gold `#FFD700` (TODO chip). The one core, prominent slot **unused anywhere** in the prompt widget is **`primary` (blue `#205EA6`)** — a distinct hue from every one of those, so zero clash.
- To make it *pop* against the near-black canvas (and stay adaptive for the light-theme test snapshots), I'll lift `primary` a controlled 30% toward the foreground — brighter blue on dark backgrounds, darker blue on light ones (contrast rises either way) — and render it **bold**. Clean, on-brand, unmistakably a bullet.

Let me set up task tracking and write the code.

Now the mixin. I'll model it on the clean alt-syntax template, add a pure-Python scanner and a testable color helper.

Let me remove the unused `Any` import.

Those diagnostics are the Pyright tool not seeing the workspace venv (the same `textual.*` imports resolve fine for every sibling mixin); `just check` uses the real environment. Now let me wire the mixin into the MRO.

Let me sanity-check the scanner and color helper in the real venv before writing tests.

The scanner and color helper behave exactly as designed — dashes matched only as true leading bullets, `--- `/`-- `/mid-line/`-nospace` all correctly rejected, and the lifted-primary blue is `#628DBC` on dark (a clean, spottable sky-blue) / `#164174` on light. (The `prompt_text_area.py:127` diagnostic is pre-existing Pyright-env noise, unrelated to these edits — `just check`/mypy is the real gate.)

Now the unit tests.

Now the unit tests, modeled on the TODO test patterns:

The fast-path test patches a compiled-regex method, which `re.Pattern` won't allow. Let me mirror the TODO module's structure with a separate scan helper so the fast path is cleanly testable.

Now update the fast-path test to patch the scan helper instead:

Now let me run the unit tests in the real venv:

The cross-row `.index()` comparison was the flaw — overlay precedence only orders *within* a row (same cell). `list.marker` (the base markdown dash marker) confirms my overlay correctly sits on top. Let me split into a byte-column membership test and a single-row precedence test.

All 22 unit tests pass. Now the visual snapshot golden — the project convention for prompt-highlight changes, and the best way to lock in "beautiful." Let me add a showcase fixture and test.

Now add the visual test (dark + light, mirroring the codeblock-solo pattern):

Now generate the golden PNGs:

Goldens generated. Let me view them to confirm the result actually looks beautiful.

That looks exactly as designed — the leading bullet dashes (lines 2–6, flush and indented) render in a bright, clean blue that pops against the canvas, clearly distinct from the green `#gh:sase` and the jinja accent, while the two **mid-line** dashes on line 6 (`- like this -`) correctly stay uncolored. Let me confirm the light theme reads well too.

Both themes look great — the dash adapts (bright sky-blue on dark, deeper blue on light), always legible against the canvas, and the leading-only rule holds in both. Now the full gate.

The markdown-format failure is on `docs/ace.md`, which I never touched. Let me confirm it's pre-existing and not caused by my change.

Confirmed — `docs/ace.md` is not among my changed files; that prettier warning is pre-existing and unrelated (it aborted `check` before the Python lint/mypy/test steps ran). Let me run the Python gates directly on my changes.

ruff and mypy pass cleanly. Symvision (unused-public-symbol lint) flags my three public helpers. Per the repo rule I must consult the symvision memory before fixing it.

The hierarchy is clear: delete `bullet_dash_count` (no src consumer — dead), and make `bullet_dash_spans`/`bullet_dash_color` private (used only within their own file). Let me apply that.

Now update the two in-file callers:

Now update the test imports and remove the `bullet_dash_count` usage:

The displayed file is fully renamed correctly (those diagnostics are stale from the intermediate state). Let me re-run the unit tests plus symvision to confirm everything's clean.

All 22 unit tests pass and symvision is clean. Let me run the full `just lint` and the relevant test suites (widget + visual) to confirm nothing regressed.

Two `test_prompt_todo_restored` goldens failed — expected: that fixture contains `- [ ] TODO:` lines, so my feature now (correctly) colors those leading bullet dashes. That's a legitimate, intended golden change. Let me regenerate those two and visually verify the dash + TODO chip coexist beautifully.

Lines 30–31 now show the leading `-` in bright blue, coexisting cleanly with the gold TODO chips — distinct hues, zero clash. The two TODO goldens are correctly updated. Now the full test suite to confirm no other regressions.

Full suite green: **20,801 passed, 7 skipped, 0 failed**. Let me do a final read of the completed mixin to make sure it reads cleanly after the edits.

The implementation is complete and clean. Let me finalize the task tracking.

Done. Here's what I built and the design behind it.

## Design decision (the color)

I audited every color already in play in the prompt input widget so the new one wouldn't clash. The sole app theme is **flexoki (dark)**, and its existing prompt highlights already spend:

| Slot | Color | Used for |
|---|---|---|
| success | green | `#gh:sase` xprompts, alt branches |
| warning | amber | directives, jinja unknowns |
| accent | purple | jinja keywords, placeholders, **and the prompt-bar border** |
| secondary | teal | jinja vars, separators, completion border |
| error | red | jinja/alt errors |
| — | gold `#FFD700` | TODO chip |

The one prominent core slot **nobody uses** is **`primary` (blue `#205EA6`)** — a distinct hue from all of the above, and notably *not* the accent-purple border, so bullets can't blend into chrome. To make it genuinely *pop*, I lift `primary` 30% toward the foreground: a brighter sky-blue (`#628DBC`) on dark backgrounds, a deeper blue on light ones — contrast rises either way — rendered **bold**. It's theme-adaptive, on-brand, and unmistakable.

Only the `-` of a true leading bullet is colored: start of line, spaces-only to its left, a space to its right. `--- rules`, `-- `, `-tight`, and mid-line dashes (`text - dash`) are all left alone.

## Files changed
- **`src/sase/ace/tui/widgets/_bullet_highlight.py`** (new) — `BulletHighlightMixin`, modeled on the existing overlay mixins; a regex scanner and a testable color helper.
- **`src/sase/ace/tui/widgets/prompt_text_area.py`** — wired the mixin into the MRO so the dash wins over base-markdown/code-block spans but still yields to the transient search/yank overlays.
- **`tests/ace/tui/widgets/test_prompt_bullet_highlight.py`** (new) — 22 tests: scan contract, UTF-8 byte-column mapping, overlay precedence, and theme-adaptive color.
- **Visual snapshots** — new `prompt_bullet_highlight_solo_{dark,light}` goldens, plus regenerated the two `prompt_todo_restored` goldens (their fixture has `- [ ] TODO:` lines, which now correctly show a blue dash beside the gold chip).

## Verification
- `just lint` — ruff, mypy, and symvision all clean.
- Full suite: **20,801 passed, 7 skipped, 0 failed** (includes the visual snapshot suite).
- I visually confirmed both themes: dashes read clearly and don't clash with the green xprompts, jinja accents, or gold TODO chips.

One note: `just check` currently stops at a **pre-existing** prettier warning on `docs/ace.md` — a file I never touched, unrelated to this change. I ran the Python gates directly instead, which all pass. I haven't committed anything, since you didn't ask me to.

I made these changes in this session, so I'll commit them using the commit skill.

I'll record the skill usage, examine the changes, then commit.

All expected files are present. This is a user-facing feature addition, so `feat` is the right tag. Let me write the commit message.

A binary conflict on the two TODO golden PNGs — an upstream commit (`627b0b377 fix(tui): keep TODO markers legible`) also regenerated them. Since the correct golden must reflect **both** upstream's TODO legibility fix and my bullet-dash highlight, I'll resolve by taking one side to unblock, then regenerating the goldens against the current code. Let me inspect the state first.

The upstream commit changed `_todo_highlight.py` rendering (black text on gold) plus the same helper/test files I touched. My goldens were generated against the *old* TODO rendering, so I must regenerate them against the current merged code — which now has both upstream's TODO fix and my bullet feature. First let me verify the auto-merged helper/test files coherently contain both sets of changes.

Good — upstream changed the `TODO_RESTORED_PROMPT` fixture text and the `TODO 4`→`TODO 5` assertion. My golden was generated against the old fixture and old rendering, so it must be regenerated. Let me confirm the current merged helper/test files contain both upstream's changes and my bullet additions.

Both upstream's changes and mine coexist cleanly in the merged files. Now I'll reinstall deps (ephemeral workspace, 8 commits pulled) and regenerate the goldens against the current merged code.

Goldens regenerated. Now verify they pass without the update flag, then let me visually confirm the regenerated TODO golden still looks right with both changes.

All four pass. Let me visually confirm the regenerated dark TODO golden shows both the black-on-gold TODO chips (upstream fix) and my blue leading dash coexisting.

The regenerated golden is correct: lines 30–31 show my blue leading `-` dashes coexisting with upstream's new black-on-gold `TODO:`/`TODO(ops):` chips, and line 32 reflects upstream's new fixture text. Both changes are integrated cleanly. Now I'll stage the resolved PNGs and continue the rebase.

The rebase completed successfully. Now I'll finalize the sase commit to replay the post-commit bookkeeping (push, ChangeSpec row, etc.).

Let me verify the final state — clean tree and pushed.

The branch is in sync with `origin/master` and my commit `0e26ea193` is at the top — the push succeeded. Let me confirm origin has it and clean up the leftover message file.

The commit is on `origin/master`, the working tree is clean, and the leftover message file is removed.

## Summary

I committed the bullet-dash highlight feature. The commit initially hit a **binary conflict** on the two `prompt_todo_restored` golden PNGs — an upstream commit (`627b0b377 fix(tui): keep TODO markers legible`) that landed while I worked had also regenerated those same goldens (rendering TODO chips as black-on-gold) and changed their fixture text (`TODO 4`→`TODO 5`).

Since the correct golden needed **both** upstream's TODO legibility fix and my new blue leading-dash highlight, I resolved it by:
1. Verifying the auto-merged helper/test files coherently contained both upstream's changes and my bullet additions.
2. Reinstalling deps (`just install`) after the rebase pulled 8 upstream commits.
3. Regenerating the two TODO goldens against the merged code with `--sase-update-visual-snapshots`, then confirming all four relevant visual tests pass *without* the update flag.
4. Visually verifying the regenerated golden — my blue `-` dashes on the `- [ ]` lines coexist cleanly with the black-on-gold `TODO:` chips, no clash.
5. Staging the resolved PNGs, continuing the rebase, and running `sase_git_commit --resume` to finalize.

The feature landed as `0e26ea193 feat(ace): highlight leading bullet dashes in prompt input`, now pushed to `origin/master` with a clean working tree.
