# Chat History - ace-run (zd)

- **TIMESTAMP:** 2026-08-13 09:42:03 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** zd

## Prompt

#gh:gh_sase-org__sase The command string for sase monitors should not be shown in the left pane on the agents tab. For example, `· sase bead work /home/bryan/.sase/plans/202608/artifacts_tab_icons.md --ye` should not be shown in #sshot. Can you help me fix this? Be mindful of the related sase-ku epic, which is currently running (leave notes on this epic bead or its phase beads if your work conflicts in any way).

## Response

I'll start by looking at the screenshot and understanding the current state.

I'll start by exploring the ACE TUI structure to find the agents tab tree rendering code.

Let me search for the monitor icon and label building.

Found the core site. Let me get exact line numbers and trace the model fields.

Found it. Let me look at the surrounding context.

Now let me make the change.

Now update the test to assert the command is *absent*:

Here is what I found.

## 1. Where the command is appended to the monitor row

**The single site.** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/_agent_list_render_agent.py:254-257`

```python
        # Agent display name (workflow name for top-level workflows,
        # Patch name otherwise).
        display_name = agent.monitor_label if agent.is_monitor else agent.display_name
        text.append(display_name or agent.display_name, style=name_style)
        if agent.is_monitor and agent.monitor_command:
            text.append(f" · {agent.monitor_command}", style="dim #D7AF5F")
```

Line 256-257 is exactly the `· <command>` append you're seeing. Removing/gating those two lines removes the command from the row.

Introduced by commit `1d3b20fad feat(tui): show monitor rows in agent rosters` (verified via `git log -L 254,258`).

**Surrounding row construction, same file** (`_agent_list_render_agent.py`):
- `:128` `def format_agent_option(agent, index, *, is_selected, ...) -> tuple[Text, Text, str]` — the left-pane row builder; docstring: *"Build `(left_text, suffix_text, option_id)` parts for an agent row."*
- `:184` and `:191` — the `⏱ ` glyph append (`text.append(f"{_MONITOR_GLYPH} ", style=_MONITOR_GLYPH_STYLE)`); `:184` is the tree-child (indented) branch, `:191` the top-level branch.
- `:214` monitor row color (`color = _MONITOR_ROW_STYLE`).
- `:229` monitors suppress the `[type]` badge.
- `:266-278` status parens (`(MONITORING)` etc.), monitor-specific status colors at `:273/:275/:277`.
- `:401` failed/timeout monitor exit badge (`✗ N` / `⧖`).
- `:521` `cached_format_agent_option(...)` — memoized wrapper; delegates to `format_agent_option` at `:579`.

**Glyph/style constants:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/_agent_list_styling.py:89-91` (`_MONITOR_GLYPH = "⏱"`, `_MONITOR_GLYPH_STYLE`, `_MONITOR_ROW_STYLE`). Note the command append does *not* use a named constant — it hardcodes `"dim #D7AF5F"` inline.

**Callers (left pane tree build):**
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/_agent_list_build.py:317` and `:624` — `cached_format_agent_option(...)`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/agent_list.py:478-490` — `AgentList._format_agent_option` wrapper
- Re-exported via `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/_agent_list_rendering.py:15-39`

No monitor-specific logic exists in `_agent_list_build.py` or `_agent_list_helpers.py` — all monitor row presentation lives in `_agent_list_render_agent.py`. There is also **no truncation** of the command anywhere; the trailing `--ye` cut-off in your sample is plain terminal-width clipping (`_agent_list_render_layout.py:153-170` `assemble_padded_option` only pads, never truncates the left text).

**Render cache:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/_agent_list_render_cache.py:219-223` includes `agent.monitor_label` and `agent.monitor_command` in `agent_render_key`, so a change to the append logic that consults a new field must add that field here too or stale rows will be served.

## 2. Model / dataclass fields and where they are populated

**Field declarations:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/_agent_state.py:159-169` — there is no separate `MonitorRow`; monitor rows are ordinary `Agent` rows with a monitor projection:

```python
    monitor_id: str | None = None
    monitor_state: str | None = None
    monitor_command: str | None = None
    monitor_label: str | None = None
    monitor_exit_code: int | None = None
    monitor_cwd: str | None = None
    ...
```

