#gh:gh_sase-org__sase #fork:0mn Actually, these are rendered at the bottom of the command's output as
children already, so `[[foo]]` links produce duplicate references. Can you help me fix
this by preferring to render the reference in the `Linked References` section only when
some references are both children and linked (make sure to omit the `Children` section
completely when all children are rendered in the `Linked References` section)? See the
command output below for context.

#plan

```
❯ sase memory show tui.md
# TUI

This is the entry point for SASE TUI work. Read the relevant child note before changing
live TUI capture, visual snapshot behavior, rendering, navigation, refresh, startup, or
other event-loop-sensitive UI code.

[[tui_screenshot.md]]

[[tui_perf.md]]

## Children

The below files contain detailed reference material. When working in their domain, you
MUST use your `/sase_memory_read` skill to review their contents. Do not read canonical
memory files directly.

**`sase/memory/tui_perf.md`**
Read before changing anything that affects TUI performance or responsiveness (navigation, refresh, rendering, startup), and before diagnosing TUI freezes or stalls.

**`sase/memory/tui_screenshot.md`**
Read before using or changing `sase screenshot`, live TUI SVG export, or TUI PNG visual snapshot capture.

## Linked References

The below memory files are linked from this one. Read one with your `/sase_memory_read`
skill; do not open the file directly.

### 1. `tui_screenshot.md`

**Tui Screenshot** — Read before using or changing `sase screenshot`, live TUI SVG
export, or TUI PNG visual snapshot capture.

### 2. `tui_perf.md`

**Tui Perf** — Read before changing anything that affects TUI performance or
responsiveness (navigation, refresh, rendering, startup), and before diagnosing TUI
freezes or stalls.
```