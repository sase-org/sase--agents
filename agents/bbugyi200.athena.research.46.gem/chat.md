# Chat History - ace-run (research.46.gem)

- **TIMESTAMP:** 2026-10-09 11:49:18 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.46.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_112907.md`

## Prompt

%id(gem, clan=research.46)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.46.cdx`, `research.46.cld`, `research.46.grk`, `research.46.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to make my macbook (which is not a powerful machine) the main driver of
sase's TUI by finishing the implementation for remote machine support.

- Because my mac has low resources, I probably won't run many agents on that machine.
  I'm fine with needing to manually specify the `%dispatch` directive (whcih we should
  add a `%d` short-hand for) when launching remote agents from sase's TUI on my macbook
  for now.
- I need to be able to reliably perform EVERY agent operation that I can currently
  perform from the "Agents" tab on local agents on remote agents as well.
- It is fine if remote agent data is slow to sync locally (or even exclusively manual
  via a new keymap that syncs the currently selected remote machine's data, which we
  should add anyway, if necessary to keep my macbook from using too many resources) as
  long as ALL of that data is able to be synced and displayed in the TUI on my macbook.

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

# Research Report: Remote Machine TUI Driver Architecture & Implementation Plan

**Report Path:** [`sase/repos/research/202610/remote_machine_tui_driver_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/remote_machine_tui_driver_architecture__gem.md)  
**Registered Artifact:** `research:202610/remote_machine_tui_driver_architecture__gem.md` (`explicit:fb8cae628899d59547130eca`)

---

## Executive Summary & Architectural Critique

Your objective is to turn your resource-constrained MacBook into the primary driver of SASE's TUI by completing remote machine support, dispatching via `%dispatch` (with a `%d` shorthand), achieving operation parity on the **Agents** tab for remote agents, and avoiding resource exhaustion via slow or manual synchronization.

### 1. Critique: Is this a good idea? Would we take a different approach?

#### The "Resource Paradox" of the Local TUI Controller
Running SASE's TUI locally on macOS is **not lightweight**:
- Textual's Python runtime maintains reactive widget DOM trees, CSS styling layout passes, Rich text rendering, and high-frequency event loops.
- SASE runs a local background Rust supervisor daemon (`sase_federation_worker`), active filesystem watchers (`watchdog`/FSEvents), SQLite query engines, and local Git repository scans.
- On a low-resource MacBook, running `sase tui` locally consumes 150–300 MB of RAM, triggers periodic CPU wakeups, and consumes battery.

**The Pragmatic Alternative (The Thin Terminal):**
If you have a powerful remote Linux devbox/desktop, running `sase tui` inside a persistent `tmux` session directly on that remote machine and connecting from your Mac via an SSH terminal emulator (e.g., Ghostty, Alacritty, or Terminal.app) has **vastly lower resource overhead**:
- MacBook RAM: ~20 MB (just the terminal emulator).
- MacBook CPU: 0.1% idle.
- Battery impact: Negligible.
- Feature Parity: **100% immediate parity**—every single local operation (`open_tmux`, `$EDITOR` spec editing, diff viewing, revives, local tool execution) already works out of the box with zero code changes, zero Tailscale sync lag, and complete resilience across laptop lid closes.

#### When Does the Local TUI Controller Make Sense?
If your setup involves a **heterogeneous multi-machine fleet** (e.g. 1 MacBook acting as a control plane dispatching between a home server, an office workstation, and a cloud GPU box), or if you need native macOS windowing, notifications, and clipboard integrations, then running SASE's TUI controller locally is justified.

#### The "Full Sync" Antipattern
Attempting to sync "all remote agent data" onto the MacBook locally contradicts the low-resource requirement. SASE agents run in ephemeral Git workspaces (`sase_<N>`) and generate large `transcript.jsonl` files (often 10–50 MB each), tool execution outputs, and git objects. Eagerly mirroring entire workspaces across Tailscale will thrash your MacBook's SSD and network. 

