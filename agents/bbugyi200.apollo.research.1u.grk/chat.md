# Chat History - ace-run (research.1u.grk)

- **TIMESTAMP:** 2026-10-16 18:13:54 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.1u.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_175332.md`

## Prompt

%id(grk, clan=research.1u)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.1u.cdx`, `research.1u.cld`, `research.1u.mus`, `research.1u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with gastown (see the
https://github.com/gastownhall/gastown GitHub repo), with a particular focus on the
things that gastown does better than sase? End your analysis with a ranked list of ways
that gastown is superior to sase along with a (not necessarily one-to-one) ranked list
of recommended changes you think I should consider making to sase based on your report's
findings. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll research Gastown independently and compare it with SASE, then write a `__grk` report. First I'm loading the research, repo, artifact, and memory skills so the work stays on the required paths.

I'll record skill use, read artifact memory, and open the Gastown and research repos so the comparison stays on audited paths.

Gastown is open. Next I’ll open the research sidecar, then map Gastown’s tree and any existing 202610 reports by filename only.

I’ll read Gastown’s design docs and the matching SASE surfaces next, then check GitHub activity so the comparison is evidence-based.

SASE already discusses Gas Town in its orchestration post. I’ll read that alongside SASE’s agent, monitor, and work-unit docs, then check Gastown’s live public docs.

I’ll verify GitHub activity, the reported shutdown, and a few implementation files so the ranking rests on shipped behavior.

The stem is free. I’ll write the independent `__grk` report from the Gastown checkout and SASE docs, then register it as a research artifact.

The report is on disk. Next I’ll register it as a durable snapshot with the exact `research:` label.

Independent comparison is in `research:202610/gastown_advantages_over_sase__grk.md`. I did not read the other swarm reports.

**Report:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/gastown_advantages_over_sase__grk.md`  
**Artifact:** `file:explicit:09e860ac6fca9fa4e9ec1074` (source left in the research repo; no `--move`)

Gas Town is a living town of specialized agents whose work, identity, and mail live outside any one context window. SASE is a cockpit for single-turn agents with host-owned landing. Gas Town is stronger on durable assignment, mail, named identity, cheap worktrees, AI supervisors, merge-queue roles, and recovery (`gt prime` / `gt seance`). Yegge later stopped running the town himself, and `main` has been quiet since 2026-07-23; steal the primitives, keep the cockpit.

### Ranked ways Gas Town is superior

1. Durable hook + GUPP (assignment survives the session; hooked work is mandatory)
2. Typed persistent agent mail
3. Persistent named identity, CV, and git/bead attribution
4. Worktree workers under a town/rig HQ with a live shared ledger
5. AI supervisor chain with a problems view (GUPP / zombie / stalled)
6. `gt prime` + `gt seance` as normal recovery
7. Implementer / merger split with a bisecting merge queue
8. Mayor as the default conversational dispatcher
9. Formulas-as-current-job plus role directives and overlays
10. Convoy as a cross-project landing tracker
11. Agent-initiated severity escalation with stale re-page
12. Work-queue capacity governor (`max_polecats`)
13. `gt doctor --fix` for harness rot
14. Immediate nudge into a living session
15. OTLP export of agent operations; quota-pause as a healthy stall
16. Docker-compose HQ packaging
17. Wasteland federated wanted board (early; below the local-fleet gaps)

### Ranked SASE changes to consider

Keep single-turn agents, host-owned commits, and non-blocking gates.

1. Hooked work as first-class state, with a GUPP successor
2. Agent mailboxes with a small typed vocabulary
3. Durable worker identities and CVs (stamp stitches; optional `GIT_AUTHOR_NAME`)
4. Worktree workspace flavor for polecat-class jobs
5. Patrol agents as AXE-launched, formula-bound turns
6. Problems-first fleet view
7. `sase agent prime` as a recovery verb
8. Seance: interview a predecessor run
9. Host-owned lander with batch-then-bisect
10. Optional Mayor session / `#mayor` macro
11. Convoys on existing epic/plan/clan objects
12. `sase escalate` with stale re-notify
13. Role directives and formula overlays for bundled macros
14. Dispatch queue in front of runner slots
15. Doctor `--fix` for harness rot, behind existing gates
16. Usage-limit as a stall, with provider/account rotation
17. Opt-in OTLP export of agent operations
18. Skip Wasteland, auto-routing, and tmux-as-default-runtime

Sources: Gas Town @ `649b832b` (docs, formulas, `prime`/`seance`, CHANGELOG), SASE docs, GitHub API (18,390 stars; `main` last commit 2026-07-23), Yegge, Maggie Appleton, and later shutdown/successor reporting.
