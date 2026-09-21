# Chat History - ace-run (research.21.cld)

- **TIMESTAMP:** 2026-09-19 07:49:23 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.21.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260919_071917.md`

## Prompt

%id(cld, clan=research.21) %m:grok/grok-4.6 %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.21.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

The `@epic` agent tribe
panel still disappears and reappears (i.e. flickers) sometimes on the "Agents" tab.
We've tried to fix this several times before now. Can you do some research with the goal
of helping me figure out what's causing this / what we need to do to mitigate this? End
your analysis with a recommended solution. Make sure to organize your contents
appropriately using markdown sections. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

I'll research the Agents-tab `@epic` tribe-panel flicker independently, then write a `__b` report and register it as a durable snapshot. First I'm loading the relevant SASE skills and locating the Agents UI code.

I'll record skill use, inventory the project, and search prior work on the Agents-tab flicker before opening any code.

I'll search beads, chats, and the Agents-tab tribe-panel code in parallel so we can reconstruct prior flicker fixes.

Background searches are still running; I'll start on the tribe-panel source and prior flicker reports in parallel.

There's already an `agents_tab_flicker` epic and later chats about remaining flicker; I'll pull that plan, git history, and the tribe-panel remount path next.

I'll open the plans and research sidecars, then read the flicker epic and the tribe-panel remount path.

sase-127 already targeted this flicker and is marked done; I'll check what still remounts tribe panels after that landing.

Live traces show 2→1→2 panel flaps, including 0-agent flashes in ~50ms. I'll write the independent `__b` report from that evidence and the remaining code holes.

The `@epic` panel still flickers because it is not a stable widget. It is a slot in an index-addressed list, and two remaining holes still tear that slot down after the earlier fixes.

Independent report (researcher B): `sase/repos/research/202609/agents_tab_epic_tribe_panel_flicker__b.md`  
Registered snapshot: `research:202609/agents_tab_epic_tribe_panel_flicker__b.md`

**What is happening.** Split-panel widgets are keyed as `agent-list-panel`, `agent-list-panel-1`, … not as `epic`. `panel_keys_for` only keeps a tribe that currently has a rendered row. A 0-row apply becomes a single empty `@default` panel, so `@epic` unmounts and later remounts with `initially_expanded` reapplied. A neighboring tribe appearing or disappearing remaps the same DOM node, so `@epic` also *looks* like it vanished when its own membership did not change. Every full rebuild starts with `clear_options()`.

**What already landed.** sase-127 stopped the 171↔484 load-tier swing and the blanket active-search *display* fallback. sase-12p admitted BY_STATUS to the incremental path and explained stale imported TUI code. 3962d8819 stopped provider-icon flicker from mutating live row graphs. Those soaks could still pass while this remaining mechanism is live.

**What is still wrong on this host today** (`by_status` + standing query `NOT machine:apollo`):

1. Empty incomplete applies still reach the display. Live traces show `2 panels / 17 agents → 1 panel / 0 agents → 2 panels / 17 agents` in ~50 ms. Incomplete merge still skips unless the complete-history latch, an artifact delta, or `bounded_prefix and has_more` is set; revalidate incoming size on the main TUI is still 41–696.
2. Row-remove still bails on any nonempty search query (`active_search` in `_try_remove_agent_rows`). sase-127.2 fixed the display-diff path; this helper was left behind. With this host’s query always on, any identity leaving the visible set full-rebuilds every panel, including `@epic`.

**Recommended fix, in order**

1. Key `AgentList` widgets by tribe, insert/remove one panel without rebuilding siblings, and keep configured tribes (at least bundled `epic`) mounted as empty/collapsed strips for the session.
2. Patch rather than replace any incomplete load once a larger cache exists; never publish a 0-row incomplete apply over a nonempty cache; delete the remaining `active_search` row-remove guard.
3. Restart the interactive TUI onto that tree and soak with traces that assert epic widget identity and `panel_keys`, not just “it looked mounted for 30 minutes.”

Do not treat this as a core/Rust bug, and do not fix it by slowing refreshes or forcing full-history loads on every tick.
