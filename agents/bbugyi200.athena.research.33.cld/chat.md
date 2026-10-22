# Chat History - ace-run (research.33.cld)

- **TIMESTAMP:** 2026-10-01 03:10:52 EDT
- **MODEL:** claude/opus
- **AGENT:** research.33.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_025457.md`

## Prompt

%id(cld, clan=research.33)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.33.cdx`, `research.33.grk`, `research.33.mus`, `research.33.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you critique
sase against the standards / best practices / learnings described in
https://openai.com/index/harness-engineering/? End your analysis with a set of
actionable takeaways (i.e. some advice on how I could improve sase). 
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

Fetched the article; now reading it fully before surveying sase's harness.

Launching parallel surveys of sase's enforcement, knowledge, feedback-loop, and autonomy/GC machinery while I read the relevant memory notes.

Evidence collection is done. Two quick spot-checks (mentor config, which `sase` binary is on PATH), then I'll write the report.

Report written; registering it as a durable artifact.

Registration succeeded. Now the final declaration.

I've written the critique and registered it as an artifact (`file:explicit:f72a597cfb510e1b48fdbc7c`), and the commit to the research repo is declared. openai.com blocked direct fetches (HTTP 403), so I read the article's full text through a reader proxy; the report paraphrases it, with only short quotes.

**Report:** `sase/repos/research/202610/sase_vs_openai_harness_engineering__cld.md` (label `research:202610/sase_vs_openai_harness_engineering__cld.md`)

**Overall:** sase is a mature harness and beats the article in several places: decision records, generated and drift-checked instruction files, audited memory reads, failure triage that labels known and flaky failures, and a fake provider for testing the harness itself. Per human it also runs at a far higher volume: about 15.5k commits since February and roughly 2.6M lines of Python with one human, against OpenAI's ~1,500 PRs with 3–7 engineers. Its weak spots are the loops the article treats as essential:

1. **No agent-to-agent review before landing.** Commits rebase and push straight to master, with no PRs and no merge commits in 30 days. Mentors exist but aren't configured for this repo and don't block anything.
2. **Some key rules are instructions, not checks.**
   - The Rust-core boundary is only stated in prose.
   - "Run `just check` before finishing" isn't enforced; skipping it just marks the commit `unverified`.
   - The 517k-line `ace` package has no declared layering.
3. **The file-size limit is checked after the fact.** About 18% of the last 30 days' commits (341 of 1,897) are agents splitting files that other agents made too large, because the size check is left out of `just check`.
4. **No isolated app instance per workspace.** `sase screenshot` runs the installed release against your real `~/.sase` state, not the workspace's code. Telemetry and traces go to shared global paths.
5. **The knowledge system has gaps.**
   - `AGENTS.md` is 283 lines, about half of it lists, and the decisions list still includes superseded records.
   - The routines that clean up file size and refresh docs live only in `~/.config/sase/sase_athena.yml`, so agents in the repo can't see them.
   - Docs get a recurring refresh agent, but memory notes and nested `AGENTS.md` files don't.
   - There are no quality grades and no single tech-debt view.

**Top takeaways** (the report has 14, in three tiers):
- **Review loop:** add a capped agent-review loop at landing, with a fallback that reviews after landing and files bug beads.
- **Verified landings:** measure how many landed commits passed `just check`, then require it the same way `tools/require_tool_run` forces checks through `sase tool run`.
- **File size:** make the size check fail only when the current change grows a file past the limit, so the authoring agent fixes it.
- **Architecture:** write the layering down as a checked contract and generate the architecture doc's dependency rules from it.
- **Sandbox:** add a per-workspace sandbox (`just sandbox up|down`) that runs this workspace's code against throwaway state.
- **Routines in the repo:** move the file-split, docs-refresh and CI-watch routines into `sase/sase.yml` so other machines and agents get them too.
- **Smaller always-loaded map:** shrink `AGENTS.md` and give it a line budget.
- **Memory lint:** add a memory lint that checks paths, commands and links in memory notes and nested `AGENTS.md` files.
- **Living epics:** let epics carry progress, decision-log and outcome sections that phase workers and the land agent fill in.

I spot-checked the main claims myself: the ruff config, the `Justfile` check recipes, commit stats, routine config, the missing mentor config and the screenshot launch path. Survey subagents gathered the rest.
