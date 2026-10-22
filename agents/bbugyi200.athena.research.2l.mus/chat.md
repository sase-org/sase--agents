# Chat History - ace-run (research.2l.mus)

- **TIMESTAMP:** 2026-09-26 09:44:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.2l.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_093123.md`

## Prompt

%id(mus, clan=research.2l)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 4-researcher swarm.
The other researchers, `research.2l.cdx`, `research.2l.grk`, `research.2l.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Once card blocks are
fully implemented (see the sase-19x epic bead for context), I want to improve the UX to
make it clear whether the spread or paged view is enabled for a deck and/or card. I also
want to add one or more new keymaps that allow the user to toggle through the 3 states
(fully spread, paged deck and spread card, paged deck and paged card).

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about what the best UX for this functionality is. End your analysis
with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete.

Report written to [deck_card_view_mode_toggle__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/deck_card_view_mode_toggle__mus.md:1) and registered as `research:202609/deck_card_view_mode_toggle__mus.md` (artifact `file:explicit:632208a0a03454b58985d958`). Final declaration accepted for commit.

Key findings:

- The real defect is mode invisibility, not just missing motion: the subtitle shows a dim `spread` tag only when spread (paged = absence of tag), and block-spread vs block-paged has no indicator at all.
- There are 3 states, not 4 — a spread deck always spreads its blocks (epic D3 invariant), so a two-toggle design would have an invalid corner.
- Recommended solution: one cycling keymap `cycle_deck_card_view` on `v` (the only clean free mnemonic on the Agents tab; `V`, `s`/`S` are taken), wrapping fully-spread → paged deck + spread card → paged deck + paged card as a panel-local ephemeral override cleared on subject change, with transitions via the existing `ReadingAnchor` mechanism — plus an always-on 3-valued subtitle tag and block-rail mode word so the toggle has visible confirmation. Full `sase-19x.7` keymap pipeline enumerated in the report.
