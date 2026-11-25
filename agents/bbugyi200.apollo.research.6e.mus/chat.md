# Chat History - ace-run (research.6e.mus)

- **TIMESTAMP:** 2026-11-25 14:21:25 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.6e.mus
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_141135.md`

## Prompt

%id(mus, clan=research.6e)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.6e.cdx`, `research.6e.cld`, `research.6e.grk`, `research.6e.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The decisions memory web for this project and the bob-cli project is taking up way too
much context for each sase agent. I would like to mitigate this somehow.

- These decisions should probably only be read by planner agents (i.e. agents that use
  the /sase_plan skill). Note, however, that we can not modify the /sase_plan skill
  directly with these instructions since it is used by all sase projects (most of which
  will not have this custom decisions memory web).
- It follows that we should stop rendering the full decisions roster in agent
  instruction bundles.
- The decisions memory is just a specific memory web though, which we should not add
  custom support for, so we need to be able to handle memory webs like this generically
  (i.e. for any memory web we want).
- The best solution I can think of is to configure the decisions memory so it stops
  rendering the roster and instead renders instructions that state that any agent that
  is writing a SASE plan (i.e. invoked the /sase_plan skill) MUST read the decisions
  memory roster. This "decisions memory roster" should be retrievable by running a
  `sase memory` command and should look a lot like the roster that is currently in the
  AGENTS.md file. I'm not sure if we have an appropriate `sase memory` command for this
  yet (if not, you should add one).
- We will need to make sure that we audit this memory web roster read and display it in
  the TUI in the appropriate place.
- As a part of this change, we should update the decisions memories appropriately for
  both of these projects (sase and bob-cli).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
First run `sase repo open research -r "Write this research report"` and use the path it prints as `<research checkout>`. Write this research to a new markdown file under `<research checkout>/202611/`.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path under the opened research checkout and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Report written and registered.

- Wrote [deferred-memory-web-rosters__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/deferred-memory-web-rosters__mus.md) under the research checkout (`202611/`), no overwrite.
- Registered as durable snapshot: `research:202611/deferred-memory-web-rosters__mus.md` (ref `file:explicit:cd45f95cf62dfcbcb0cb2bde`).

Top finding: the proposal is sound with adjustments. The decisions roster costs ~2,100 of ~5,550 bundle tokens (~38%, measured via `sase instructions render -s`), and no roster-only audited read exists today (`show` dumps all 31 strand bodies unaudited). I recommend a generic `roster: deferred` frontmatter mode plus `sase memory web roster <web> -r`, reusing `render_strand_roster` so output matches today's AGENTS.md roster by construction, with audit encoded as `kind="web"` + empty `included_targets` (no schema bump, no Rust change), TUI surfacing on the existing Memory-panel web card, plan-citation obligation for implementers, and a new `deferred-rosters` decision strand per the project's own immutability rule.

Declaration submitted: commit of `202611/deferred-memory-web-rosters__mus.md` in sdd:research.
