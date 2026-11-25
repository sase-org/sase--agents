# Chat History - ace-run (research.6e.cld)

- **TIMESTAMP:** 2026-11-25 14:30:20 EST
- **MODEL:** claude/opus
- **AGENT:** research.6e.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_141135.md`

## Prompt

%id(cld, clan=research.6e)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.6e.cdx`, `research.6e.grk`, `research.6e.mus`, `research.6e.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Opening the research checkout worked. Now I'm surveying how memory webs render into instruction bundles, and checking the bob-cli decisions web.

Prior bob-cli research artifact didn't resolve, so I'm skipping it. Now measuring the bob-cli decisions corpus directly (strand count, superseded share, summary lengths).

Design is taking shape. Before settling the read-command syntax, I'm checking the audit log for how often agents actually use bare-web reads (`sase memory read decisions`, which dumps every strand).

Read events record each agent run's `artifacts_dir`, so `sase plan validate` can check reliably whether the current planner read a required roster. Checking where plan validation lives.

Codex has a 32 KiB instruction cap, and bob-cli's AGENTS.md is already 35.8 KB. Checking whether bob-cli Codex bundles are being compacted today.

I have everything needed for the recommendation. Loading the Mermaid diagram skill so the report's flow figure renders properly.

Environment failure (sandbox); retrying with the no-sandbox puppeteer config as the recipe specifies.

Figure renders at 100% fit and answers its question. One last check: whether the glossary's Memory Web definition would need updating too (audited read).

Glossary definition also needs updating. Writing the report now.

Report written. Registering it as a durable artifact snapshot.

Artifact registered. Finishing the turn through the SASE final declaration.

I recommend making the decisions roster load on demand, as you proposed, but with four changes so planners reliably read it. The report is written to `202611/on_demand_memory_web_rosters__cld.md` in the research repo and registered as artifact `research:202611/on_demand_memory_web_rosters__cld.md`. The host commits the research repo after this turn ends.

**Why it matters.** The decisions roster is about 38% of sase's instruction bundle (~2,000 tokens) and about 68% of bob-cli's (~6,300 tokens). In the last 30 days only 19% (sase) and 33% (bob-cli) of agents that read any memory read even one decision. bob-cli's Codex bundle is already being shrunk to fit Codex's 32 KiB cap, with about 2 KB left. bob-cli adds about 30 decisions a month, so it will hit Codex's fallback to native file delivery within weeks.

**Critique of the plan:**
- **The sentence in AGENTS.md fires at the wrong time.** Agents read it at turn start but decide to plan much later. It needs a check at planning time, not just a "MUST".
- **"Planners only" skips today's biggest readers.** Research agents make 78% of sase's decision reads, and epic phase workers make 37% of bob-cli's.
- **bob-cli's roster is written as rules for everyone.** Its descriptor says "Each roster summary is a rule to follow as written", so this is a policy change for bob-cli that should be accepted deliberately.
- **The right command already exists but does the wrong thing.** Agents already run `sase memory read decisions` asking for "the decisions index". It currently dumps every record body, up to about 190 KB per read in bob-cli.
- **The repo already expects this.** The `webs-render-in-their-own-section` decision names this exact cost as its reopen condition, so a new decision record is needed.
- **Hidden sase-core dependency.** The Rust audit query (`audit_query.rs`) silently drops any read kind other than note, web or strand. A new "roster" read kind would never show in the TUI unless sase-core changes first.

**Requirement changes I'm proposing (all called out in the report):**
1. **One generic flag in `/sase_plan`.** Its existing first step becomes `sase memory read sase_sizes.md --for plan …`. It reads whatever the current project requires for planning, which is nothing in most projects, and adds no decisions-specific text.
2. **SASE generates the pointer text.** Two descriptor keys replace hand-written instructions: `roster_loading: on_demand` and `roster_required_for: [plan]`.
3. **The bare web read becomes the roster read.** `sase memory read decisions` returns the roster, with the same entries as today's AGENTS.md section. The old dump moves to `-a/--all-strands`, behind a temporary feature flag while callers migrate.
4. **`sase plan validate` rejects a plan** inside an agent run if a required roster wasn't read in that run. The error names the exact command to run.
5. **Planners cite the records that govern their plan** as `decisions:<keyword>`, so implementers read only those.

**Recommended solution.**
- **Every agent** sees a pointer of about 110 tokens instead of the roster.
- **Planners** get an audited roster read. It is recorded as a new "roster" read kind and shown in the TUI's MEMORY lane and the memory panel's web card. A "Consulted" line in the plan approval modal is a recommended follow-up.
- **Memory updates:**
  - **sase:** a new decision record that partly supersedes `webs-render-in-their-own-section`, plus updates to the Memory Web glossary entry and the generated text.
  - **bob-cli:** a descriptor rewrite that states the policy change openly, plus an optional decision record.
- **Rollout:** sase-core first, then sase, then the memory changes in both projects.
- **Expected bundle sizes:** sase drops from about 22 KB to 14 KB, and bob-cli from about 37 KB to 12 KB with no Codex compaction needed.

Decisions for you:
- **bob-cli rules:** is it acceptable that unplanned bob-cli agents no longer see the decision rules? The alternative is a titles-only roster for every agent, at about 1,700 tokens a turn.
- **Validator strictness:** should a missing roster read be an error (my recommendation) or a warning?
- **Command meaning:** are you OK changing what the bare `sase memory read <web>` returns?
- **Research agents:** should research prompts also run the `--for plan` read?