**The Solution:** Use **on-demand bounded streaming** (via SASE's existing `/api/fleet/v1/content` handles) and **SSH transport handoffs** (`ssh_target`), *never* bulk disk replication.

---

## 2. Requirement Adjustments

| Requirement | Proposed Adjustment | Rationale |
| :--- | :--- | :--- |
| **`%dispatch` / `%d` shorthand** | **Approved + Enhanced:** Add `%d` as an official alias for `%dispatch`, and add `dispatch.default_target: <alias>` in config. | Immediate ergonomic win; default target removes the need to type `%d` on every prompt. |
| **"EVERY local agent operation on remote agents"** | **Classified into 4 Implementation Tiers:**<br>1. *Direct Fleet RPC:* Stop (`x`), Retry (`R`), Fork (`F`), Revive.<br>2. *Attention/HITL:* Questions (`Enter`), Plan gate approval with round-trip buffer.<br>3. *On-Demand Streaming:* Native Main Deck (Chat) and Files Deck (Diffs) instead of popup modals.<br>4. *SSH Transport Handoff:* Tmux attach (`t`) routes over SSH using `ssh_target`. | Local workspace filesystem operations cannot run directly on remote paths; they must be cleanly abstracted into RPC streaming or SSH handoffs. |
| **Slow / Manual Sync Control** | **Approved:** Add `dispatch.federation.sync_mode: manual` to suspend background polling, and add a dedicated `sync_selected_remote_machine` keymap (`gs` or `Ctrl+S`). | Completely prevents the MacBook from running hot or churning network bandwidth in the background. |

---

## 3. Codebase Gap Analysis

SASE already contains strong federation building blocks (`sase_gateway` in `sase-core`, `sase_federation_worker`, and `RemoteContentClient`), but several critical gaps currently block full parity:

1. **`%d` Directive Parsing:**
   - [`src/sase/macro/_directive_types.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/_directive_types.py): `"d"` is currently unmapped in `_DIRECTIVE_ALIASES`.
   - [`src/sase/macro/_directive_scan.py:94`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/_directive_scan.py#L94): `if "%dispatch" not in prompt:` skips scanning if only `%d` is provided.
2. **Main Deck Isolation:**
   - Remote agent chat/transcripts currently do not render in `DeckId.MAIN`. Instead, `_open_agent_chat` redirects to `RemoteContentModal` via an unbound key (`view_remote_agent_content`), leaving the detail panel empty during normal `j`/`k` list navigation.
3. **Files & Tools Deck Gated Off:**
   - [`src/sase/ace/tui/widgets/decks/availability.py:48`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/widgets/decks/availability.py#L48): `probe_files_deck()` returns `DeckAvailability(False, 0)` for remote rows.
   - `probe_tools_deck()` explicitly suppresses tool runs for remote rows.
4. **Action Availability Restrictions:**
   - [`src/sase/ace/tui/_app_action_availability_agents.py:290`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/_app_action_availability_agents.py#L290): Hardcodes `False` for `_LOCAL_AGENT_ROW_ACTIONS` on remote agents, disabling `open_tmux`, `jump_to_agent_patch`, `view_agent_metadata`, and `toggle_agent_unread`.
5. **Tmux / Terminal Handoff:**
   - [`src/sase/ace/tui/actions/agents/_panel_tmux.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/actions/agents/_panel_tmux.py) expects a local workspace path, even though `sase` already has `resolve_remote_ssh_target()` for SSH connectivity.

---

## 4. Recommended Implementation Roadmap

### Phase 1: Launch Ergonomics (1–2 days)
- Register `"d": "dispatch"` in `_DIRECTIVE_ALIASES` in [`_directive_types.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/_directive_types.py).
- Update regex in [`_directive_scan.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/macro/_directive_scan.py) to recognize `%d:<target>` and `%d(target)`.
- Support `dispatch.default_target: <alias>` in config resolution so manual directive typing can be omitted when targeting a single remote box.

### Phase 2: Native Deck Presentation & Streaming (3–5 days)
- Connect [`RemoteContentClient`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/dispatch/content.py) directly to `DeckId.MAIN` in [`AgentDetail`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/widgets/agent_detail.py) to stream transcripts in the native deck panel.
- Connect `RemoteContentClient` to `DeckId.FILES` to stream git diff handles from `/api/fleet/v1/content`.
- Remove modal barriers and unblock the metadata pager for remote rows.
- Cap in-memory remote content chunk caching to an LRU maximum of 30 MB.

### Phase 3: Terminal & Workspace Operations (2–3 days)
- Wire `action_open_tmux` (`t`) in [`_panel_tmux.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/ace/tui/actions/agents/_panel_tmux.py) to use `resolve_remote_ssh_target()` and spawn `ssh -t <target> "tmux attach -t <session>"` in the terminal.
- Support jump-to-patch for upstream published branches.

### Phase 4: Mutations & Throttled Sync Control (3–5 days)
- Add `dispatch.federation.sync_mode: manual` setting to turn off background tab-switch and timer polling.
- Implement `sync_selected_remote_machine` keymap action (bound to `gs` or `Ctrl+S`).
- Add remote `Revive` mutation to `sase_gateway` (`crates/sase_gateway/src/fleet_mutations.rs`) and wire `action_agents_revive`.
- Implement round-trip plan buffer editing for interactive HITL gates.

---

The complete research report with architecture diagrams, code diff outlines, and detailed comparison matrices has been saved and registered at:
[`sase/repos/research/202610/remote_machine_tui_driver_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/remote_machine_tui_driver_architecture__gem.md)
