# Chat History - ace-run (research.6e.grk)

- **TIMESTAMP:** 2026-11-25 14:30:33 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** research.6e.grk
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_141135.md`

## Prompt

%id(grk, clan=research.6e)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.6e.cdx`, `research.6e.cld`, `research.6e.mus`, `research.6e.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll start by opening the research repo and reading the skills this work depends on, then investigate how decision memory webs currently render into agent instruction bundles.

I'll open the research checkout next and pull the remaining skills and memory notes this design depends on.

The research-repo open is still running; I’ll wait on it and start mapping how memory webs render into agent instructions.

Research checkout is at `sase/repos/research`. Next I’ll load the memory and CLI notes that govern webs, artifacts, and instruction rendering.

The `webs-render-in-their-own-section` decision already names this token-budget reopen. I’ll map the renderer, CLI, and TUI surfaces next so the design can reuse them.

There's already `roster:` frontmatter and a `sase memory web` command. I'll inspect those next before proposing anything new.

Compaction already exists for list rosters. I’ll trace how bundles apply it and what `sase memory read` currently returns.

I’ll open bob-cli next and measure how much of the instruction bundle the decisions roster actually costs.

bob-cli already blows the Codex cap: the decisions roster is 25,641 bytes, about 70% of that bundle. I’ll draw the design figures and write the report from that evidence.

Figures read cleanly. I’ll copy them into the research checkout and write the report.

The request is a good idea, and it is the reopen condition of `decisions:webs-render-in-their-own-section`. Implement it as a generic roster-inclusion axis, not as decisions-specific machinery.

**Recommendation:** add `roster_load: always | on_demand` on any memory web (default `always`). Runtime bundles honor `on_demand` by replacing the managed roster with a generated stub. Committed `AGENTS.md` keeps the full roster. Agents fetch the catalog with a new audited selector, `sase memory read roster:<web>`, which prints the same numbered list currently inlined into `AGENTS.md` and shows up in the existing TUI MEMORY lane. Opt sase and bob-cli `decisions` into `on_demand`. Leave `glossary` and `task_types` always-loaded. Do not edit `/sase_plan` in v1.

**Justified adjustments** (called out in the report):

- Planner-only is too narrow. Fetch before writing a SASE plan **and** before changing behavior a record might govern.
- Keep the full roster in committed `AGENTS.md` (human-readable projection and fallback). Only runtime bundles stub it.
- Extend `sase memory read` with `roster:<web>`. Do not add `sase memory web roster`, and do not reuse unaudited `sase memory web show`.
- No feature flag, no new TUI lane, no revival of `type:` on descriptors.

**Why it is worth doing:** on sase, `proj.web.decisions` is 8,408 B / 2,102 tok, 38% of the root bundle. On bob-cli it is 25,641 B, 70% of an uncapped 36,911 B bundle, and Codex already compact-fits at 30,365 B. Grok/Claude/Muse still pay the full catalog every turn. Existing cap-driven compaction is a last-resort brake, not a standing policy. A bare `sase memory read decisions` dumps every strand body (74 KB / 233 KB), so a catalog selector is actually missing.

Full report: `research:202611/on_demand_memory_web_rosters__grk.md`  
Artifact: `file:explicit:f04902725ed86054c458d47a` (source left in the research repo).
