# Chat History - ace-run (research.3c.cld)

- **TIMESTAMP:** 2026-10-02 13:13:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3c.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124120.md`

## Prompt

%id(cld, clan=research.3c)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3c.cdx`, `research.3c.grk`, `research.3c.mus`, `research.3c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add
excellent support for the recently added memory file history functionality to the TUI
(see the sase-1dr epic bead for context). I'm pretty sure sase's pager is the only thing
that supports memory history at the moment. Can you do some research with the goal of
helping me decide the best way to implement this? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! End your analysis with a
recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

I'm reading the memory-history epic plan (sase-1dr). Next I'll look at how the TUI's Memory panel and the pager handle history today.

I'm mapping the code now: the ACE Memory panel, the pager's history stack, and the TUI tab layout.

Three explorers came back with a full map. Next I'll check a suspected bug in the existing `H`/`C` path and look at the current visuals.

I'm running a quick headless probe to confirm whether the Memory panel's `H` key actually opens the pager today.

Next I'm checking which pager rendering pieces (pill, scrubber, diff body, picker) the TUI could reuse directly.

I'm grabbing a real render of the Memory pane inside the Admin Center to check how much space an inline history view would have.

The Admin Center render shows the real constraint: at 120×40 the Memory card is only about 52×15 cells. Next I'm checking the service and provider caching for the reliability part of the design.

I've ruled out an Artifacts-tab pane for now: each existing pane runs to 10–15 modules. Next I'm checking free key prefixes for a direct entry point.

I'm checking how the Memory pane's "unpublished" state relates to git, so the time strip doesn't misreport it.

Both `H` and `C` fail the same way. Before writing, I'm checking what the user guide promises about the Memory panel.

I have enough evidence to design. I'm generating aligned mockups with a small script, then writing the report.

Writing the report now.

Report written. Registering it as a durable artifact:

The sase repo itself is unchanged; the only new file is the report in the research repo. Now the required final declaration:

I've written the report and registered it as `file:explicit:39da94ae1b3d317c8e32f223` (label `research:202610/memory_history_in_ace__cld.md`). The host commits it to the research repo when this turn ends.

**You're right that only the pager works.** The epic did add history keys to the TUI's Memory pane: `H` for one note's history and `C` for all changes. But both are silently broken. Each builds its document, then the worker crashes with `RuntimeError: The call_from_thread method must run in a different thread from the app`. The error toast uses the same call, so nothing appears. A headless run that presses each key confirmed this. No test presses either key, and `docs/memory_history.md` still tells users to use them.

**Other gaps:**
- The Memory pane is only reachable inside the Admin Center (`#` → Config → `05 Memory`, or `gm` from the prompt bar). At 120×40 the note card is about 52×15 cells.
- The History row on note cards is an 8-cell sparkline that says little for short histories.
- Every surface builds its own history service, and the pager builds a new one on every lookup. Measured warm: about 54 ms per timeline query, with no caching of repeats.
- The Agents tab never uses the evidence the epic already records (which version of each note an agent read, and its `AGENTS.md` at launch).

**Recommendation: "one model, one reader, four doors."** The pager stays the only deep reader. The TUI gets compact, at-a-glance history views drawn by the same rendering code the pager uses, all backed by one shared, cached history service. Every view hands off to the pager at the exact version you were looking at, never back at "now".

1. **Memory card.** A two-row time strip with the same keys as the pager (`( ) { } = @`). The card frame turns violet while you're in the past. `H` opens the pager at the same version. After an edit the strip turns amber ("uncommitted"); publishing turns it back and adds the new version.
2. **Memory changes review screen** (`C`). A full-screen list of changesets on the left (`j`/`k`) with word diffs on the right. Each shows bead, agent and commit chips, and unread dots backed by a saved review watermark. Marking things read uses the Agents tab's keys (`U`, `,j`, `,u`).
3. **Agents tab.** Each memory read gets a version tag (`v12 ⟲ 2 newer` or `v25 ≡ now`), plus a new `AGENTS.md as launched` row. The hint opens the pager pinned at what the agent actually saw.
4. **The pager everywhere.** Unchanged for users, but it now shares the warm service, so it opens instantly.

**Rejected or deferred:**
- Fixing `H`/`C` alone isn't enough; it becomes the first phase.
- Embedding the pager widget inside the card would need a new host adapter, causes key clashes, and doesn't fit a 15-row card.
- An Artifacts-tab pane would be too large: each existing pane is 10–15 modules.
- A fourth main tab would move memory out of Config, which history alone doesn't justify.

**Phases:**
1. The fix, end-to-end tests that press the keys, and the shared service.
2. The Memory card time strip; absorbs `sase-1en`.
3. The changes review screen; absorbs `sase-1e6`.
4. The Agents tab view; absorbs the TUI half of `sase-1e5`.
5. Polish, including restore-as-draft (`sase-1e7`).

The report also covers mockups, the visual system, reliability and speed targets, keymap wiring, and what belongs in sase-core.

**Decisions for you:**
- Do you want the review screen, or would a fixed pager feed do?
- How loudly should unreviewed memory changes announce themselves? I suggest only a badge on the Admin Center's Memory tab.
- Confirm that viewing history stays unaudited in the TUI, as in the pager.

I didn't file a bug bead for the broken keys, to avoid seeing other researchers' beads during duplicate checks. The report includes proposed bead text for the lead to file.
