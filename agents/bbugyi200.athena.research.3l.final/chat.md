# Chat History - ace-run (research.3l.final)

- **TIMESTAMP:** 2026-10-04 16:22:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3l.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_145503.md`

## Prompt

%clan(research.3l, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you help me dig into the research sidecar repo for all research swarms that Gemini
models contributed to (the files they produced end with `__gem.md`) and find ones (if
any) where Gemini provided unique insights that the other models in the swarm did not
that were actually included in the final research report? End your analysis with a list
of those research files and a summary of what unique contributions Gemini made to them.]]) %id:research.3l.final %m:@xlarge
%wait:research.3l.cdx %wait:research.3l.cld %wait:research.3l.grk %wait:research.3l.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you help me dig into the research sidecar repo for all research swarms that Gemini
models contributed to (the files they produced end with `__gem.md`) and find ones (if
any) where Gemini provided unique insights that the other models in the swarm did not
that were actually included in the final research report? End your analysis with a list
of those research files and a summary of what unique contributions Gemini made to them.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.3l.cdx`, `research.3l.cld`, `research.3l.grk`, `research.3l.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.3l.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3l.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__gem.md
├── <name>__final.md
└── <name>_narration.md
```

## Response

I've read the grk and gem reports; now reading the full cdx and cld reports.

Read all four reports. Now checking the corpus state and the points where the reports disagree.

Next I'll check how `_narration.md` files have been produced in past swarms, and confirm my chosen stem doesn't collide with anything.

I'm using the stem `gemini_only_insights_in_research_swarm_finals` and moving the four reports into its directory now.

Moves are done. I'm writing the consolidated report now.

Checking the report against my notes turned up a few count errors. Fixing them now.

Next I'll check that every relative link in the report resolves, then register the artifact.

Registered. Now the final declaration.

The consolidated report is written and registered. Gemini contributed something no other researcher had, and the lead kept it, in 17 of the 65 completed swarms it joined: 12 clear cases and 5 qualified ones.

**Corpus:** there are 69 `__gem.md` reports. 65 belong to swarms with a final report; the other 4 are loose drafts with no final, so they can't count. Beyond the 17, 23 swarms kept only minor Gemini-only details and 25 kept nothing unique from Gemini.

**How I settled it:** the four researchers named 12 to 15 swarms each, and only 3 swarms were on all four lists. I re-checked all 27 swarms that any of them flagged, comparing each final against the Gemini report and every other researcher's report in that swarm. 15 minor-only swarms that no one disputed were not re-checked; they rely on cld's grading.

**What changed after checking:**
- **Credits in finals are wrong in both directions.**
  - At least nine finals credit Gemini for ideas another researcher had first: the "test tax" (cld and grk), the Böckeler companion read (cld), the "Run project tool…" palette entry (cdx), artifact tags (cdx), the `P` key (grk's runner-up), and −16 LUFS (cld).
  - Three Gemini-only findings were adopted with no credit: the stale core pin, the `v`/`view_files` key clash, and the `,j` cache miss.
- **Which reports came closest:** cld was closest to the checked result. grk and gem (the Gemini researcher auditing itself) over-counted by trusting the finals' credits. cdx under-counted.
- **Why cdx and cld missed the sasos rename swarm:** `should_sase_become_sasos` was only consolidated at 14:57 today, after they had taken their inventories.

**Pattern:** what survives is usually one sharp, checkable item per swarm. These come from running things live, from Gemini's knowledge of its own Antigravity harness, from tracing version pins across repos, from UI edge cases, and from name searches. Its architecture proposals and unmeasured numbers were usually rejected. It also matters more in small swarms: 6 of 15 three-researcher swarms have a clear case, versus 6 of 49 swarms with four or five researchers.

## Research files where a Gemini-only insight reached the final

**Clear cases (12):**
1. `202609/agent_long_command_early_exits`: Antigravity's 10 s `run_command` cap, the tool text telling the model to end its turn, and the 5 s idle kill in print mode. Gemini also showed a working escape live: keep calling tools until the command finishes.
2. `202609/sase_services_post_landing_hardening`: `sase scheduler restart` is a no-op because `delay=0.0` clears the stop marker before the host reads it. Also a duplicate launch when a child survives SIGKILL, `proc start` reporting success on a disabled proc, and an undocumented `r` key.
3. `202609/sase_master_ci_repair_and_pypi_0_18_release`: a stale `sase-core-revision.txt` pin (the bindings exist only in `33b0250`). This became the largest CI failure cluster and the Wave 1 fix, with no credit to Gemini.
4. `202609/agents_dynamic_tabs`: an emptied active tab stays put (requirement R11). Two other researchers proposed the opposite.
5. `202609/core_schema_skew_outage_recovery_ux`: a second schema-skew channel, where each workspace's `just _setup` fast-forwards and rebuilds `sase-core`.
6. `202609/bead_speedup_daemon_vs_direct_path`: the first bead command in a fresh workspace takes 10–30 s because of the sidecar clone. It became TL;DR item 2, requirement RA7, a Phase 0 fix, and bead `sase-17r`.
7. `202609/unread_ack_reliability_and_tui_responsiveness`: under lag, a double press of `,u` silently undoes and restores all 27 unread markers (requirement R5). Also, every `,j` misses the candidate cache.
8. `202609/sase_core_agent_maintainability`: bare `cargo check` fails because pyenv's Python is 3.11 and the binding needs 3.12.
9. `202609/tui_colon_command_line`: a side-by-side documentation preview next to completions on wide terminals, and ranking the linked bead first.
10. `202609/sase_terminology_renames`: retire the `task` alias on `sase proc`, since "task" now means a bead tier (recommendation 6).
11. `202610/sase_rename_new_name_shortlist`: the name `baste`, ranked #2 and one of three finalists, plus ten "graveyard" names already taken by agent tools.
12. `202610/should_sase_become_sasos`: Nokia's 7210 SAS OS switch firmware as a spoken `sasos` collision.

**Qualified cases (5):**
13. `202609/sase_vs_hermes_agent`: Hermes approvals block a live process while sase gates are durable. This was emphasis rather than discovery, but it raised sase's human-approval score from 7 to 8.
14. `202609/goal_outcomes_and_verification`: a synced per-goal live directory any machine can rebuild from, kept in heavily reworked form as `goals/live/<id>.json`.
15. `202609/deck_card_paging_ux`: `v` is already bound to `view_files`, which ruled out another researcher's proposed key (no credit in the final).
16. `202610/prompt_space_and_project_cycle_latency`: a ~27 ms import on first mount plus staggering the startup workers, kept as secondary "mount hygiene".
17. `202610/commute_audio_from_markdown`: a −1.5 dBTP peak ceiling, 0.6 s / 1.2 s pauses, and a no-root ffmpeg install via `static-ffmpeg` under `uv`.

The four reports now sit in `202610/gemini_only_insights_in_research_swarm_finals/` with their suffixes. The final report is `gemini_only_insights_in_research_swarm_finals__final.md`, registered as `research:202610/gemini_only_insights_in_research_swarm_finals/gemini_only_insights_in_research_swarm_finals__final.md`. I didn't create `<name>.md` (the linker publishes it) or `<name>_narration.md`, which has come from a separate step in past swarms. The research-repo commit has been declared and is made after this turn ends.
