# Chat History - ace-run (research.02.cld)

- **TIMESTAMP:** 2026-10-02 11:20:12 EDT
- **MODEL:** claude/opus
- **AGENT:** research.02.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_110156.md`

## Prompt

%id(cld, clan=research.02)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.02.cdx`, `research.02.grk`, `research.02.mus`, `research.02.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

I'm surveying the memory notes and how they render into the 283-line instruction files. Next I'll look at the renderer code.

Still reading the renderer (`src/sase/amd/_memory.py`) to see where each section of the 283 lines comes from and what knobs already exist.

I have the outside evidence. Now I'm checking how agents actually use the memory notes (read logs) and reading the relevant decision records.

Pulling raw read events to see which agents actually consult decisions and glossary entries, and how often.

Checking what the provider adapters already inject into each agent's prompt, so I can tell which instruction-file rules are duplicated there.

Next I'm checking the 100-line budget against real numbers: line wrapping, the token cost of each section, and whether memory rendering sits in Python or in the Rust core.

I checked all three against the official code.claude.com docs.

**(1) Yes: `claudeMdExcludes`** (https://code.claude.com/docs/en/memory#exclude-specific-claude-md-files)
- It takes a list of patterns: *"lets you skip specific files by path or glob pattern."* The doc's example is `["**/monorepo/CLAUDE.md", "/home/user/monorepo/other-team/.claude/rules/**"]`.
- Matching: *"Patterns are matched against absolute file paths using glob syntax."*
- Scopes: *"You can configure `claudeMdExcludes` at any settings layer: user, project, local, or managed policy. Arrays merge across layers."* The docs suggest `.claude/settings.local.json`.
- It also applies to AGENTS.md files. *"Managed policy CLAUDE.md files cannot be excluded."*

**(2) No flag skips only the ancestor files.** These are the broader switches:
- `CLAUDE_CODE_DISABLE_CLAUDE_MDS=1`: *"prevent loading any CLAUDE.md memory files into context, including user, project, and auto memory files"* (https://code.claude.com/docs/en/env-vars).
- `--bare` (same as `CLAUDE_CODE_SIMPLE=1`): skips *"auto memory, and CLAUDE.md"* along with hooks, skills and plugins (https://code.claude.com/docs/en/cli-reference).
- `--safe-mode`: CLAUDE.md and auto memory *"do not load"*. Managed CLAUDE.md is also skipped.
- `--setting-sources user,project,local`: the memory doc says excluding `project` skips project rules, and excluding `local` skips CLAUDE.local.md. The Agent SDK table (https://code.claude.com/docs/en/agent-sdk/claude-code-features) lists *"Project (parent dirs) | CLAUDE.md files in directories above cwd | settingSources includes 'project'"*. ⚠ The CLI reference itself doesn't say the flag controls CLAUDE.md, so applying the SDK table to the CLI flag is my inference.

**(3) Yes, AGENTS.md is read natively from v2.1.277** (https://code.claude.com/docs/en/memory#agents-md)
- By default it is read only when there is *"no `CLAUDE.md` or `CLAUDE.local.md` in your working directory or above it."* If a CLAUDE.md exists, *"Your `CLAUDE.md` files only"* are read.
- The **Project instructions** setting changes this. Its values are `claude-md-or-agents-md` (the default), `claude-md-and-agents-md`, `claude-md` and `managed-only`. In a settings file it goes under `pluginConfigs` → `agents-md@builtin` → `options.instructionFiles`, and is ignored in project and local settings.
- Not read: `AGENTS.local.md`, `AGENTS.override.md` and `.agents/`.

The file's history shows growth by accretion: 33 lines in late May, a peak of 361 in August, 283 now. I'm checking what the small version contained.

I'm drafting a concrete ≤100-line mock of the rendered file and running it through the project's own Markdown formatter, so the line count is measured, not estimated.

Evidence gathering is done. Before writing, I'm loading the memory-write skill, because the report will propose edits to memory notes.

I have everything I need. Writing the report now.

The report is written and registered. Finishing with the SASE final declaration.

Getting to 100 lines is a good idea and doable without dropping anything agents rely on. I built a mock of the rendered file (Appendix A of the report) and ran it through the project's own Markdown formatter. It comes out at 101 lines and about 1,380 tokens, down from 283 lines and about 4,300. It keeps every core rule, all 10 reference-note triggers and all three web rosters. Turning the decisions list into a one-line pointer gets it to 93 lines.

**Where the 283 lines go:**
- **Decisions roster:** 90 lines, about 36% of the tokens. Over the past month (1,460 audited memory reads), only about 19 agents other than research agents opened a decision record. Two of the 24 rows are fully superseded but still load on every turn.
- **Reference-note triggers:** these work and must survive. Short "read X before Y" lines brought 415 agents to `lint_and_test.md`.
- **Glossary roster:** works as an index (about 56 non-research agents looked up terms). It can lose the aliases and stay.
- **Generated `sase.md`:** 76 lines, mostly restating skill descriptions. The same template also produces `~/CLAUDE.md`, which Claude agents load on top of the project file. That puts their real load at about 357 lines.
- **History:** the file went from 33 lines (May) to 361 (August) to 283 now. The 33-line version was only short because it used `@imports`, which still cost context in Claude and aren't expanded by Codex.

**Changes I'd make to the requirement:**
- **Measure what is actually loaded, not file lines.** Budget at most 100 lines *and* about 1,600 tokens per provider, counting imports and Claude's parent-folder `CLAUDE.md` files. A line count alone can be gamed by widening the wrap width.
- **Aim for about 85 lines,** so the next new core note doesn't immediately push it over and someone just raises the limit.
- **Enforce it.** `sase memory init --check` should fail when over budget and print a per-section breakdown.
- **Keep every trigger line.** Moving triggers into skills or `@imports` is the wrong way to cut: in Vercel's tests, agents never invoked the skill in 56% of cases.

**Recommended path:**
1. **No-code edits (about 283 → 200 lines):**
   - Switch the decisions roster to the existing inline format.
   - Rewrite reference descriptions as one-line triggers.
   - Tighten the Rust-boundary and gotchas notes.
2. **Small Python renderer changes (to about 100 lines):**
   - Rewrite the shared `sase.md` template as four short bullets; this also shrinks `~/CLAUDE.md`.
   - Add a titles-only roster option with no aliases.
   - Stop loading fully superseded decisions.
   - Make the task-types section a one-line list.
   - Add the budget check.
3. **Governance:**
   - Write a new decision record for the budget. The existing `webs-render-in-their-own-section` decision says to reopen it in exactly this situation.
   - Link each decision from the reference note for its area, so agents see it when they read that note.
4. **Optional:** have the Claude adapter skip ancestor `CLAUDE.md` files. That's your call, because project agents would then stop seeing home memory such as `tailnet.md`, which 27 of them read last month.

Steps 1–3 change memory files, so they need an approved plan that names each file. I made no memory edits.

I'd consider rolling back the decisions cut if non-research decision reads or `/sase_final` compliance drop afterwards. The fallback is about 6 always-loaded lines for the handful of decisions every agent must follow.

The report was created without overwriting anything and registered with `sase artifact create` (`file:explicit:bbeeefe6e2b9067448adf2ea`, label `research:202610/agent_instruction_files_100_line_budget__cld.md`). The commit to the research repo has been declared and will land after this turn ends.

File: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/agent_instruction_files_100_line_budget__cld.md`
