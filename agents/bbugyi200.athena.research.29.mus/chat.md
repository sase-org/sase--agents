# Chat History - ace-run (research.29.mus)

- **TIMESTAMP:** 2026-09-22 12:32:21 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.29.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_122509.md`

## Prompt

%id(mus, clan=research.29)
%m:muse/muse-spark-1.3-contributor@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 3-researcher swarm.
The other researchers, `research.29.cld`, `research.29.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? Note that I had some agents do some research on this issue yesterday but I
don't think the research swarm finished (feel free to review those research files for
inspiration, but make sure to verify any claims you intend to use in your own research).
End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete.

**Report:** [headless_singleturn_early_exit__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/sase/repos/research/202609/headless_singleturn_early_exit/headless_singleturn_early_exit__mus.md) — registered as `file:explicit:d54caf11de8c1286297f4947` (label `research:202609/headless_singleturn_early_exit/headless_singleturn_early_exit__mus.md`), final declaration accepted.

**Verdict:** the hypothesis is confirmed with a refinement — three things look identical ("long command, monitor, agent died") and only one is the headless misunderstanding:

1. Silent false success (provider-native background + wait-ending reply recorded as `completed`). Fixed for Claude since Sep 15; still active for agy; latent for Grok/Muse/Codex, whose invoke loops return the first reply unconditionally with no wait guard (verified in code).
2. Designed monitor handoffs used destructively — agents cancel in-flight verification and restart it under a monitor. The handoff machinery itself is healthy (1319 monitors: 537 completed, 710 failed-but-followed-up, only 3 lost).
3. Slow verification underneath both (`just check` p90 34–45 min vs. every provider's shorter foreground window).

My own transcript scan (newest 300 chats) found no fresh wait-ending failures — the only hits were researchers quoting the old cases.

**Recommended solution (phased):** Phase 0 — provider-neutral host backstop (a run with an assigned bead but no declaration or mechanical handoff is `incomplete`, closing the clean-tree silent-success gap I verified in `declaration_store.py`); repair agy's directive/classifier/trajectory gating; replace mid-flight guidance with up-front per-provider rules. Phase 1 — lossless mechanical handoff (detachable/joinable ToolRuns, monitor adoption, `--handoff-after`). Phase 2 — loop governor and faster verification. Prompt text alone will not fix it — agy's harness overrides prompts.
