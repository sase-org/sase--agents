# Chat History - ace-run (research.1q.cld)

- **TIMESTAMP:** 2026-09-09 14:41:03 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1q.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260909_142203.md`

## Prompt

%id(cld, clan=research.1q) %m:@opus_or_grok 
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1q.cdx`, is independently investigating the same request and will write its
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

I'm rethinking the UX design and overall user-experience
associated with sase's new remote dispatch feature.

- See the sase-xe epic bead for context on remote dispatch.
- I know that I want users to be able to easily manage sase agents running on remote
  machines, but I'm not sure how/where remote agents should be displayed in the TUI.
- I'm also not sure about any of our UX choices.
- Finally, I'm not sure if we should bother supporting "Focused" remote agents vs
  "Unfocused" remote agents.

Can you do some research with the goal of helping me decide the best UX (for the
`sase ace` TUI) to support this functionality? Think hard about this and don't be afraid
to make drastic changes. End your analysis with a recommended UX. 
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

I'll start by gathering context on the sase-xe epic bead and the current TUI/dispatch implementation.

Now I'll write the report.

Research complete and registered.

**Report:** `sase/repos/research/202609/remote_agents_are_not_a_place__b.md`
**Artifact:** `file:explicit:bfb8af43d1e4bfa8909eec46` (label `research:202609/remote_agents_are_not_a_place__b.md`)

## What I found

I read epic `sase-xe` and child `sase-xe.16`, the two accepted plans, the shipped fleet code, and — most usefully — the four committed Fleet/Focus PNG snapshots as images. The shipped experience is not the designed one.

Ten verifiable findings, of which three matter most:

- **The machine alias is written into the row's *project* field** (`_fleet_agents_rows.py:189`). A remote agent working on project `sase` appears under a "project" called `apollo`. This kills `group by project` — the only view that could answer "what's happening on project X across my machines" — and it's visible in the narrow snapshot, where `apollo` sits at the same level as `sase`.
- **Remote rows are appended after the fold/filter boundary** (`_loading_apply.py:402`). They bypass the search query, dismiss rules, and fold counts entirely. The list looks integrated and behaves as a second, unfiltered stream.
- **Remote attention is fetched only for followed rows and terminates in a toast.** The notification indicator, panel, mute, and snooze know nothing about remote agents. The one job this feature must do — tell you when a machine you aren't looking at needs you — has no durable surface.

Also: all nine fleet keybindings ship `"unbound"`; `F` (edit hooks) is silently overloaded as remote fork; 21 familiar commands vanish on remote rows; the catalog eagerly pulls 3×100 rows including history; "unavailable" and "zero results" render as pixel-identical blank panels; and machine management exists only as a 12-second toast telling you to go run shell commands.

## Recommendation

**Delete the Focus/Fleet axis.** It models location as a *place* and then invents Follow to undo the damage — and since `%dispatch` auto-follows, "followed" mostly means "I launched this from here," a provenance accident rather than intent.

Instead: one list; `machine:` added to the agent query language; `by machine` added to the existing `o` grouping cycle (which reconstitutes Fleet for free, with folds and counts the user already knows); the follow store **kept** but reframed as a notification subscription where unwatch = the existing mute; machine management moved to an Admin Center **Machines** pane modeled on Projects (which already has an in-TUI init flow); and per-machine capacity promoted to a first-class concept so `%dispatch` finally composes with `%queue` and `%dispatch:auto` becomes possible.

On your third question specifically — **no** to Focused/Unfocused as a view axis, **yes** to keeping the subscription underneath it. The mechanism is right; it was wired to list membership instead of to notification.

I did not run the TUI; my reading of the live experience rests on the committed snapshots and source, and the epic is still open with live proof unmet — some of what I call a UX choice may be unfinished work. The report flags this in its risks section.
