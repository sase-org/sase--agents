- **PLAN:**
  [202609/fix_deck_document_scroll_watcher_crash.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_deck_document_scroll_watcher_crash.md)
- **AGENTS:**
  - [bbugyi200.apollo.2r--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2r.md)

`sase tui` just crashed on this machine while I was browsing the "Tools" deck for sase
agent on the "Agents" tab (see the stacktrace below for context). Can you help me
diagnose the root cause of this issue and fix it? Think this through thoroughly and
create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.

```
╭──────────────────────────────────────────────────────────────────────────────────── Traceback (most recent call last) ────────────────────────────────────────────────────────────────────────────────────╮
│ /home/bryan/.local/share/uv/tools/sase/lib/python3.12/site-packages/textual/widget.py:2815 in _scroll_to                                                                                                  │
│                                                                                                                                                                                                           │
│   2812 │   │   │   if maybe_scroll_y:                                                                                                                                                                     │
│   2813 │   │   │   │   assert y is not None                                                                                                                                                               │
│   2814 │   │   │   │   scroll_y = self.scroll_y                                                                                                                                                           │
│ ❱ 2815 │   │   │   │   self.scroll_target_y = self.scroll_y = y                                                                                                                                           │
│   2816 │   │   │   │   scrolled_y = scroll_y != self.scroll_y                                                                                                                                             │
│   2817 │   │   │                                                                                                                                                                                          │
│   2818 │   │   │   self._last_scroll_time = monotonic()                                                                                                                                                   │
│                                                                                                                                                                                                           │
│ ╭────────────────────────────────────────────────── locals ──────────────────────────────────────────────────╮                                                                                            │
│ │        animate = False                                                                                     │                                                                                            │
│ │       animator = <textual._animator.Animator object at 0x74b9bb4014c0>                                     │                                                                                            │
│ │       duration = None                                                                                      │                                                                                            │
│ │         easing = None                                                                                      │                                                                                            │
│ │          force = False                                                                                     │                                                                                            │
│ │          level = 'basic'                                                                                   │                                                                                            │
│ │ maybe_scroll_x = False                                                                                     │                                                                                            │
│ │ maybe_scroll_y = True                                                                                      │                                                                                            │
│ │    on_complete = None                                                                                      │                                                                                            │
│ │ release_anchor = True                                                                                      │                                                                                            │
│ │       scroll_y = 0.0                                                                                       │                                                                                            │
│ │     scrolled_x = False                                                                                     │                                                                                            │
│ │     scrolled_y = False                                                                                     │                                                                                            │
│ │           self = VerticalScroll(id='agent-deck-panel-0-tools-scroll', classes='deck-scroll -tools -shown') │                                                                                            │
│ │          speed = None                                                                                      │                                                                                            │
│ │              x = None                                                                                      │                                                                                            │
│ │              y = 22.0                                                                                      │                                                                                            │
│ ╰────────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                                                            │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: DeckPanelCardDocumentsMixin._watch_document_scroll.<locals>.<lambda>() missing 2 required positional arguments: '_o' and '_n'
```
