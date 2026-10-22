# Chat History - ace-run (research.3h.mus)

- **TIMESTAMP:** 2026-10-03 13:43:17 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3h.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_133508.md`

## Prompt

%id(mus, clan=research.3h)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3h.cdx`, `research.3h.cld`, `research.3h.grk`, `research.3h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

My
apollo machine keeps killing all of its sase agents due to OOM errors I believe. Can you
dig into this / do some research with the goal of helping me figure out what is causing
this and fix it? End your analysis with a recommended solution. 
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

Finding: apollo (31 Gi RAM, 0 swap, 16 cores) vs athena (62 Gi RAM, 63 Gi swap, 64 cores). Each sase agent costs ~1–3 Gi (runner 0.35–1.1 Gi + provider CLI 0.2–0.45 Gi + rustc up to 1.9 Gi / pytest workers ~1 Gi each, observed via `ps`); sase admission is count-based (`max_running_agents` default 10, apollo override 5) with no memory check. Athena survives the same fleet via 18 Gi of swap in use; apollo has no cushion, so correlated swarm fan-out triggers the kernel OOM-killer. OOM log unconfirmed (apollo `journalctl` restricted) — confirm with `sudo dmesg -T | grep -i oom`.

Recommended fix, in order: (1) add 16–32 Gi swap to apollo, (2) keep cap at 5 (or 3–4 for build-heavy swarms), (3) run heavy builds/tests staggered or on athena.

Report: `sase/repos/research/202610/apollo_oom_sase_agents__mus.md`, registered as `research:202610/apollo_oom_sase_agents__mus.md` (artifact `explicit:3e8f93cddbbf12b724e5e605`). Final declaration accepted for commit.