**`is_monitor` predicate:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/agent.py:249-252` — `bool(self.monitor_id) or self.agent_family_role == "monitor"`.

**Population path (TUI loaders):**
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/_loaders/_meta_enrichment_common.py:32-72` — `apply_monitor_meta(...)`, sets `agent.monitor_command` at `:53-55` and `agent.monitor_label` at `:56`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/_loaders/_meta_enrichment_wire.py:258-259` — from the `AgentMetaWire` scan wire.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/_loaders/_meta_enrichment_filesystem.py:384-385` — from raw `agent_meta.json` (`data.get("monitor_command")` / `"monitor_label"`).

**Upstream producers (outside the TUI):**
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/monitor/member.py:57-70` — writes `"monitor_command": command`, `"monitor_label": label` into `agent_meta.json`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/agent_scan_wire_markers.py:196` — wire schema field.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/agent/running_listing.py:69, :290, :473`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/monitor/models.py:121-124` — note the fallback contract `label = meta.monitor_label or meta.monitor_command or ""`, so a monitor with no label already falls back to the command as its label.

**Other consumers of `monitor_command` (not the tree row)** — worth checking if you change the contract:
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/prompt_panel/_agent_monitor_section.py:67-70` — right-pane detail panel renders the command as a bash-highlighted block (this is the "full" surface for the command).
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agents/_monitor_stop_flow.py:31, :45` — `monitor_label or monitor_command or "monitor"` for stop-flow messages.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/integrations/_mobile_agent_summary.py:177`, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/integrations/_agent_list_entry_builder.py:230-232`, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/agents/cli_list.py:105`.

## 3. Tests asserting on the rendered row text including the command

**Primary (this is the test that will fail if you drop the command):**
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_list_monitor_rows.py:50-62`

```python
def test_monitor_row_uses_glyph_label_and_command_annotation() -> None:
    left, _suffix, _option_id = format_agent_option(
        _monitor(status="MONITORING", monitor_state="running"), 0, is_selected=False,
    )
    assert "⏱" in left.plain
    assert "just check" in left.plain
    assert "just check-full" in left.plain   # <- the appended command
    assert "MONITORING" in left.plain
```

The fixture at `:11-48` sets `monitor_label="just check"`, `monitor_command="just check-full"`. Same file also has `test_failed_monitor_row_renders_exit_badge` (`:64`) and `test_timeout_monitor_row_renders_timeout_badge` (`:73`), which assert on `✗ 1` / `⧖` and would not be affected.

