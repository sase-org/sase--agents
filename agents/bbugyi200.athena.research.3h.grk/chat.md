# Chat History - ace-run (research.3h.grk)

- **TIMESTAMP:** 2026-10-03 13:52:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3h.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_133508.md`

## Prompt

%id(grk, clan=research.3h)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3h.cdx`, `research.3h.cld`, `research.3h.mus`, `research.3h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll start by reading the research and SASE skills, then independently investigate the Apollo OOM kills without looking at the other swarm reports.

I'll open the research repo, then pull agent status, memory, and Apollo/OOM context in parallel.

Research repo is open. Next I’ll pull dispatch/artifact memory, host identity, and any existing Apollo/OOM evidence.

We're on Athena; Apollo is a remote enrolled machine. I'll pull fleet status, OOM history, and agent-kill evidence next.

Apollo is enrolled and reachable. Next I’ll inspect fleet events, remote agent state, and whether we can SSH in for OOM logs.

Failed-bucket agents and prior Apollo research look useful; I’ll inspect those and try SSH for kernel OOM logs.

Apollo has 31 GiB RAM and no swap — a strong OOM-kill risk. I’ll pull kernel logs, cgroup limits, and live agent memory next.

User journal confirms real OOM kills of `tmux-spawn` scopes, including one minutes ago. I’ll pull those event windows and the SASE OOMPolicy test path next.

The 16:24 kill is the smoking gun: one tmux pane peaked at 29 GiB. I’ll trace that process, TUI/agent spawn, and whether OOMPolicy tests are blowing the box.

TUI RSS is already climbing, and two agents were marked `killed` at the 17:32 OOM. I’ll pull Apollo’s SASE config, TUI memory history, and the rest of those kill records.

I have a confirmed causal chain: 32 GiB, no swap, TUI heap growth, and TUI-launched agents stuck in the same `tmux-spawn` cgroup. Next I’ll write the independent report.

Artifact is registered. I’ll submit the SASE finalizer next so the research repo commit is declared.

Apollo is OOM-killing the long-lived TUI tmux pane, and TUI-launched agents die with it. The report is `research:202610/apollo_sase_agent_oom_kills__grk.md` (snapshot `file:explicit:c53a8d5690be51c7d8ec4a2c`).

**What is happening.** Apollo is a 32 GiB DigitalOcean droplet with **no swap**. `systemd-oomd` is not installed. User cgroup `memory.max` is unlimited. The kernel OOM killer is real: user-journal `oom-kill` on `tmux-spawn-*.scope` on Sep 3, Oct 1 21:15 UTC, Oct 3 16:24 UTC (**29.0 GiB peak**, SIGKILL of `zsh` + `python3` + `claude`), and Oct 3 17:32 UTC. After 16:24 the TUI’s `agent_row_count` dropped from 46 to 7. Two in-flight agents (`sase-1fs.1--1`, `4r.f1.f0`) recorded `outcome: killed` at the 17:32 event.

**Why every agent dies.** `detach_scope()` only wraps children in `systemd-run --user --scope` when the parent is already `sase.service` / `sase-*`. A TUI in `tmux-spawn-*.scope` fails that check, so `setsid` leaves the runner and `claude`/`muse`/`codex` in the TUI cgroup. systemd then fails the whole pane. Axe-scoped agents can still die in the same global OOM because there is no swap and no `MemoryMax`.

**Why Apollo and not Athena.** Same TUI heap-bloat (snapshot caches; a fresh Apollo TUI hit a **5.8 GiB cgroup peak in 14 minutes**). Athena has 64 GiB RAM and 64 GiB swap, so it pages. Apollo has neither. `max_running_agents` is already overridden to 5; that is not enough.

**Recommended fix, in order.**

1. **Today, on Apollo:** 8 GiB zram + 16 GiB swapfile (51 GiB disk free; no resize required).
2. Restart the TUI around 4 GiB RSS; keep runner cap at 3–4; set `sase.service` `OOMPolicy=continue`.
3. Enable `systemd-oomd` (or earlyoom); optional user-slice `MemoryHigh=24G` / `MemoryMax=28G`.
4. **SASE code:** always `systemd-run` agent runners from the TUI, with `MemoryMax=6G` and `OOMPolicy=kill`, so one provider dies alone.
5. Land the TUI snapshot-cache fix from `research:202610/tui_freeze_gc_heap_bloat`.
6. Optional later: in-place resize to 64 GiB. Do that after swap and cgroup isolation, not instead of them.
