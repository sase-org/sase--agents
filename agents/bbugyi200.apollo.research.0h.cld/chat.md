# Chat History - ace-run (research.0h.cld)

- **TIMESTAMP:** 2026-10-07 17:35:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0h.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_171417.md`

## Prompt

%id(cld, clan=research.0h)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0h.cdx`, `research.0h.grk`, `research.0h.mus`, `research.0h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with omniagent (see the code
and documentation at https://github.com/omnigent-ai/omnigent for context)? End your
analysis with a ranked list of recommended changes you think I should consider making to
sase based on this comparison. 
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

Research is complete and the target path is free. Writing the report now.

Report written. Registering it as a durable artifact.

I wrote the omnigent vs sase comparison and registered it as an artifact. The final declaration was accepted, so the host will commit the report to the research repo after this turn. Nothing was executed from either codebase; everything comes from reading the code and docs.

**Report:** `sase/repos/research/202610/omnigent_meta_harness_vs_sase__cld.md`
**Artifact:** `file:explicit:c5bff9845eba25917f743182`, label `research:202610/omnigent_meta_harness_vs_sase__cld.md`

**How the two compare:**
- **Omnigent is a team product.** It's a server plus web, desktop and phone UI over long-running chat sessions. It covers about 27 harness variants (roughly 16 agent products, plus any CLI that speaks the Agent Client Protocol, ACP). It's largely built by Databricks/MLflow people and ships about weekly.
- **Omnigent is far ahead on governance.** It has an allow/deny/ask policy engine plugged into each CLI's own hooks, optional OS sandboxing, a network allowlist proxy, environment allowlists, dollar budgets, and a test bench that catches when a harness stops doing what it claims. sase has none of these mechanically: every provider runs with its permission-bypass flag and gets the full host environment.
- **sase is ahead on keeping work safe and structured.** Omnigent keeps live turn and approval state in memory, and its own resilience tests list open failures such as messages lost while a machine is unreachable. sase's single-turn agents, on-disk gates, host-owned commits, beads/epics and memory system avoid that whole class of problem.

**Ranked recommendations (top 6 of 12; the rest are in the report):**
1. **Block risky tool calls through provider hooks.** Deny-only, with each denial pointing to the approved route (`/sase_final`, `/sase_sudo`, `sase repo open`, `sase artifact read`, `/sase_gate`). This turns prose rules into enforced ones: no commits by agents, no writes outside the workspace, read-only research and review roles. sase already has the Claude hook plumbing; it's used for one rule today.
2. **Review by a different vendor, seeing only the diff and the acceptance criteria.** This is omnigent's cross-review pattern. It would apply to the epic land agent and mentors, with fixes sent back to the original implementer's session.
3. **A provider capability table plus live checks that flag drift.** These would run on CLI upgrades, since an update can quietly break sase's single-turn safeguards.
4. **Pass providers only an allowlisted environment** instead of a full copy. This is the cheapest security win.
5. **Roll up cost and usage per epic, clan or goal, with budgets checked at launch.** Over budget, the model size steps down instead of the run being refused.
6. **A `join_launched` continuation:** wake the requesting agent when its launched children finish, with their results attached.

The report also lists what not to copy: long-running steerable sessions, the multi-user web server stack, LLM-judged policies, and Hindsight-style memory.

Two caveats:
- Omnigent's README says its native terminals run sandboxed on Linux. But the spec it generates for `omnigent claude` declares no sandbox, so the default appears to be no sandboxing.
- Several design docs that omnigent's code cites aren't in the open-source repo.