**Related but not asserting on the tree row text:**
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/models/test_monitor_rows.py:39-55, :74, :116` — loader projection only (`assert agent.monitor_command == "just check-full"`).
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_prompt_panel_monitor.py:48` — right-pane detail section.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_display_family_member_roster.py:239` — roster entries assert on `(label, kind, status)` tuples, not command text.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_keybinding_footer_agent.py:418`, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_mobile_agent_listing.py:128`, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_agent_list_entries.py:187-229`, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_core_agent_scan_wire.py:530-561`.

**Help-modal legend that documents the behavior** (would go stale if you drop the command): `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/help_modal/agents_bindings.py:421` — `("⏱", "Monitor member (command)")`.

Both failures are pre-existing and unrelated to my change. Let me file them properly.

Now let me record both findings.

Done. The monitor command string no longer renders in the Agents-tab left pane.

## The change

`src/sase/ace/tui/widgets/_agent_list_render_agent.py:256-257` was the single site appending ` · <monitor_command>` to the row. Removed it, so rows go from:

```
⏱ Epic launch · artifacts_tab_icons · sase bead work /home/bryan/.sase/plans/202608/artifacts_tab_icons.md --ye (MONITORING)
⏱ Epic launch · artifacts_tab_icons (MONITORING)
```

The label always survives — `src/sase/monitor/start.py:113` falls back to `_default_label(command)` when `--label` is omitted, and the epic-launch path sets `f"Epic launch · {plan_stem}"` explicitly (`src/sase/bead/epic_launch.py:145`). The full command is untouched in the right-hand detail panel (`prompt_panel/_agent_monitor_section.py:67-70`), which is now the only surface for it.

Three follow-on edits: dropped `monitor_command` from `agent_render_key` (`_agent_list_render_cache.py:222`) since the row renderer no longer reads it; updated the help modal glyph legend from `"Monitor member (command)"` to `"Monitor member (label)"` (`agents_bindings.py:421`); and flipped the test assertion to require the command's *absence*.

`just check` — all lint gates green; 29,476 tests passed, 2 failed.

## The two failures are pre-existing, not mine

1. **`tests/main/test_project_handler_list_show.py`** dies at collection on a circular import (`sase.project_aliases` ↔ `sase.memory.read_log`). Confirmed by stashing my tree and re-running on clean master — identical error. Filed as **sase-kw** (ready, size `small`): `read_log.py:35` and `proposals/paths.py:9` both import `resolve_project_alias_ref` at module scope though their only uses are function-local, so a deferred import should close it. Noted its relationship to sase-ku.1 (whose phase worker recorded the same thing as a PROPOSED FOLLOW-UP awaiting land triage), sase-kf, sase-kt, and sase-kq.

2. **`test_start_monitor_promotes_a_bare_lane_and_runs_to_completion`** failed in the parallel lane but passed on the isolated node, on `tests/monitor/` with `-p no:randomly`, and on `tests/monitor/` in random order. A note on epic sase-j7 from sase-kp.land already calls this "a separate, understood claim-release race owned by epic sase-kp." Rather than file a duplicate, I added a `DISCOVERED ISSUE:` note to **sase-kp** recording that it still reproduces at 829030f97 — a tree that predates the `monitor_land_fixes` tale — so whoever lands it verifies the fix clears the node instead of assuming it's covered.

## On sase-ku

No conflict. Its landed phases (`afa8178ce`, `dc9da5576`) touch `src/sase/monitor/**`, `src/sase/logs/pipe.py`, and the scan wire; none of my four files appear in `plans:202608/monitor_hardening.md`. I left a heads-up note on the epic anyway, because phase sase-ku.10's end-to-end exercises inspect the live monitor row — the glyph, label, status parens, live runtime, and `✗<exit>`/`⧖` badges are all preserved, so its agent shouldn't report the missing command as a regression.

These are my changes from this session. Committing them now.

Committed as `18f7e22de`; tree is clean and in sync with `origin/master`.

**What landed** — the monitor command no longer renders in the Agents tab left pane:

- `_agent_list_render_agent.py:254-257` — removed the ` · <monitor_command>` append. Rows now show the label only (`⏱ Epic launch · artifacts_tab_icons (MONITORING)` instead of the version that trailed off into `... --ye`). Every monitor has a label: `sase monitor start` derives a default when `--label` is omitted, and the epic-launch path sets one explicitly. The full command is untouched in the right-hand detail panel, which is now its only surface.
- `_agent_list_render_cache.py:222` — dropped `monitor_command` from `agent_render_key`, since the row renderer no longer reads it.
- `agents_bindings.py:421` — help modal glyph legend now reads `("⏱", "Monitor member (label)")`.
- `test_agent_list_monitor_rows.py:52` — assertion flipped to require the command's absence.

`just check` was green on all lint gates with 29,476 tests passing. The two failures were pre-existing and unrelated: a circular import at collection in `tests/main/test_project_handler_list_show.py` (reproduced on clean master, filed as **sase-kw**), and a monitor claim-release race already owned by epic **sase-kp** (added a note that it still reproduces at `829030f97`).

**On sase-ku** — no conflict. Its landed phases touch `src/sase/monitor/**`, `src/sase/logs/pipe.py`, and the scan wire; none of my four files appear in its plan. I left a heads-up note on the epic anyway, since phase sase-ku.10 inspects live monitor rows — the glyph, label, status parens, runtime, and `✗<exit>`/`⧖` badges are all preserved, so the missing command is expected rather than a regression.

One thing worth your attention: the commit reported that this project has **2 quarantined agent-hood publication requests**, so the link written to this commit may stay unavailable until you run `sase agent sync --retry-quarantined`. That predates my work — I didn't run it, since clearing another agent's outbox seemed like your call.
