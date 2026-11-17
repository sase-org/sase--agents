# Chat History - ace-run (1dl--code)

- **TIMESTAMP:** 2026-11-17 15:05:45 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 1dl--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202611/agents_stranded_count_scope.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- backlog_hint = toast (planner default: toast). Implement the "backlog_hint = toast" branch; ignore "backlog_hint = strip", "backlog_hint = silent". Context: "Should the Agents tab still point at stranded beads that have no loaded agent row?".
- beads_filter = yes (planner default: yes). Implement the "beads_filter = yes" branch; ignore "beads_filter = no". Context: "Add a `status:stranded` filter to the Beads pane so the stranded backlog can be listed?".
Implement only the branches selected above.
%macros_enabled:true


## Response

Implemented the approved `agents_stranded_count_scope` plan with the reviewer branches `backlog_hint = toast` and `beads_filter = yes`.

What changed:

- **Surfaced stranded projection** ([agent_stranded.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/models/agent_stranded.py)): new `surfaced_stranded_leaves()` (own stranded verdict + stranded wait targets + clan-subtree leaves; blocked never counts) and memoized `surfaced_stranded_count()` keyed on roster generation, roster identity/length, and cached report identities, so the info strip stays O(1) on cache hits.
- **Info strip** ([_display_detail_info.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_display_detail_info.py)): both call sites now pass the surfaced count; grammar and zero-suppression unchanged.
- **`,j` navigation** ([_unread_navigation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_unread_navigation.py), [_unread_jump_candidates.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_unread_jump_candidates.py)): stranded jumps use the surfaced-leaves predicate ordered by most-recent `since`; clan containers are jump candidates for stranded jumps only (new `include_clan_containers` flag, so unread/stopped behavior is byte-identical), with ties preferring concrete rows so hidden members still reveal.
- **Triple-miss toast** ([_leader_mode.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agent_workflow/_leader_mode.py)): on a `,j` triple miss with a project-wide backlog, the toast reads `No unread completed, stopped, or stranded agents · ⚐ N stranded beads have no agent row here (Beads: status:stranded)`; unchanged when the backlog is empty.
- **Beads `status:stranded`** ([filter_query.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/bead/filter_query.py), [_beads.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/query_profile/profiles/_beads.py), [bead_filter_bar.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/widgets/artifacts/bead_filter_bar.py), [beads_filtering.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/widgets/artifacts/beads_filtering.py), [beads_filter_session.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/widgets/artifacts/beads_filter_session.py), [beads_pane.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/widgets/artifacts/beads_pane.py), [beads_stranded_refresh.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/widgets/artifacts/beads_stranded_refresh.py)): `stranded` is a derived status fed by an O(1) verdict-index lookup, and the filter-index cache key now folds in the stranded-report token with a rebuild on report change (the Beads status-bar count stays project-wide).
- **Docs**: info-strip paragraph rewritten ([agent-row-glyphs.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/docs/reference/tui/agent-row-glyphs.md)), `status:stranded` documented ([filtering.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/docs/reference/tui/filtering.md)) and named as the backlog worklist ([bead-lifecycles.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/docs/reference/work-units/bead-lifecycles.md)). No help-modal legend describes the strip count, so no modal changes.
- **Tests**: new coverage for surfaced leaves/count/memo, WAITING-row and rowless-clan jumps, the backlog toast, and `status:stranded` matching/negation/index-invalidation; updated the beads query golden; rebased the TUI import footprint baseline (+5,143 bytes, no new modules, per repo precedent); added a missing cache-clear fixture in `test_agent_stranded_detail.py`.

Verification: `just lint` clean, and `sase tool run check` succeeded (exit 0), including the escalated full suite. The one unrelated failure seen mid-way (a gate-capacity timing test under load ~45) passes alone.
