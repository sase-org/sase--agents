# Chat History - ace-run (research.16.cld)

- **TIMESTAMP:** 2026-08-26 13:02:38 EDT
- **MODEL:** claude/opus
- **AGENT:** research.16.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260826_123104.md`

## Prompt

%id(cld, clan=research.16) %m:@research_b  #gh:gh_sase-org__sase We recently added the new "Agents" sub-tab to the "Artifacts"
tab (see the sase-tj epic bead). We also fixed some defects related to / made some
improvements to artifact links (see the sase-tw epic bead). I now want to add a rich
integration with artifact links to every tab in the TUI (even chops can link to the
agent artifacts they were responsible for launching!).

- I think we can accomplish this by adding a single new "Links" panel that allows the
  user to view and traverse the links associated with the currently selected sase
  entity.
- This keymap should also support jumping to the corresponding linked-to entity in the
  TUI using as few key presses as possible (similarly, link traversal should be
  incredibly intuitive and take as few key presses as possible).
- We should use a single keymap across all tabs to trigger this new panel (select an
  appropriate trigger key for this--maybe `$`?).
- We should figure out a way to display the links related to the currently selected
  entity somewhere in the TUI. This location should be the same across all tabs and all
  entities. It should provide useful information about the links but must be very
  concise.
- None of this functionality should be available or visible when the currently selected
  entity does not have any associated links.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of exploring a few different user interfaces for
this new panel and helping me decide the best way to implement it? End your analysis
with a recommended solution and user interface (make sure you think hard about this). Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the existing TUI architecture, the artifact link system, and the two epics you mentioned.

I have the ground truth I need. Writing the report now.

Found a confirmed defect while measuring. Filing it per project rules before finishing the report.

Now updating the report with the corrections and the new prerequisite finding.

The sase repo and sase-core are clean; the only change is the new research report in the research sidecar. Finalizing.

Report written to `sase/repos/research/202608/cross_tab_artifact_links.md` (`research:202608/cross_tab_artifact_links.md`).

## What the measurements decided

Three numbers from the live graph (1,262 rows, 1,852 nodes) drove the whole design:

- **82% of linked entities have exactly one link; 99.8% have ≤9.** This isn't a graph-browsing problem — it's a one-chip problem with a tiny tail.
- **63% of edges are cross-kind.** Following a link is normally a cross-pane, often cross-tab move, so the surface can't be pane-local.
- **Only 3% of agents and 18% of beads have any link.** Your invisible-when-empty requirement is the dominant case, not an edge case.

## Recommendation: the Link Rail

A single app-owned one-line widget docked directly above the keybinding footer — the only location that is literally the same object on all three tabs. It renders numbered chips, and `$` acts as a **one-shot prefix**, not a mode:

`$1`–`$9` follow link N · `$$` follows the lead chip · `$0` opens the overflow panel · `Ctrl+O`/`Ctrl+Shift+O` walk the trail (existing keys).

Two keystrokes reach 100% of entities. `$` is genuinely free — an audit of every `ace.keymaps` value leaves only `"`, `$`, `&`, `\`, `|` unclaimed.

Two things I'd flag as the design's best and riskiest ideas. The best: the destination kind's accent color is painted on the chip's icon, so *hue tells you where the key takes you* — "jump to the bead" vs "jump to the plan" is distinguishable pre-attentively at zero cell cost. The riskiest: I deliberately rejected making a bare `$` jump when there's only one link, even though it saves a keystroke 82% of the time — on Artifacts, bare digits switch sub-panes, so `$2` at a one-link bead would follow the link *and* switch panes. Uniform beats fast there.

About 70% of this already exists in the wrong place: cross-kind ref→target resolution, the cross-pane navigation primitive, the one-shot `.N` prefix (Memory panel), and the bounded traversal trail. The codebase has also hand-built two special-cased single-link jumps (`L` on Beads and Plan panes) that `$1` subsumes.

## One thing to know before building

While measuring I confirmed a defect and filed it as **`sase-ua`** (ready, linked to `sase-u9`/`sase-t0`, noted on epic `sase-tj`): the read model every TUI surface uses, `artifact-links.json`, is 231 rows behind the store and contains **zero** agent-endpoint rows, zero `cites`, zero `read`. A read-only `preview_aggregate()` dry run produces the correct 1,261 rows, so the rebuild logic is fine — the file is just never rebuilt, and no consumer checks.

The user-visible consequence: `sase agent search 'linked:true'` returns 0 of 12,898 despite 193 agents having links. That's the entire deliverable of phase `sase-tw.13` sitting inert. It doesn't change the recommendation, but the Agents-tab adapter can't be demonstrated until it lands, so I made it phase 0 in the report's sequencing.

Section 11 leaves five decisions open for you — the two I'd most like your call on are whether the lead chip should carry the `why` by default, and whether chops become virtual link sources (cheap, recommended) or get a real `chop:` ref kind (proper, but expands a deliberately closed catalog).
