# Chat History - ace-run (research.3p.cld)

- **TIMESTAMP:** 2026-10-05 14:38:48 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3p.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_141626.md`

## Prompt

%id(cld, clan=research.3p)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3p.cdx`, `research.3p.grk`, `research.3p.mus`, `research.3p.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md,
  instruction_bundles_provider_parity_and_memory_ledger.md, and
  fresh_clone_bootstrap_and_native_subagent_instructions.md files in the research
  sidecar repo for context before performing your own research. I agree with all of the
  recommendations made in these research files for the most part, but you should call
  out any issues that you are able to identify.
- I think I want to split this work up into multiple epics with clear completion/exit
  criteria and verifiable results that are easy for me to confirm, but I'm not sure how
  this work should be split up or if it is even advisable to split this work up at all.

Can you do some research with the goal of helping me decide the best way to split this
work up (if at all)? End your analysis with a recommended set of epics (with clear
completion/exit criteria and verifiable results) or justification for why you don't
think that I should split up this work. 
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

Read all three prior reports. Now checking current code state, existing beads, and what (if anything) has already shipped.

Checking the actual code paths the prior reports cite (generator, adapters, invoke boundary, CI) to verify claims and find gaps.

Found that sase-core carries a hand-written (not memory-generated) `AGENTS.md`, and Rust `memory_history` already tracks instruction files as subjects. Checking those dependencies next.

Mapping the existing generator (~7k lines) and its post-commit regeneration hook, then looking at sase-core's release cadence and the remaining consumers.

I have enough evidence. Writing the report now.

Report written. Registering it as a durable artifact snapshot.

I wrote the report, and I recommend splitting the work: five core epics run in order, plus two optional ones that wait for a trigger. Not one big epic, and not one epic per provider. The report is registered as `research:202610/memory_built_instructions_epic_split__cld.md` (ref `file:explicit:3e0a8790c49a2f04881339af`).

**Why split.** Size isn't the problem: epics in this repo land in hours (median 3.7 h for 1–4 phases, about 21 h for 9 or more), and big ones aren't abandoned more often. The problem is that two steps change how every agent behaves, and you'll want several days of real runs before going further. An epic can't wait days, and SASE's flag rules don't let a temporary (beta) flag outlive its epic. So those two waiting periods become the epic boundaries.

**Build a scoreboard first.** Epic 1 starts with one command that reads each provider's own session logs. For each provider it shows:
- how many copies of the SASE contract arrived;
- whether the home and project instructions arrived;
- how many SASE-owned instruction files the CLI loaded natively;
- what subagents received.

Every later epic's exit criterion is a specific change in that output (or a `git ls-files` count), so you confirm each epic by running one command.

| Epic | What it does | How you confirm it |
|---|---|---|
| E1 · Scoreboard + stopgaps | Grok gets instructions via `--rules`; Claude subagents get their own prompt plus a hook that blocks `sase final` | Grok goes from 0 copies to 1; subagent probe attempts are denied |
| E2 · Bundles in shadow mode | Render and record each agent's instructions at every launch, but don't deliver them yet | Coverage on every invocation; renders for different providers differ only in the provider section |
| E3 · Delivery cutover | Each provider gets the rendered instructions once through its own channel, and its native files are suppressed | Every provider shows 1 copy, home and project present, 0 native files |
| E4 · Committed files in the repo | Short generated stub, a gitignored local copy for developers, nested files become path-scoped notes, Memory History fixed | 20 committed instruction files become 2; fresh-clone check passes |
| E5 · Home + other projects | `~/AGENTS.md` and `~/CLAUDE.md` stop telling interactive sessions to run `/sase_final`; `bob-cli` and `actstat` adopt the new files | `grep` finds no "SASE Final Declaration" in your home files |
| E6 (optional) | The TUI views from the ledger report | — |
| E7 (conditional) | Per-audience sections (`when:`, launch facts, `SASE.md`), only once the recorded data shows a real need | — |

There are three good places to stop: after E1 (the measured harm is stopped), after E3 (your stated goal is met for every SASE agent), and after E5 (all files migrated).

**Problems I found in the three reports:**
1. **The proposed Grok quick fix would duplicate the contract.** It sends both the project and home instruction files through `--rules`, and both contain the full SASE contract. It also leaves out the single-turn directive, which Grok doesn't get today.
2. **"A feature flag per provider, all in one epic" breaks SASE's flag rules.** Instead, use one kill-switch flag that keeps the old file-based delivery reachable, and remove it after the waiting period.
3. **No report covers Memory History.** sase-core builds its instruction-file history from the committed files, including the INSTRUCTIONS rail just shipped in sase-1ev.9. Deleting or untracking those files changes it, so E4 has a phase for this.
4. **Claude's own auto-memory differs per workspace.** 35 notes sit in 8 of the 46 workspace folders, so what a Claude agent "remembers" depends on which `sase_<N>` it lands in. I recommend turning it off in SASE runs (in E3) and filing a task to move those notes into SASE memory.
5. **Phase agents can only edit memory files the approved plan names.** Each epic plan has to list every memory change explicitly, or the phases will stall.
6. **The proposed "lean monitor and gate" instructions have no target.** Monitor and gate turns never call an LLM provider. That leaves little real demand for the audience machinery, which is why E7 waits.

The report also covers these smaller points:
- The scope is about 45 files across 9 repos, not 20. I recommend leaving the hand-written files in linked repos like sase-core alone.
- "Receipt" is already a glossary term; I suggest calling the per-launch record an "instruction manifest".
- `sase doctor` has no subcommands, so `sase doctor instructions` doesn't fit.
- Rendering on every launch needs a cache and a time budget.
- The ledger report's first-phase TUI work would be thrown away.
- The Rust/Python split should be decided in each plan, not discovered in review.
- Each epic's exit criteria need to be kept separate from the metrics you watch afterwards.

The report ends with a checklist to copy into each epic plan.
