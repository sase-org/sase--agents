- **PLAN:**
  [202610/peek_subtitle_unhashable_text.md](https://github.com/sase-org/sase--plans/blob/main/202610/peek_subtitle_unhashable_text.md)
- **AGENTS:**
  - [bbugyi200.athena.0uu--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uu.md)

`sase tui` just crashed (see stacktrace below for context). Can you help me diagnose the
root cause of this issue and fix it? Think this through thoroughly and create a plan
using your `/sase_plan` skill. Choose and author the appropriate tier, validate and
revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

```
│ ╭─────────────────────────────────────────────────────────────── locals ────────────────────────────────────────────────────────────────╮                                                                 │
│ │          event = Key(key='escape', character='\x1b', name='escape', is_printable=False, aliases=['escape', 'ctrl+left_square_brace']) │                                                                 │
│ │ pending_spacer = None                                                                                                                 │                                                                 │
│ │           self = PromptTextArea(id='prompt-input-g0-p0', classes='prompt-input -read-only solo -vim-normal active')                   │                                                                 │
│ ╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                                 │
│                                                                                                                                                                                                           │
│ /home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/widgets/_prompt_text_area_actions.py:372 in _enter_normal_mode                                                                                 │
│                                                                                                                                                                                                           │
│   369 │   │   self._clear_insert_g_prefix()                                                                                                                                                               │
│   370 │   │   self._clear_normal_g_prefix()                                                                                                                                                               │
│   371 │   │   self._clear_prompt_search(clear_highlights=True)                                                                                                                                            │
│ ❱ 372 │   │   self._clear_file_completion()                                                                                                                                                               │
│   373 │   │   self._clear_xprompt_arg_hint()                                                                                                                                                              │
│   374 │   │   self._vcs_mru_index = None                                                                                                                                                                  │
│   375 │   │   self._clear_soft_completion(cancel_timer=True)                                                                                                                                              │
│                                                                                                                                                                                                           │
│ ╭───────────────────────────────────────────────── locals ──────────────────────────────────────────────────╮                                                                                             │
│ │ self = PromptTextArea(id='prompt-input-g0-p0', classes='prompt-input -read-only solo -vim-normal active') │                                                                                             │
│ ╰───────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                                                             │
│                                                                                                                                                                                                           │
│ /home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/widgets/_file_completion_base_panel.py:351 in _clear_file_completion                                                                           │
│                                                                                                                                                                                                           │
│   348 │   │   self._vcs_ref_completion_has_namespaces = False                                                                                                                                             │
│   349 │   │   self._prompt_path_completion_directory_key = None                                                                                                                                           │
│   350 │   │   self._model_completion_catalog_request = None                                                                                                                                               │
│ ❱ 351 │   │   self._update_file_completion_panel("")                                                                                                                                                      │
│   352 │   │   if clear_xprompt_arg_hint:                                                                                                                                                                  │
│   353 │   │   │   self._clear_xprompt_arg_hint()                                                                                                                                                          │
│   354                                                                                                                                                                                                     │
│                                                                                                                                                                                                           │
│ ╭────────────────────────────────────────────────────────── locals ───────────────────────────────────────────────────────────╮                                                                           │
│ │ clear_xprompt_arg_hint = True                                                                                               │                                                                           │
│ │                   self = PromptTextArea(id='prompt-input-g0-p0', classes='prompt-input -read-only solo -vim-normal active') │                                                                           │
│ ╰─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                                           │
│                                                                                                                                                                                                           │
│ /home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/widgets/_file_completion_base_panel.py:246 in _update_file_completion_panel                                                                    │
│                                                                                                                                                                                                           │
│   243 │   │   │   return                                                                                                                                                                                  │
│   244 │   │                                                                                                                                                                                               │
│   245 │   │   if not self._file_completion_active or not self._file_completion_candidates:                                                                                                                │
│ ❱ 246 │   │   │   bar.hide_file_completions()                                                                                                                                                             │
│   247 │   │   │   return                                                                                                                                                                                  │
│   248 │   │                                                                                                                                                                                               │
│   249 │   │   if self._completion_kind != NEXT_WORD_COMPLETION_KIND:                                                                                                                                      │
│                                                                                                                                                                                                           │
│ ╭────────────────────────────────────────────────── locals ──────────────────────────────────────────────────╮                                                                                            │
│ │   bar = PromptInputBar(id='prompt-input-bar')                                                              │                                                                                            │
│ │  self = PromptTextArea(id='prompt-input-g0-p0', classes='prompt-input -read-only solo -vim-normal active') │                                                                                            │
│ │ token = ''                                                                                                 │                                                                                            │
│ ╰────────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                                                            │
│                                                                                                                                                                                                           │
│ /home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:293 in hide_file_completions                                                                     │
│                                                                                                                                                                                                           │
│   290 │   │   self._completion_visible = False                                                 ╭─────────────────────────── locals ───────────────────────────╮                                           │
│   291 │   │   self._completion_panel_kind = None                                               │     panel = Static(id='prompt-completion', classes='hidden') │                                           │
│   292 │   │   self._completion_line_count = 0                                                  │      self = PromptInputBar(id='prompt-input-bar')            │                                           │
│ ❱ 293 │   │   if self._subtitle_base in {                                                      │ was_jinja = False                                            │                                           │
│   294 │   │   │   MODEL_ALIAS_MODE_SUBTITLE,                                                   ╰──────────────────────────────────────────────────────────────╯                                           │
│   295 │   │   │   MODEL_EXPLICIT_MODE_SUBTITLE,                                                                                                                                                           │
│   296 │   │   }:                                                                                                                                                                                          │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: cannot use 'rich.text.Text' as a set element (unhashable type: 'Text')
```
