# Chat History - ace-run (1dl--plan)

- **TIMESTAMP:** 2026-11-17 12:49:56 EST
- **MODEL:** claude/opus
- **AGENT:** 1dl--plan

**Plan:** /home/bryan/.sase/plans/202611/agents_stranded_count_scope.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/agents_stranded_count_scope.md`

> # Scope the Agents-tab stranded count to what the Agents tab can show
> ## Diagnosis
> The Agents info strip renders `⚐ N stranded` next to the agent counts
> (`85 [5 running · 29 waiting · 51 done]`), so it reads as "N stranded agents". It
> actually counts **stranded beads across each project's whole bead store**:
> - `src/sase/ace/tui/actions/agents/_display_detail_info.py` (both the `update_state` and
>   the `update_agent_counts` paths) calls `stranded_count_for_agents(roster)`.
> - `stranded_count_for_agents` (`src/sase/ace/tui/models/agent_stranded.py`) maps the
>   roster to the project keys it represents. It then returns
>   `_StrandedReportCache.stranded_count`, which is `sum(len(report.stranded_ids))` over

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Why does the TUI show that there are 142 stranded agents but there do not seem to
be any stranded agent nodes? See the ~/tmp/screenshots/20261117_124019.png screenshot
for context. Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Let me load the live stranded report for the `sase` project to see what those 142 beads are.

The reports came back empty, which could mean a silent collector failure or the wrong project key. I'll turn on logging and check which project keys the TUI actually uses.

Project keys look like `gh_sase-org__sase`. Rerunning with those.

I'll read the original plan to see what the info-strip count was meant to show.

I've found the cause. Now I'm checking how the Beads pane's derived status filters (`blocked`/`launched`) work, so the plan can add a matching `stranded` filter.

I have the full picture. Next I'll load the planning skill and write the plan.

No existing bead covers this. One related in-flight phase is `sase-1t3.11.1.5`, which reworks stranded fact collection; I'll note the possible overlap. Writing the plan now.

The validator wants `title`/`goal`, shorter choice labels, no `none` key (a YAML null word), and a boolean shape for `beads_filter`. Fixing those.

The plan validates. Submitting it.

The header's "⚐ 142 stranded" isn't counting stranded agents. It counts stranded **beads** across the whole bead store of every project that has an agent row loaded. Almost all of those beads belong to agents that went into the Archive long ago, so nothing in the Agents tab can show them. Yes, it's worth fixing, and I've proposed a plan for it.

**Where the number comes from:** `_display_detail_info.py` calls `stranded_count_for_agents()` (`src/sase/ace/tui/models/agent_stranded.py:488`). That adds up every stranded bead in each represented project's report, whether or not any row on screen relates to it. The original stranded-work plan chose a project-wide count on purpose. But the other Agents-tab features (the `STRANDED` row label, the `,j` stranded jump, Enter to resolve) only look at loaded rows. That's why `,j` said "No unread completed, stopped, or stranded agents" while the header said 142.

**The live data matches:**
- **Projects:** `sase` has 136 stranded beads and `bob-cli` has 5, which is 141, about the 142 in your screenshot.
- **What they are:** 64 epics, 71 phases and 1 task.
- **Why they're stranded:** 104 ended without closing their bead, 14 lost their last turn, 13 ended with "keep", and 5 had a failed follow-up.
- **Age:** 95 are more than 30 days old; the oldest, `sase-j7`, is 98 days old.

The classifier is right that these beads are open with nothing working on them. The problem is that this backlog is counted in a place that can't show it.

The one real flag in your screenshot is the `⚐1` on the `sase-1tb` clan row. That was almost certainly `sase-1tb.1`: it committed at 12:27 but left its bead `in_progress`. It's been picked up again since.

**The plan** (a medium-sized single-agent plan, now waiting for your approval):
1. **Header count:** count only stranded beads that a loaded row flags, either on its own row, as something a waiting row is waiting on, or inside a clan.
2. **`,j` jump:** make the stranded jump use the same set, including clan and waiting rows, so it can reach every bead the header counts.
3. **Beads pane:** add a `status:stranded` filter so the project-wide backlog has a list you can work through. This is a decision in the plan, defaulting to yes.
4. **Pointer to the backlog:** a second decision controls how the Agents tab points at stranded beads it can't show. The default only mentions them in the `,j` "nothing found" message; the other options are a dim `+N in Beads` in the header, or no mention at all.
5. **Docs and help:** update the stranded-work docs and help text, and add tests.

It's display-only, with no change to the stranded classifier in sase-core. Clearing out the ~140 old beads is still up to you, for example with `w` (resolve) in the Beads pane or `sase bead close`.
