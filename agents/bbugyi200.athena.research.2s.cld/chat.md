# Chat History - ace-run (research.2s.cld)

- **TIMESTAMP:** 2026-09-27 16:21:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2s.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_154958.md`

## Prompt

%id(cld, clan=research.2s)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2s.cdx`, `research.2s.grk`, `research.2s.mus`, `research.2s.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm going to
implement goals for sase soon, but am worried this might be a very large epic that is
hard to verify. Can you do some research with the goal of helping me split this up into
multiple, distinct, and verifiable epics? If a single epic is more appropriate, say so!
See the sase_goals_design.md file in the research sidecar repo for context before
performing your own research. End your analysis with a recommended solution. 
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

Reading the goals design doc from the research sidecar now.

Checking which in-flight epics touch the same code areas as Goals.

I have what I need. Checking that the filename is free, then writing the report.

Report written. Registering it as an artifact now.

Registration worked. Now submitting the final declaration.

I've written the report and registered it. My recommendation: **don't build Goals as one epic. Split it into six epics, plus one small bug-fix task first.**

**Why not one epic.** The design adds up to about 35 phases and touches five separate Rust interfaces. Your own bead history shows that past about 7 phases, epics get much less reliable:

| Phases per epic | Relaunched | Spawned a follow-up child epic |
|---|---|---|
| 6–7 | 29% | 22% |
| 8–9 | 53% | 29% |
| 12 or more | 67% | 58% |

The big feature epics that went badly (`sase-xe`, `sase-zm`, `sase-x7`) were the same kind of work Goals is: cross-cutting interface changes that had to be checked live across machines. The `sase tool` series, split into epics of 6–7 phases, closed its first three in 38h, 7.6h and 27h. The one that went to 9 phases needed a follow-up epic.

**The split:**

| # | Epic | Phases | What you can check when it lands |
|---|---|---|---|
| pre | Small task: notification jumps open collapsed agent rows | — | Jumping to an agent inside a collapsed group selects it |
| G1 | Goal storage, `sase goal` commands, `goal:` references | 6 | A goal created on athena shows up in `sase goal list` on apollo; the list stays under 50 ms with 100k finished goals |
| G2 | Automatic binding when the host already knows the goal (`%goal`, plans, child agents) | 6 | Every agent in an approved epic carries the goal id; `sase goal audit` lists agents with no goal |
| G3 | Claims and your verify step | 7 | A finished epic produces exactly one Verify gate with evidence; rejecting it from Telegram relaunches onto the goal |
| G4 | Drafts: agents name a new goal or adopt an existing one | 6 | A question agent names its own goal; a 5-agent swarm makes one goal; no agent runs without a goal |
| G5 | Goals tab and Agents-tab links | 6 | The badge matches the Review count; numbered jumps and `v` to verify work |
| G6 | Silence success notifications | 5 | Successful runs go quiet and claims ping instead; a before/after notification count |

Order: G1 → G2 → G3 → G4 and G5 in parallel → at least a week of real use → G6. That's roughly 2½–3½ weeks in total.

**Where this differs from the design's own P0–P4 rollout:**
- **Claims come before drafts.** Claims get tested first on epics, where the goal comes straight from the plan and today's noise is worst. That keeps "does the agent claim honestly?" separate from "does the agent name or adopt goals correctly?", and each gets its own metrics.
- **Each part that's hard to verify gets one owner and a way to measure it.**
  - Missing bindings across the 14 launch paths: `sase goal audit` (G2).
  - Claim accuracy per model: `sase goal stats` (G3).
  - Cross-machine sync: two-clone tests, in G1 only.
  - Screenshot tests: only G5 changes them.
  - "Did silencing lose anything?": coverage measured during the soak before G6 is allowed to start.
- **The design's P0 isn't an epic.** One piece becomes the small task above and another moves into G4. The parent-lineage prerequisite is mostly unnecessary: the `%tab` inheritance that landed today (`aff4fc082f`) already passes values down to child agents, and G2 can copy it.
- **The goal finalizer never fails an agent run.** Any problem falls back to "keep open" with a diagnostic.

**Three code facts from checking against the current tree:**
- Built-in finalizers are hard-coded in about 12 Python files, and the Rust interface rejects unknown fields. That makes the goal finalizer the biggest single cost in G3.
- The FINAL deck is still behind a beta flag, so the Goal card on it waits for `sase-1b2` to land.
- The launch path that carries structured launch data is still behind a beta flag. G2 should look up the goal in the runner before the agent starts, so it works whether or not that flag is on.

**Suggested first steps:**
1. Record a decision note: "host binds, agents claim, users settle".
2. File the jump-fix task.
3. Close `sase-rr`: all its phases are done but the epic is still open, and it owns the finalizer code G3 changes.
4. Decide whether goal titles and claims can be public, since the beads repo is public.
5. Write only the G1 plan now.

The G6 start thresholds (for example 90% coverage and 80% of claims accepted) are my proposals for you to confirm.

The report is registered as `file:explicit:862dd3d3752e30bf0bc110d5` and will be committed to the research repo when this turn ends.

Files are in the research repo:
- sase_goals_epic_split__cld.md (in 202609/)
